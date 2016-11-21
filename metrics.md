# Nomenclature des metrics

```
{nom-du-projet-github}.{env}.container.{containerId}.worker.{workerId}.{key}
```

## nom de projets github

```
afrostream-back-end
afrostream-billings
```

## env

```
development
test
staging
production
```

## containerId

identifiant du container docker / heroku.  

heroku: variable d'environnement DYNO dans laquelle on remplace "." par "-"

```js 
var containerId = process.env.DYNO && String(process.env.DYNO).replace(/\./g, '-') || "unknown";
```

## workerId

identifiant du process

sous nodejs @see https://github.com/Afrostream/afrostream-node-statsd/blob/master/index.js#L12

```js
cluster.worker.id % numCPUs;
```

## Exemples
exemples

```
afrostream-back-end.production.container.24242242.worker.1.route.all.success     # 200
afrostream-back-end.production.container.24242242.worker.1.route.all.error       # 4xx,5xx
afrostream-back-end.production.container.24242242.worker.1.route.all.redirect    # 3xx
```

# Projet afrostream-back-end

```
# routage
route.all.success
route.all.error
route.all.redirect

route.api.video.success
route.api.video.error
route.api.video.redirect
```
