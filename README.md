# ansible-submodule

Shared `group_vars` for the Ansible content repository
([McPedro8791/ansible](https://github.com/McPedro8791/ansible)), included there as
a git submodule at `group_vars/` (and reached by Ansible through the symlink
`inventory/group_vars`).

- `all.yml` - variables for every host.
- `<group>.yml` - variables for the inventory group `<group>` (for example `local.yml`).

The repository is **public**: it must not contain secrets. Values that must stay
secret come from Kubernetes (`# param: ... | type=const | from=secret:...`).

After a change here, bump the submodule pointer in the content repository
(`git add group_vars && git commit`), because a run uses exactly the commit the
content repository points to.
