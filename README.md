# Filament Select Tree

[![Latest Version on Packagist](https://img.shields.io/packagist/v/codewithdennis/filament-select-tree.svg?style=flat-square)](https://packagist.org/packages/codewithdennis/filament-select-tree)
[![Total Downloads](https://img.shields.io/packagist/dt/codewithdennis/filament-select-tree.svg?style=flat-square)](https://packagist.org/packages/codewithdennis/filament-select-tree)

The multi-level select field lets you pick one option at a time from a list that's neatly organized into different levels. It's all made possible with [TreeSelectJS](https://github.com/dipson88/treeselectjs).

## Installation

You can install the package via composer:

```bash
composer require codewithdennis/filament-select-tree
```

## Usage

At the moment, it only works with fields that accept single values.

```PHP
use CodeWithDennis\FilamentSelectTree\SelectTree;
use App\Models\Category;

SelectTree::make('category_id')
    // It uses the Category model to build a select tree with 'category_id' as the parent column and 'name' as the node label.
    ->tree(Category::class, 'category_id', 'name')

    // Here, the label 'Category' is assigned to the field.
    ->label(__('Category'))

    // By calling this function, it ensures that only leaf nodes can be selected while preventing the selection of groups.
    ->disabledBranchNode()

    // Enabling this feature will show the count of children alongside the group's name.
    ->withCount()

    // By calling this function, it activates the search functionality for the SelectTree.
    ->searchable()

    // Using this function, the SelectTree is disabled. (You can also use: ->disabledOn(''))
    ->disabled(),
```
## Screenshot

![select-tree-example](https://github.com/CodeWithDennis/filament-select-tree/assets/23448484/688713ae-015e-416c-a2c2-b3e6e049a74d)

## Changelog

Please see [CHANGELOG](CHANGELOG.md) for more information on what has changed recently.

## Contributing

Please see [CONTRIBUTING](.github/CONTRIBUTING.md) for details.

## Security Vulnerabilities

Please review [our security policy](../../security/policy) on how to report security vulnerabilities.

## Credits

- [CodeWithDennis](https://github.com/CodeWithDennis)
- [Dipson88](https://github.com/dipson88/treeselectjs)
- [All Contributors](../../contributors)

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.
