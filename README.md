# [WIP] Laravel Viewi
## This is just a proof-of-concept. Don't use it in production!

[![Latest Version on Packagist](https://img.shields.io/packagist/v/protonemedia/laravel-viewi.svg?style=flat-square)](https://packagist.org/packages/protonemedia/laravel-viewi)
[![GitHub Tests Action Status](https://img.shields.io/github/workflow/status/protonemedia/laravel-viewi/run-tests?label=tests)](https://github.com/protonemedia/laravel-viewi/actions?query=workflow%3Arun-tests+branch%3Amain)
[![GitHub Code Style Action Status](https://img.shields.io/github/workflow/status/protonemedia/laravel-viewi/Check%20&%20fix%20styling?label=code%20style)](https://github.com/protonemedia/laravel-viewi/actions?query=workflow%3A"Check+%26+fix+styling"+branch%3Amain)
[![Total Downloads](https://img.shields.io/packagist/dt/protonemedia/laravel-viewi.svg?style=flat-square)](https://packagist.org/packages/protonemedia/laravel-viewi)

[Viewi](https://viewi.net) for Laravel: Build full-stack and completely reactive user interfaces with PHP.

* Already familiar HTML.
* PHP dynamic data state.
* Efficient SSR/CSR.
* SEO friendly.
* No HTML over "the wire".
* The same code for server and front-end sides.
* Speed up your development process.
* Turn your components into highly-optimized JavaScript code.
* Build mobile and desktop applications (Planned).

## Launcher 🚀

Hey! We've built a Docker-based deployment tool to launch apps and sites fully containerized. You can find all features and the roadmap on our [website](https://uselauncher.com), and we are on [Twitter](https://twitter.com/uselauncher) as well!

## Support

We proudly support the community by developing Laravel packages and giving them away for free. Keeping track of issues and pull requests takes time, but we're happy to help! If this package saves you time or if you're relying on it professionally, please consider [supporting the maintenance and development](https://github.com/sponsors/pascalbaljet).

## Installation

You can install the package via composer:

```bash
composer require protonemedia/laravel-viewi
```

Install the example components and routes:

```bash
php artisan viewi:install
```

Add the `ViewiMiddleware` to the `web` group:

```php
class Kernel extends HttpKernel
{
    protected $middlewareGroups = [
        'web' => [
            \ProtoneMedia\LaravelViewi\Middleware\ViewiMiddleware::class,
            ...
        ],
    ];
}
```

Optionally, you can publish the config file with:

```bash
php artisan vendor:publish --tag="viewi-config"
```

## Usage

Add Viewi components as regular Laravel routes, for example, in `web.php`:

```php
use App\Components\Views\Home\HomePage;
use App\Components\Views\NotFound\NotFoundPage;
use App\Components\Views\Pages\TodoAppPage;
use Illuminate\Support\Facades\Route;

Route::get('/', HomePage::class);
Route::get('/todo', TodoAppPage::class);
Route::get('*', NotFoundPage::class);
```

Clear the build and public assets:

```bash
php artisan viewi:clear
```

## Changelog

Please see [CHANGELOG](CHANGELOG.md) for more information about what has changed recently.

## Testing

```bash
$ composer test
```

## Contributing

Please see [CONTRIBUTING](CONTRIBUTING.md) for details.

## Other Laravel packages

* [`Laravel Analytics Event Tracking`](https://github.com/protonemedia/laravel-analytics-event-tracking): Laravel package to easily send events to Google Analytics.
* [`Laravel Blade On Demand`](https://github.com/protonemedia/laravel-blade-on-demand): Laravel package to compile Blade templates in memory.
* [`Laravel Cross Eloquent Search`](https://github.com/protonemedia/laravel-cross-eloquent-search): Laravel package to search through multiple Eloquent models.
* [`Laravel Eloquent Scope as Select`](https://github.com/protonemedia/laravel-eloquent-scope-as-select): Stop duplicating your Eloquent query scopes and constraints in PHP. This package lets you re-use your query scopes and constraints by adding them as a subquery.
* [`Laravel Eloquent Where Not`](https://github.com/protonemedia/laravel-eloquent-where-not): This Laravel package allows you to flip/invert an Eloquent scope, or really any query constraint.
* * [`Laravel FFMpeg`](https://github.com/protonemedia/laravel-ffmpeg): This package provides an integration with FFmpeg for Laravel. The storage of the files is handled by Laravel's Filesystem.
* [`Laravel Form Components`](https://github.com/protonemedia/laravel-form-components): Blade components to rapidly build forms with Tailwind CSS Custom Forms and Bootstrap 4. Supports validation, model binding, default values, translations, includes default vendor styling and fully customizable!
* [`Laravel Mixins`](https://github.com/protonemedia/laravel-mixins): A collection of Laravel goodies.
* [`Laravel Paddle`](https://github.com/protonemedia/laravel-paddle): Paddle.com API integration for Laravel with support for webhooks/events.
* [`Laravel Verify New Email`](https://github.com/protonemedia/laravel-verify-new-email): This package adds support for verifying new email addresses: when a user updates its email address, it won't replace the old one until the new one is verified.
* [`Laravel WebDAV`](https://github.com/protonemedia/laravel-webdav): WebDAV driver for Laravel's Filesystem.

## Security

If you discover any security-related issues, please email code@protone.media instead of using the issue tracker. Please do not email any questions, open an issue if you have a question.

## Credits

- [Pascal Baljet](https://github.com/pascalbaljet)
- [All Contributors](../../contributors)

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.
