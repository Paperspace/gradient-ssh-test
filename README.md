# Gradient° SSH Test

<img width="899" alt="screen shot 2018-04-23 at 9 52 09 am" src="https://user-images.githubusercontent.com/585865/39141590-0fab55c8-46dd-11e8-9b0d-07370086723b.png">

Simple SSH workspace to connect to your running [Gradient°](https://www.paperspace.com/gradient) job.

## Running this workspace

```
paperspace jobs create --machineType P100 --container Test-Container --ports 8888:22 --command './run.sh' --workspace "https://github.com/Paperspace/gradient-ssh-test.git" 
```

Alternatively, you can clone this repo locally and run it from your own machine:

```
git clone git@github.com:Paperspace/gradient-ssh-test.git && cd gradient-ssh-test

paperspace project init

paperspace jobs create --machineType P100 --container Test-Container --ports 8888:22 --command './run.sh' 

```

## Connecting to your running job

Once this job is running it will appear to stop at `processing triggers for systemd`. This is expected behavior as it waits for the SSH connection. 

<img width="1221" alt="screen shot 2018-04-23 at 10 13 53 am" src="https://user-images.githubusercontent.com/585865/39142309-26e1f4a2-46df-11e8-914e-0e70f29286e3.png">

You can now SSH to your job by getting the public IP address from the your console (https://www.paperspace.com/console/jobs) and then typing:

```
ssh ssh root@104.196.249.111 -p 8888
```

*Note: we are forwarding port `8888` to the container's SSH port `22` which you can see in the `--ports 8888:22` portion of the job run. This is because the host node cannot expose port `22` directly as it is reserved for internal communication. (TODO: make list of ports that cannot be used)*




## Additional Notes

Check out the accompanying HelpDesk tutorial [here](https://paperspace.zendesk.com/hc/en-us/articles/360003413994)

