---
layout: docs
title: History
permalink: /history/
authors:
  - Jack R. Dunaway
editors:
  - placeholder
---

## 2.5.3 / 2014-12-22
{: #v2-5-3}

### Bug Fixes
{: #bug-fixes-v2-5-3}

- When checking a Markdown extname, include position of the `.` ([#3147]({{ site.repository }}/issues/3147))
- Fix `jsonify` Liquid filter handling of boolean values ([#3154]({{ site.repository }}/issues/3154))
- Add comma to value of `viewport` meta tag ([#3170]({{ site.repository }}/issues/3170))
- Set the link type for the RSS feed to `application/rss+xml` ([#3176]({{ site.repository }}/issues/3176))
- Refactor `#as_liquid` ([#3158]({{ site.repository }}/issues/3158))

### Development Fixes
{: #development-fixes-v2-5-3}

- Exclude built-in bundles from being added to coverage report ([#3180]({{ site.repository }}/issues/3180))

### Site Enhancements
{: #site-enhancements-v2-5-3}

- Add `[@alfredxing](https://github.com/alfredxing)` to the `[@jekyll](https://github.com/jekyll)/core` team. :tada: ([#3218]({{ site.repository }}/issues/3218))
- Document the `-q` option for the `build` and `serve` commands ([#3149]({{ site.repository }}/issues/3149))
- Fix some minor typos/flow fixes in documentation website content ([#3165]({{ site.repository }}/issues/3165))
- Add `keep_files` to configuration documentation ([#3162]({{ site.repository }}/issues/3162))
- Repeat warning about cleaning of the `destination` directory ([#3161]({{ site.repository }}/issues/3161))
- Add jekyll-500px-embed to list of third-party plugins ([#3163]({{ site.repository }}/issues/3163))
- Simplified platform detection in Gemfile example for Windows ([#3177]({{ site.repository }}/issues/3177))
- Add the `jekyll-jalali` plugin added to the list of third-party plugins. ([#3198]({{ site.repository }}/issues/3198))
- Add Table of Contents to Troubleshooting page ([#3196]({{ site.repository }}/issues/3196))
- Add `inline_highlight` plugin to list of third-party plugins ([#3212]({{ site.repository }}/issues/3212))
- Add `jekyll-mermaid` plugin to list of third-party plugins ([#3222]({{ site.repository }}/issues/3222))


## 2.5.2 / 2014-11-17
{: #v2-5-2}

### Minor Enhancements
{: #minor-enhancements-v2-5-2}

- `post_url` should match `post.name` instead of slugs and dates ([#3058]({{ site.repository }}/issues/3058))

### Bug Fixes
{: #bug-fixes-v2-5-2}

- Fix bundle require for `:jekyll_plugins` ([#3119]({{ site.repository }}/issues/3119))
- Remove duplicate regexp phrase: `^\A` ([#3089]({{ site.repository }}/issues/3089))
- Remove duplicate `Conversion error:` message in `Convertible` ([#3088]({{ site.repository }}/issues/3088))
- Print full conversion error message in `Renderer#convert` ([#3090]({{ site.repository }}/issues/3090))

### Site Enhancements
{: #site-enhancements-v2-5-2}

- Change variable names in Google Analytics script ([#3093]({{ site.repository }}/issues/3093))
- Mention CSV files in the docs for data files ([#3101]({{ site.repository }}/issues/3101))
- Add trailing slash to `paginate_path` example. ([#3091]({{ site.repository }}/issues/3091))
- Get rid of noifniof (`excerpt_separator`) ([#3094]({{ site.repository }}/issues/3094))
- Sass improvements, around nesting mostly. ([#3123]({{ site.repository }}/issues/3123))
- Add webmentions.io plugin to the list of third-party plugins ([#3127]({{ site.repository }}/issues/3127))
- Add Sass mixins and use them. ([#2904]({{ site.repository }}/issues/2904))
- Slightly compress jekyll-sticker.jpg. ([#3133]({{ site.repository }}/issues/3133))
- Update gridism and separate out related but custom styles. ([#3132]({{ site.repository }}/issues/3132))
- Add remote-include plugin to list of third-party plugins ([#3136]({{ site.repository }}/issues/3136))


## 2.5.1 / 2014-11-09
{: #v2-5-1}

### Bug Fixes
{: #bug-fixes-v2-5-1}

- Fix path sanitation bug related to Windows drive names ([#3077]({{ site.repository }}/issues/3077))

### Development Fixes
{: #development-fixes-v2-5-1}

- Add development time dependencies on minitest and test-unit to gemspec for cygwin ([#3064]({{ site.repository }}/issues/3064))
- Use Travis's built-in caching. ([#3075]({{ site.repository }}/issues/3075))


## 2.5.0 / 2014-11-06
{: #v2-5-0}

### Minor Enhancements
{: #minor-enhancements-v2-5-0}

- Require gems in `:jekyll_plugins` Gemfile group unless `JEKYLL_NO_BUNDLER_REQUIRE` is specified in the environment. ([#2865]({{ site.repository }}/issues/2865))
- Centralize path sanitation in the `Site` object ([#2882]({{ site.repository }}/issues/2882))
- Allow placeholders in permalinks ([#3031]({{ site.repository }}/issues/3031))
- Allow users to specify the log level via `JEKYLL_LOG_LEVEL`. ([#3067]({{ site.repository }}/issues/3067))
- Fancy Indexing with WEBrick ([#3018]({{ site.repository }}/issues/3018))
- Allow Enumerables to be used with `where` filter. ([#2986]({{ site.repository }}/issues/2986))
- Meta descriptions in the site template now use `page.excerpt` if it's available ([#2964]({{ site.repository }}/issues/2964))
- Change indentation in `head.html` of site template to 2 spaces from 4 ([#2973]({{ site.repository }}/issues/2973))
- Use a `$content-width` variable instead of a fixed value in the site template CSS ([#2972]({{ site.repository }}/issues/2972))
- Strip newlines in site template `<meta>` description. ([#2982]({{ site.repository }}/issues/2982))
- Add link to atom feed in `head` of site template files ([#2996]({{ site.repository }}/issues/2996))
- Performance optimizations ([#2994]({{ site.repository }}/issues/2994))
- Use `Hash#each_key` instead of `Hash#keys.each` to speed up iteration
    over hash keys. ([#3017]({{ site.repository }}/issues/3017))
- Further minor performance enhancements. ([#3022]({{ site.repository }}/issues/3022))
- Add 'b' and 's' aliases for build and serve, respectively ([#3065]({{ site.repository }}/issues/3065))

### Bug Fixes
{: #bug-fixes-v2-5-0}

- Fix Rouge's RedCarpet plugin interface integration ([#2951]({{ site.repository }}/issues/2951))
- Remove `--watch` from the site template blog post since it defaults
    to watching in in 2.4.0 ([#2922]({{ site.repository }}/issues/2922))
- Fix code for media query mixin in site template ([#2946]({{ site.repository }}/issues/2946))
- Allow post URL's to have `.htm` extensions ([#2925]({{ site.repository }}/issues/2925))
- `Utils.slugify`: Don't create new objects when gsubbing ([#2997]({{ site.repository }}/issues/2997))
- The jsonify filter should deep-convert to Liquid when given an Array. ([#3032]({{ site.repository }}/issues/3032))
- Apply `jsonify` filter to Hashes deeply and effectively ([#3063]({{ site.repository }}/issues/3063))
- Use `127.0.0.1` as default host instead of `0.0.0.0` ([#3053]({{ site.repository }}/issues/3053))
- In the case that a Gemfile does not exist, ensure Jekyll doesn't fail on requiring the Gemfile group ([#3066]({{ site.repository }}/issues/3066))

### Development Fixes
{: #development-fixes-v2-5-0}

- Fix a typo in the doc block for `Jekyll::URL.escape_path` ([#3052]({{ site.repository }}/issues/3052))
- Add integration test for `jekyll new --blank` in TestUnit ([#2913]({{ site.repository }}/issues/2913))
- Add unit test for `jekyll new --force` logic ([#2929]({{ site.repository }}/issues/2929))
- Update outdated comment for `Convertible#transform` ([#2957]({{ site.repository }}/issues/2957))
- Add Hakiri badge to README. ([#2953]({{ site.repository }}/issues/2953))
- Add some simple benchmarking tools. ([#2993]({{ site.repository }}/issues/2993))

### Site Enhancements
{: #site-enhancements-v2-5-0}

- `NOKOGIRI_USE_SYSTEM_LIBRARIES=true` **decreases** installation time. ([#3040]({{ site.repository }}/issues/3040))
- Add FormKeep to resources as Jekyll form backend ([#3010]({{ site.repository }}/issues/3010))
- Fixing a mistake in the name of the new Liquid tag ([#2969]({{ site.repository }}/issues/2969))
- Update Font Awesome to v4.2.0. ([#2898]({{ site.repository }}/issues/2898))
- Fix link to [#2895]({{ site.repository }}/issues/2895) in 2.4.0 release post. ([#2899]({{ site.repository }}/issues/2899))
- Add Big Footnotes for Kramdown plugin to list of third-party plugins ([#2916]({{ site.repository }}/issues/2916))
- Remove warning regarding GHP use of singular types for front matter defaults ([#2919]({{ site.repository }}/issues/2919))
- Fix quote character typo in site documentation for templates ([#2917]({{ site.repository }}/issues/2917))
- Point Liquid links to Liquid’s Github wiki ([#2887]({{ site.repository }}/issues/2887))
- Add HTTP Basic Auth (.htaccess) plugin to list of third-party plugins ([#2931]({{ site.repository }}/issues/2931))
- (Minor) Grammar & `_config.yml` filename fixes ([#2911]({{ site.repository }}/issues/2911))
- Added `mathml.rb` to the list of third-party plugins. ([#2937]({{ site.repository }}/issues/2937))
- Add `--force_polling` to the list of configuration options ([#2943]({{ site.repository }}/issues/2943))
- Escape unicode characters in site CSS ([#2906]({{ site.repository }}/issues/2906))
- Add note about using the github-pages gem via pages.github.com/versions.json ([#2939]({{ site.repository }}/issues/2939))
- Update usage documentation to reflect 2.4 auto-enabling of `--watch`. ([#2954]({{ site.repository }}/issues/2954))
- Add `--skip-initial-build` to configuration docs ([#2949]({{ site.repository }}/issues/2949))
- Fix a minor typo in Templates docs page ([#2959]({{ site.repository }}/issues/2959))
- Add a ditaa-ditaa plugin under Other section on the Plugins page ([#2967]({{ site.repository }}/issues/2967))
- Add `build/serve -V` option to configuration documentation ([#2948]({{ site.repository }}/issues/2948))
- Add 'Jekyll Twitter Plugin' to list of third-party plugins ([#2979]({{ site.repository }}/issues/2979))
- Docs: Update normalize.css to v3.0.2. ([#2981]({{ site.repository }}/issues/2981))
- Fix typo in Continuous Integration documentation ([#2984]({{ site.repository }}/issues/2984))
- Clarify behavior of `:categories` in permalinks ([#3011]({{ site.repository }}/issues/3011))


## 2.4.0 / 2014-09-09
{: #v2-4-0}

### Minor Enhancements
{: #minor-enhancements-v2-4-0}

- Support a new `relative_include` tag ([#2870]({{ site.repository }}/issues/2870))
- Auto-enable watch on 'serve' ([#2858]({{ site.repository }}/issues/2858))
- Render Liquid in CoffeeScript files ([#2830]({{ site.repository }}/issues/2830))
- Array Liquid filters: `push`, `pop`, `unshift`, `shift` ([#2895]({{ site.repository }}/issues/2895))
- Add `:title` to collection URL template fillers ([#2864]({{ site.repository }}/issues/2864))
- Add support for CSV files in the `_data` directory ([#2761]({{ site.repository }}/issues/2761))
- Add the `name` variable to collection permalinks ([#2799]({{ site.repository }}/issues/2799))
- Add `inspect` liquid filter. ([#2867]({{ site.repository }}/issues/2867))
- Add a `slugify` Liquid filter ([#2880]({{ site.repository }}/issues/2880))

### Bug Fixes
{: #bug-fixes-v2-4-0}

- Use `Jekyll.sanitized_path` when adding static files to Collections ([#2849]({{ site.repository }}/issues/2849))
- Fix encoding of `main.scss` in site template ([#2771]({{ site.repository }}/issues/2771))
- Fix orientation bugs in default site template ([#2862]({{ site.repository }}/issues/2862))

### Development Fixes
{: #development-fixes-v2-4-0}

- Update simplecov gem to 0.9 ([#2748]({{ site.repository }}/issues/2748))
- Remove `docs/` dir ([#2768]({{ site.repository }}/issues/2768))
- add class `<< self` idiom to `New` command ([#2817]({{ site.repository }}/issues/2817))
- Allow Travis to 'parallelize' our tests ([#2859]({{ site.repository }}/issues/2859))
- Fix test for Liquid rendering in Sass ([#2856]({{ site.repository }}/issues/2856))
- Fixing "vertycal" typo in site template's `_base.scss` ([#2889]({{ site.repository }}/issues/2889))

### Site Enhancements
{: #site-enhancements-v2-4-0}

- Document the `name` variable for collection permalinks ([#2829]({{ site.repository }}/issues/2829))
- Adds info about installing jekyll in current dir ([#2839]({{ site.repository }}/issues/2839))
- Remove deprecated `jekyll-projectlist` plugin from list of third-party
    plugins ([#2742]({{ site.repository }}/issues/2742))
- Remove tag plugins that are built in to Jekyll ([#2751]({{ site.repository }}/issues/2751))
- Add `markdown-writer` package for Atom Editor to list of third-party
    plugins ([#2763]({{ site.repository }}/issues/2763))
- Fix typo in site documentation for collections ([#2764]({{ site.repository }}/issues/2764))
- Fix minor typo on plugins docs page ([#2765]({{ site.repository }}/issues/2765))
- Replace markdown with HTML in `sass_dir` note on assets page ([#2791]({{ site.repository }}/issues/2791))
- Fixed "bellow" typo in datafiles docs ([#2879]({{ site.repository }}/issues/2879))
- Fix code/markdown issue in documentation for variables ([#2877]({{ site.repository }}/issues/2877))
- Remove Good Include third-party plugin from plugins page ([#2881]({{ site.repository }}/issues/2881))
- Add some more docs on `include_relative` ([#2884]({{ site.repository }}/issues/2884))

## 0.0.0 / 2008-10-19
{: #v0-0-0}
- Birthday!
