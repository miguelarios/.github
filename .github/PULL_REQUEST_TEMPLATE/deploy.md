<!-- Use with ?template=deploy.md -->

## Service

<!-- Which container/host. e.g. paperless-ngx on Edith -->

## Change

| Field | From | To |
| --- | --- | --- |
| Image tag |  |  |
| Ports |  |  |
| Volumes |  |  |
| Env |  |  |

## Upstream release notes

<!-- Link. Call out breaking changes and required migrations. -->

## Deploy steps

- [ ] Merge
- [ ] `git pull` on the host
- [ ] `docker compose up -d <service>`
- [ ] Verify healthcheck and Traefik route
- [ ] Confirm data/volumes intact

## Rollback

<!-- Previous tag and the exact command to revert. -->
