# BackpackPermissionManager Extension

[![Latest Version on Packagist][ico-version]][link-packagist]
[![Total Downloads][ico-downloads]][link-downloads]
[![The Whole Fruit Manifesto](https://img.shields.io/badge/writing%20standard-the%20whole%20fruit-brightgreen)](https://github.com/the-whole-fruit/manifesto)

This package override the [Backpack PermissionManager](https://github.com/Laravel-Backpack/PermissionManager) and display the checklist field role and permissions into groups. 

## Screenshots
![Backpack Permission Manager Extension](https://github.com/user-attachments/assets/8f7c74e9-134b-4394-ba2a-fef8b51716fd)


## Installation

Via Composer

``` bash
composer require winex01/backpack-permission-manager
```

## Usage
how does it worked, im using the role_permission convention
```
'admin' => [
  'admin_view',
  'admin_trashed_filter', 
  'admin_debugbar', 
  'admin_web_tinker', 
  'admin_notify_newly_registered',
  'admin_notify_newly_created_manga',
  'admin_proxy_notice',
  'admin_telescope',
  'admin_widgets',
  'admin_received_contact_us',
  'admin_reply_contact_us',
]

'audit_trails' => [
  'audit_trails_list',
  'audit_trails_show', 
  'audit_trails_delete',
  'audit_trails_bulk_delete',
  'audit_trails_export',
  'audit_trails_restore_revise',
  'audit_trails_bulk_restore_revise', 
]
```

Restrict user without permissions:
```php
//EntityCrudController.php
public function setup()
{
    // some hode here..
    
    $this->userPermission('users'); // Optional parameter with a default value of current model tables name.

    // if you follow roleName_permissionName and use the table's name as your roleName then you can leave it empty.
    $this->userPermissions();

    // calling $this->userPermissions method is equivalent:
    $this->checkAccess('users');
    $this->checkAccess('admin');

    // you can either use userPermissions or the checkAccess method.
}

```
Although above methods are called role and roles method it just checking if you have permission that starts with users or secret_process, that's why i recommend you to use the convention roleName_permissionName, like: users_list, users_create and etc..

Uninstall this package. 
```bash
composer remove winex01/backpack-permission-manager
```

## Change log

Changes are documented here on Github. Please see the [Releases tab](https://github.com/winex01/backpack-permission-manager/releases).

## Testing

``` bash
composer test
```

## Contributing

Please see [contributing.md](contributing.md) for a todolist and howtos.

## Security

If you discover any security related issues, please email winnie131212592@gmail.com instead of using the issue tracker.

## Credits

- [Winnie A. Damayo][link-author]
- [All Contributors][link-contributors]

## License

This project was released under MIT, so you can install it on top of any Backpack & Laravel project. Please see the [license file](license.md) for more information. 

However, please note that you do need Backpack installed, so you need to also abide by its [YUMMY License](https://github.com/Laravel-Backpack/CRUD/blob/master/LICENSE.md). That means in production you'll need a Backpack license code. You can get a free one for non-commercial use (or a paid one for commercial use) on [backpackforlaravel.com](https://backpackforlaravel.com).


[ico-version]: https://img.shields.io/packagist/v/winex01/backpack-permission-manager.svg?style=flat-square
[ico-downloads]: https://img.shields.io/packagist/dt/winex01/backpack-permission-manager.svg?style=flat-square

[link-packagist]: https://packagist.org/packages/winex01/backpack-permission-manager
[link-downloads]: https://packagist.org/packages/winex01/backpack-permission-manager
[link-author]: https://github.com/winex01
[link-contributors]: ../../contributors
