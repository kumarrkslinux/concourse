
``` 
~/concourse$ fly -t ci_prod login --concourse-url https://ci.concouse.net/ --team-name linuxoperation[git reponame]
logging in to team 'linuxoperation```````'

navigate to the following URL in your browser:

  https://ci.concouse.net/login?fly_port=61536

or enter token manually (input hidden):
target saved
```

``` 
~/concourse$ cat task.yml
---
platform: linux
image_resource:
  type: docker-image
  source: {repository: busybox}
run:
  path: echo
  args: [hello world]
```

```  
~/concourse$ fly -t ci_prod execute -c task.yml
executing build 30530121 at https://ci.concouse.net/builds/30530121
initializing
waiting for docker to come up...
Pulling busybox@sha256:15a3c8a1b44b5ef66f9b4b2e1875b50302d100e116f1d4d5ede71d5ac63177c3...
docker.io/library/busybox@sha256:15a3c8a1b44b5ef66f9b4b2e1875b50302d100e116f1d4d5ede71d5ac63177c3: Pulling from library/busybox
2c39bef88607: Pulling fs layer
2c39bef88607: Verifying Checksum
2c39bef88607: Download complete
2c39bef88607: Pull complete
Digest: sha256:15a3c8a1b44b5ef66f9b4b2e1875b50302d100e116f1d4d5ede71d5ac63177c3
Status: Downloaded newer image for busybox@sha256:15a3c8a1b44b5ef66f9b4b2e1875b50302d100e116f1d4d5ede71d5ac63177c3
docker.io/library/busybox@sha256:15a3c8a1b44b5ef66f9b4b2e1875b50302d100e116f1d4d5ede71d5ac63177c3

Successfully pulled busybox@sha256:15a3c8a1b44b5ef66f9b4b2e1875b50302d100e116f1d4d5ede71d5ac63177c3.
```

selected worker: aws-99.113.144.16-16cc2
running echo hello world
hello world
succeeded
