# Adopted from [Saiyam's tutorial](https://www.youtube.com/watch?v=KAa2l0oycOk)

### Status

Ingress does not find Pod endpoints

Navigating to DNS-url/demo gives 404 error

### Notes

The commands used have been modified so that edits inside the files are kept to a minimum.

YAML files use environment variables for DNS address so that YAML manifests do not have to be edited. YAML manifest contain envt_var placeholders that are processed by envsubst.

The general structure of command for applying the manifests is:

`$ envsubst < <manifest> | kubectl apply -f -`
