# Ansible MongoDB Role

An ansible role for installing and managing MongoDB's.


## Configuration:


## Dependencies

None.


## Example Playbook

    ---
    - hosts: mongo-cluster-*
      remote_user: root
    
      roles:
      - sontags.mongodb
    
      pre_tasks:
      - name: get mongo_group_name
        set_fact: mongo_group_name="{{ item }}" 
        with_items: group_names
        when: item | search("mongo-cluster-*")
    
      - name: get mongo_replica_set
        set_fact: mongo_replica_set="{{ mongo_group_name  }}" 
        when: mongo_replica_set is not defined

## License

MIT


## Author Information

Daniel Menet
