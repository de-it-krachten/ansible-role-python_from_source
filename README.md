[![CI](https://github.com/de-it-krachten/ansible-role-python_from_source/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-python_from_source/actions?query=workflow%3ACI)


# ansible-role-python_from_source

Compile python from source

Platforms
--------------

Supported platforms

- Red Hat Enterprise Linux 7<sup>1</sup>
- Red Hat Enterprise Linux 8<sup>1</sup>
- CentOS 7
- RockyLinux 8
- AlmaLinux 8<sup>1</sup>
- Debian 10 (Buster)
- Debian 11 (Bullseye)
- Ubuntu 18.04 LTS
- Ubuntu 20.04 LTS

Note:
<sup>1</sup> : no automated testing is performed on these platforms

Role Variables
--------------
<pre><code>
# Python version to compile
python_version: 3.8.12

# Python minor version
python_version_minor: "{{ python_version | regex_replace('^(\\d\\.\\d)(.*)', '\\1') }}"

# Python exectable
python_binary: python{{ python_version_minor }}

# Python exectable (full path)
python_binary_full: /usr/local/bin/{{ python_binary }}

# Download url of the source code
python_url: https://www.python.org/ftp/python/{{ python_version }}/Python-{{ python_version }}.tgz
</pre></code>


Example Playbook
----------------

<pre><code>
- name: sample playbook for role 'python_from_source'
  hosts: all
  vars:
  tasks:
    - name: Include role 'python_from_source'
      include_role:
        name: python_from_source
</pre></code>
