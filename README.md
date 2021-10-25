## Instalation

`composer create-project laravel/laravel crudVue`
`composer require laravel/breeze`
`php artisan breeze:install`
`php artisan migrate --seed`
`npm install && npm run dev`


## Dev
`php artisan make:model Company -m`
`php artisan make:controller Api/CompanyController --api --resource --model=Company`
`php artisan make:resource CompanyResource`
`php artisan make:request CompanyRequest`
`mac$ php artisan migrate`