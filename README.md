# DND 5e API Wrapper in PHP

[![Latest Version on Packagist](https://img.shields.io/packagist/v/darkgoldblade01/dnd-5e-api.svg?style=flat-square)](https://packagist.org/packages/darkgoldblade01/dnd-5e-api)
[![Build Status](https://img.shields.io/travis/com/darkgoldblade01/dnd-5e-api-php/master.svg?style=flat-square)](https://travis-ci.com/darkgoldblade01/dnd-5e-api-php)
[![Quality Score](https://img.shields.io/scrutinizer/g/darkgoldblade01/dnd-5e-api-php.svg?style=flat-square)](https://scrutinizer-ci.com/g/darkgoldblade01/dnd-5e-api-php)
[![Total Downloads](https://img.shields.io/packagist/dt/darkgoldblade01/dnd-5e-api-php.svg?style=flat-square)](https://packagist.org/packages/darkgoldblade01/dnd-5e-api-php)

This package is a PHP wrapper for the [DND5eAPI](https://www.dnd5eapi.co/).

## Installation

You can install the package via composer:

```bash
composer require darkgoldblade01/dnd-5e-api
```

## Usage

``` php
use Darkgoldblade01\Dnd5eApi;

$api = new Dnd5eApi();

// Get Ability Scores API
$ability_scores_api = $api->ability_scores();

// Get Skills
$skills_api = $api->skills();

// Get Proficiences
$proficiencies_api = $api->proficiencies();

// You can get all items under an api
// This returns an array with all the ability scores in the AbilityScores Models
$ability_scores_api->all();

// Returns the AbilityScore Model based on the index
$ability_scores_api->{ability_score_index}();
//For instance:
$ability_scores_api->cha(); // Returns the Charisma AbilityScores Model
        
```

### Testing

``` bash
composer test
```

### Changelog

Please see [CHANGELOG](CHANGELOG.md) for more information what has changed recently.

## Contributing

Please see [CONTRIBUTING](CONTRIBUTING.md) for details.

### Security

If you discover any security related issues, please use the issue tracker.

## Credits

- [Brian Logan](https://github.com/darkgoldblade01)
- [All Contributors](../../contributors)

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.

---

## 🛠️ Technologische Stack

- **PHP 8.5+** — PSR-17 HTTP client, Guzzle
- **Composer** — afhankelijkheidsbeheer
- **PHPUnit** — unit tests (8 test suites: AbilityScores, Classes, Languages, Proficiencies, Skills, SubClasses, Model)
- **DND5eAPI.co** — externe API voor D&D 5e gegevens

## 🎥 Gource Visualization

De ontwikkelhistorie van dit project in een film:

<video src="https://raw.githubusercontent.com/itsdarklikehell/dnd-5e-api-php/master/gource.mp4" controls width="100%"></video>

*De video wordt automatisch gegenereerd door de [Gource workflow](.github/workflows/gource.yml) bij elke push — rendered via [nbprojekt/gource-action@v1.3.0](https://github.com/marketplace/actions/gource-action) in 1080p.*

Lokaal render (vereist Gource + ffmpeg):

```bash
gource --max-files 1500 --key -1920x1080 \
  --highlight-users --filename-time 3 --output-framerate 30 \
  --stop-at-end --auto-skip-seconds 0.1 --multi-sampling \
  --seconds-per-day 0.4 -o gource.ppm

ffmpeg -y -r 30 -f image2pipe -vcodec ppm -i gource.ppm \
  -c:v libx264 -preset medium -pix_fmt yuv420p \
  -c:a aac -b:a 192k gource.mp4
```