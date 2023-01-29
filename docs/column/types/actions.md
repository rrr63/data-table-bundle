# ActionsType

The [ActionsType](../../../src/Column/Type/ActionsType.php) represents a column with value displayed as a list of actions.

## Options

### `actions`

**type**: `array` **default**: `[]`

This option contains a list of actions. Each actions consists of two options:

- `template_path` (**type**: `string`) - path to the template that represents the action;
- `template_vars` (**type**: `array`, **default**: `[]`) - variables used within the template;

The following action templates are natively available in the bundle:

- `@KreyuDataTable\Action\action_link_button.html.twig`

Example usage:

```php
$columns
    ->add('actions', ActionsType::class, [
        'actions' => [
            'show' => [
                'template_path' => '@KreyuDataTable\Action\action_link_button.html.twig',
                'template_vars' => [
                    'label' => t('Details'),
                    'url' => function (Product $product): string {
                        return $this->urlGenerator->generate('category_show', [
                            'id' => $product->getId(),
                        ]);
                    }),
                ],
            ],
        ],
    ])
;
```

## Inherited options

See [abstract column type documentation](abstract.md).

## Overridden options

### `display_personalization_button`

**type**: `bool` **default**: `true`