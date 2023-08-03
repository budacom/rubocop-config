# rubocop-config

This repo contains the Rubocop configurations used for all Rails applications in Buda.com. 
There is a `rubocop-base` file that contains all the main rules and configurations.
Then, there is a `rubocop-1-28` which is for applications that use a Ruby version <= 2.5, and Rubocop <= 1.28.
The default file `rubocop` is for applications with newer versions of Rubocop.

To use these configurations, in your local `.rubocop.yml` file you must inherit the configuration and overwrite with your projects Ruby version in the following way:
```yml
inherit_from:
  - https://raw.githubusercontent.com/budacom/rubocop-config/main/rubocop.yml

AllCops:
  TargetRubyVersion: 3.2
```

If your project needs the older configuration, you must change the last part `rubocop.yml` for `rubocop-1-28.yml`.

Also, add the following to your `.gitignore`:

```yml
# Rubocop
.rubocop-*
```

This will prevent you from committing the rubocop cache files.
