# Policyfile Repo Generator

The purpose of this project is to act as a custom chef cookbook generator for generating not just a policyfile, but all the additional accoutrements needed for testing a policy in a pipeline, as well as files wanted for making the result a well-rounded repository (README, CHANGELOG, and LICENSE files).

## To use the generator

For lack of a better name to use, when generating a policyfile repo, this custom generator triggers off the cookbook generator, so when using this as the source, your generate command would look like:

```bash
chef generate cookbook policies/my_policy -g generators/policyfile_repo_generator
```

This will give you a subdirectory in your policies folder for this specific policyfile repo.

```text
policies/my_policy
├── CHANGELOG.md
├── LICENSE
├── README.md
├── chefignore
├── kitchen.yml
├── my_policy.rb
└── test
    └── integration
        └── default
            └── default_test.rb
```

The policyfile name will have the same name as the "cookbook" name given when you use the generator.  In this case, `my_policy.rb`
