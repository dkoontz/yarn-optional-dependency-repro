This has 2 dependencies, a regular one and an optional one. `npm i` succeeds and `yarn --ignore-optional` works when there is only 1 optional dependency, but any other combination fails for yarn.

`npm i`

```
yarn-test@1.0.0 /home/davidk/yarn-test
└── left-pad@1.1.3 

npm WARN optional Skipping failed optional dependency //grunt-appdmg:
npm WARN notsup Not compatible with your operating system or architecture: grunt-appdmg@0.3.3
npm WARN yarn-test@1.0.0 No description
```

`yarn`

```
yarn install v0.19.1
info No lockfile found.
[1/4] Resolving packages...
[2/4] Fetching packages...
warning grunt-appdmg@0.3.3: The platform "linux" is incompatible with this module.
info "grunt-appdmg@0.3.3" is an optional dependency and failed compatibility check. Excluding it from installation.
error appdmg@0.3.10: The platform "linux" is incompatible with this module.
error Found incompatible module
info Visit https://yarnpkg.com/en/docs/cli/install for documentation about this command.
```

`yarn --ignore-optional`

```
yarn install v0.19.1
info No lockfile found.
[1/4] Resolving packages...
[2/4] Fetching packages...
warning grunt-appdmg@0.3.3: The platform "linux" is incompatible with this module.
info "grunt-appdmg@0.3.3" is an optional dependency and failed compatibility check. Excluding it from installation.
error appdmg@0.3.10: The platform "linux" is incompatible with this module.
error Found incompatible module
info Visit https://yarnpkg.com/en/docs/cli/install for documentation about this command.
```

If you remove the non-optional `leftpad` dependency 

`yarn`

```
yarn install v0.19.1
info No lockfile found.
[1/4] Resolving packages...
[2/4] Fetching packages...
warning grunt-appdmg@0.3.3: The platform "linux" is incompatible with this module.
info "grunt-appdmg@0.3.3" is an optional dependency and failed compatibility check. Excluding it from installation.
error appdmg@0.3.10: The platform "linux" is incompatible with this module.
error Found incompatible module
info Visit https://yarnpkg.com/en/docs/cli/install for documentation about this command.
```

`yarn --ignore-optional`

```
yarn install v0.19.1
info No lockfile found.
[1/4] Resolving packages...
success Nothing to install.
success Saved lockfile.
Done in 1.05s.
```
