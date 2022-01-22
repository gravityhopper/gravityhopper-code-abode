## Gravity Custom Code Keeper
Provides a reliable and consistent way to store and load custom form-related code on your site.

### How does it work?
Gravity Custom Code Keeper…
1. creates a directory at `wp-content/uploads/gravity_hopper/code/`.
1. adds a file loader as an `mu-plugin` on your site.
1. adds a file `gf-global-code.php` *(for housing globally run code)*.
1. optionally creates/duplicates/deletes a `gf-00xx.php` file for every form created/duplicated/deleted. *(for housing form-specific code)*
1. will load all files in the code directory which are prefixed with `gf-` and `gform-`.
1. allows exporting any number of code files to compressed .zip.
1. introduces a form settings page whereby you can preview relevant custom code and create a file if one doesn't yet exist.

**Please note that Gravity Custom Code Keeper is intended for code organization only and doesn't restrict when code is run.**
**All code residing in files prefixed with `gf-` or `gform-` in the `gravity_hopper/code/` directory will run for all forms.**
**Always use appropriate hooks and/or conditional checks when targeting specific forms and fields.**

Use the following filters to override default behavior file auto-generation/duplication/deletion.

```
add_filter( 'gravityhopper-cck/create_file', '__return_true' );
add_filter( 'gravityhopper-cck/duplicate_file', '__return_false' );
add_filter( 'gravityhopper-cck/remove_file', '__return_true' );
```

### Why use it?
Gravity Custom Code Keeper provides orderliness to your code customizations, gives you a better sense of the specific code running across your site, and helps ensure your customizations are not lost when other site modifications are made.

**Organization:** Our file-per-form framework for organizing your code helps you keep your code in a way that is easier to access, investigate, and update.

**Reliability:** Since code is initialized via an mu-plugin loader, your code is not dependant upon a specific theme or plugin being active on the site. The mu-plugin loader is retained when Code Abode is deactivated or removed from the site. Thus, the only dependency for your code is Gravity Forms itself running on the site.

**Preservation:** Having your code reside outside of a specific plugin or theme ensures it is not lost to theme updates or plugin deactivation.

**Troubleshoot:** The mu-plugin includes an option to quickly toggle the active state of your custom code. Be sure to deactivate your code when running conflict tests.

**Portability:** A form is often only as good as the code that stands behind it. Taking your form to another site? Code file exports make it easy to pull the code you need.

### Need more?
[Gravity Hopper](https://gravityhopper.com) offers an elite array of developer tools that integrates seamlessly with Gravity Forms, saving you time and effort with every form you build.