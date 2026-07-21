# Runbook

## Service

- Name: `review-api`
- Team: `Platform Engineering`
- Owner: `mooref068@gmail.com`
- Cost center: `platform-engineering`

## First Checks

```bash
kubectl get rollout review-api -n review-api-dev
kubectl get pods -l app.kubernetes.io/name=review-api -n review-api-dev
kubectl logs -l app.kubernetes.io/name=review-api -n review-api-dev
```

## Health

```bash
curl https://review-api.dev.platform.ohanyere.internal/healthz
curl https://review-api.dev.platform.ohanyere.internal/readyz
curl https://review-api.dev.platform.ohanyere.internal/livez
```

## Rollback

```bash
kubectl argo rollouts undo review-api -n review-api-dev
```

Escalate to `Platform Engineering` through `mooref068@gmail.com` if rollback does not restore service.
