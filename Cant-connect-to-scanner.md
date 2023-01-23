# Cant Connect to scanner error

If you get an error that you cannot start a scan task due to the following error report:

```
Cannot connect to scanner.
```
It could be that the default scanner doesnt have the permissions set correctly

Try the following to fix this:

## Within Linux

open a terminal and put in the following command either as root or sudo:

```
chmod 666 /var/run/ospd.sock
```

run it and it should not error out when you try to do a scan

## For docker image

(note: we are going to assume that the docker name is "gvm")

get the name of the docker image by typing in this

```
docker container ls
```

or 

```
docker stats
```

get the container name and execute the following command

```
docker exec gvm chmod 666 /var/run/ospd/ospd.sock
```
