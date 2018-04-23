# Gradient° SSH Test

<img width="899" alt="screen shot 2018-04-23 at 9 52 09 am" src="https://user-images.githubusercontent.com/585865/39141590-0fab55c8-46dd-11e8-9b0d-07370086723b.png">

Simple SSH workspace to connect to your running [Gradient°](https://www.paperspace.com/gradient) job.

## Running this workspace

```
paperspace jobs create --machineType P100 --container Test-Container --ports 8888:22 --command './run.sh' --workspace ~/sshjob/run.sh
```

Alternatively, you can clone this repo locally and run it from your own machine:

```
git clone git@github.com:Paperspace/gradient-ssh-test.git && cd gradient-ssh-test

paperspace project init

paperspace jobs create --machineType P100 --container Test-Container --ports 8888:22 --command './run.sh' 

```

## Additional Notes

Check out the accompanying HelpDesk tutorial [here](https://paperspace.zendesk.com/hc/en-us/articles/360003413994)

