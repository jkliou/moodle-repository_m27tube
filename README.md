# Youtube (v3) repository plugin for Moodle 2.7 (m27tube)

Recently some old [APIs were shutdown by Google](https://support.google.com/youtube/answer/6098135?p=yt_devicesupport&hl=en&rd=1), that caused the Youtube APIs used by Moodle to stop working.

While recent versions of Moodle (2.8 and up) [were adapted](https://tracker.moodle.org/browse/MDL-50176) to work with the new Youtube, it was technically difficult and unsafe to backport that change to Moodle 2.7.

This plugin, **m27tube**, workarounds the problem by embedding the new Google libraries within the plugin, making it 100% self-contained and avoiding the use of the google libraries (outdated) available in core.

The plugin was built by:
- Copying the current Moodle 2.8 plugin and renaming it to `m27tube`.
- Copying the current Moodle 2.8 google libraries within the `m27tube` plugin.
- Replacing nearly every `youtube` occurrence within the plugin to `m27tube`.
- Changing various includes, both in the plugin and in the google libraries to point to their new place within the plugin.

And that's all, just a bit of dark hacking with an apparently successful result.

## Installation instructions

- Manually:
  - [Download](https://github.com/stronk7/moodle-repository_m27tube/releases/latest) the plugin, uncompress it and rename the main folder to `m27tube`.
  - Copy the `m27tube` folder under the `repository` folder of your site.
- Using git:
  - Clone this repository in the `repository/m27tube` folder of your site.
- Visit the `admin/index.php` page, an upgrade should happen, with the repository being installed and enabled by default.
- Go to the plugin settings page and follow the instructions to set the, now required, **Google API**.
- Try it!

## Notes

- This plugin should be only used as an interim replacement for Moodle 2.7. It's highly advisable to upgrade to more recent, fully supported versions ASAP.
- This plugin is given as is, without any support neither guarantee and all the typical safeguard paraphernalia, be warned.
- All the authorships and credits of the original authors has been kept. Yay for them.
- I'd love to declare this distributed under the 3-Clause BSD license but I'm afraid, this is GPL v3.

## Bonus

- It seems that the plugin is also working under Moodle 2.6, but please, please, please... consider upgrading ASAP. It's really unsecure to run fully unsupported versions. At very least jump to the LTS (long term support) guard's van.

Enjoy, ciao, stronk7 :-)
