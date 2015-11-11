# rolling_rollout
The playbook performs rollout in rolling manner.

## Examples

```yaml
---
- hosts: webservers
  remote_user: root
  serial: 1
  vars:
    rollout_script: </path/to/user_rollout_script>
    rollout_user: <rollout_user>
  vars_prompt:
    - name: "rollout_branch"
      prompt: "Enter branch name (default:master) ?"
      default: "master"
      private: no
  roles:
    - { role: rollout, tags: [ "rollout" ] }
```
