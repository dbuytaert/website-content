---
title: 'Extended security coverage for Drupal 8 minor releases'
date: '2018-09-13T02:50:45-04:00'
author: Dries
summary: 'Drupal 8 site owners now have six months to upgrade between minor releases instead of one month'
image: drupal/new-drupal-8-security-policy-for-minor-releases
tags:
  - Drupal
  - Security
published: true
type: blog
url: /extended-security-coverage-for-drupal-8-minor-releases
id: 4516
---

Since the launch of Drupal 8.0, we have successfully launched a new minor release on schedule every six months. I'm very proud of the community for this achievement. Prior to Drupal 8, most significant new features were only added in *major releases* like Drupal 6 or Drupal 7. Thanks to our new release cadence we now consistently and predictably ship great new features twice a year in *minor releases* (e.g. [Drupal 8.6 comes with many new features](https://dri.es/drupal-8-6-0-released)).

However, only the most recent minor release has been actively supported for both bug fixes and security coverage. With the release of each new minor version, we gave a one-month window to upgrade to the new minor. In order to give site owners time to upgrade, we would not disclose security issues with the previous minor release during that one-month window.

[image drupal/old-drupal-8-security-policy-for-minor-releases resize=false]

Over the past three years, we have learned that users find it challenging to update to the latest minor in one month. Drupal's minor updates can include dependency updates, internal API changes, or features being transitioned from contributed modules to core. It takes time for site owners to prepare and test these types of changes, and a window of one month to upgrade isn't always enough.

At DrupalCon Nashville [we declared that we wanted to extend security coverage for minor releases](https://dri.es/state-of-drupal-presentation-april-2018). Throughout 2018, Drupal 8 release managers quietly conducted a trial. You may have noticed that we had several security releases against previous minor releases this year. This trial helped us understand the impact to the release process and learn what additional work remained ahead. You can read about the results of the trial at [\#2909665: Extend security support to cover the previous minor version of Drupal](https://www.drupal.org/project/drupal/issues/2909665#phase-three).

I'm pleased to share that the trial was a success! As a result, we have extended the security coverage of minor releases to six months. Instead of one month, site owners now have six months to upgrade between minor releases. It gives teams time to plan, prepare and test updates. Releases will have six months of normal bug fix support followed by six months of security coverage, for a total lifetime of one year. This is a huge win for Drupal site owners.

[image drupal/new-drupal-8-security-policy-for-minor-releases resize=false]

It's important to note that this new policy only applies to Drupal 8 core starting with Drupal 8.5, and only applies to security issues. Non-security bug fixes will still only be committed to the actively supported release.

While the new policy will provide extended security coverage for Drupal 8.5.x, site owners will need to update to an upcoming release of Drupal 8.5 to be correctly notified about their security coverage.

### Next steps

We still have some user experience issues we'd like to address around how site owners are alerted of a security update. We have not yet handled all of the potential edge cases, and we want to be very clear about the potential actions to take when updating.

We also know module developers may need to declare that a release of their project only works against specific versions of Drupal core. Resolving outstanding issues around [semantic versioning support for contrib](https://www.drupal.org/project/drupal/issues/2313917) and [module version dependency definitions](https://www.drupal.org/project/drupal/issues/2641658) will help developers of contributed projects better support this policy. If you'd like to get involved in the remaining work, the [policy and roadmap issue on Drupal.org](https://www.drupal.org/project/drupal/issues/2909665) is a great place to find related issues and see what work is remaining.

*Special thanks to [Jess](https://www.drupal.org/u/xjm) and [Jeff Beeman](https://www.drupal.org/u/jrbeeman) for co-authoring this post.*
