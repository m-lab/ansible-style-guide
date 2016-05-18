# ansible-style-guide

## Objective

This style guide is designed to ensure consistent style and practices across
M-Lab's Ansible playbooks and associated Ansible files.

## Style Guide Additions / Changes

To propose an addition or change to the style guide:

1. File [a new issue](https://github.com/m-lab/ansible-style-guide/issues/new)
1. Give the other M-Lab Ansible developers a few days to reach agreement.
1. Make a pull request to implement the agreed upon change.

## Style Guide Style

This style guide is modeled after Google Style guides, for example:

 * [Google Python Style Guide](https://google.github.io/styleguide/pyguide.html)
 * [Google JavaScript Style Guide](https://google.github.io/styleguide/javascriptguide.xml)

In particular, style decisions should include both a clear explanation of the
style choice and the rationale for the decision.

## Relationship to Ansible Playbook Best Practices

This style guide is an extension of the [Ansible Playbook Best
Practices](http://docs.ansible.com/ansible/playbooks_best_practices.html). If
contradictions arise between the two documents, the Playbook Best Practices take
priority and this style guide should be modified to eliminate the contradiction.

## Ansible Language Rules

### One parameter per line

#### Decision

Use line breaks and indentation to separate parameters to Ansible modules, for
example:

```yaml
# Correct
- name: create foo temp directory
  file: path=/tmp/foo
        state=directory
        owner=bar
        group=fooers

# WRONG
- name: create foo temp directory
  file: path=/tmp/foo
        state=directory owner=bar group=fooers # WRONG: multiple params on line
```

#### Pros

* One parameter per line is a simple rule to follow globally

#### Cons

* Takes up more vertical space in the file
* Not as easy to express tight grouping among related parameters (e.g. `owner`,
  `group`, `mode` for several modules)
