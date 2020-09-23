# Conda - Package, dependency and environment management for any language

https://docs.conda.io/en/latest/

## Working with Environments

### Deactivate Activation of base Environment on Terminal Startup

```conda config --set auto_activate_base false```

### Manual Activation/Deactivation of an Environment

* ```conda activate myenv```
* ```conda deactivate```

### Creating an Environment

Create an environment:  
```conda create --name myenv```

Create an environment with a specific version of Python:  
```conda create -n myenv python=3.6```

### Viewing a list of all Environments

```conda env list```

### Viewing a list of the packages in an Environment

If the environment is not activated:  
```conda list -n myenv```

If the environment is activated:  
```conda list```


## Resources

* https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html
