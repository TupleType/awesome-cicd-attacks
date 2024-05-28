# https://twitter.com/alxk7i/status/1524353383976558593?t=5EsgWtom2218SgYgy5VdoA&s=19
```
alxkalxk @alxk7i
if you ever see self-hosted CircleCI runners:
- no access controls on runners, anyone in org can run job on them
- cat /proc/1/environ gives runner's API key
- register your own runner
- harvest creds from other projects in org from subsequent jobs CircleCI will dispatch to you
```