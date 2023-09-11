# Upgrade Patches

This package provides two versions to help with patch selection in case where a module needs to 
be patched for compatibility with Open Social and the patch does not apply to versions that 
support both Drupal 9 and Drupal 10.

This package should not be applied outside of `goalgorilla/open_social` and will be abandoned 
once Open Social drops support for Drupal 9.

## Adding patches
Patches should only be added in case adding them directly to `goalgorilla/open_social` provides 
an issue with backwards incompatibility (for example because a 1.x version of a module only 
supports Drupal 9, and 2.x only supports Drupal 10, but a patch does not apply to both 1.x and 2.x).

Make changes for Drupal 9 in the 1.x branch of this package, and changes for Drupal 10 on the 2.x 
branch of this module.

Even when adding a patch to only one of the two branches, you _MUST_ add the module to the 
`require` key of the `composer.json` in _BOTH_ branches to ensure composer selects the right 
version of this package when resolving dependencies.

You _MUST_ add a dependency on a module with as wide a version range as possible (i.e. `^1` and 
not `1.0.1`), specific version requirements should be managed from the downstream 
`goalgorilla/open_social` package.
