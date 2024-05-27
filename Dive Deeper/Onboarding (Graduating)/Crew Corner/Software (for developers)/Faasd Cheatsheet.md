Add your docker account prefix: ```
```
export OPENFAAS_PREFIX="tbsfchnr"
```

OpenFaas CLI docs for creating new functions: https://docs.openfaas.com/cli/templates/

"Cannot connect to OpenFaaS on URL: ..." - need to login: ```
```
faas-cli login -g https://faasd.platform.earth/ -p {password}
```
Or, for less insecure password passing, try: `--password-stdin` in place of `-p {password}`

May still persist. Try adding the domain as an environment variable: 
```
export OPENFAAS_URL=https://faasd.platform.earth
```
