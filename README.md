# k9s-karpenter-jumps

Press `Enter` on a Karpenter NodePool in k9s to list its NodeClaims in the same k9s session (instead of describing the NodePool).

Requires k9s >= 0.51.0 (custom jumps, [derailed/k9s#3736](https://github.com/derailed/k9s/pull/3736)).

## Install

Copy `jumps.yaml` to the `Custom Jumps` path shown by `k9s info`:

- macOS: `~/Library/Application Support/k9s/jumps.yaml`
- Linux: `~/.config/k9s/jumps.yaml`

If you already have a `jumps.yaml`, merge the entry under `jumps:`.

## Notes

- Only matches `karpenter.sh/v1`. On an older `v1beta1` cluster, add the same entry with `karpenter.sh/v1beta1/...`.
- One target per source: k9s ships [`jumps/karpenter.yaml`](https://github.com/derailed/k9s/blob/master/jumps/karpenter.yaml), which jumps to Nodes instead.
