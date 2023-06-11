# portainer_shace_stack

 A .yml file for shace services

## Local development

1. Create stack.env file and put all environment variables there
2. `docker-compose up`

## Production

1. Go to Portainer
2. Go to stacks
3. Create a new github stack
4. put the url `https://github.com/shace-co/portainer_deets_stack` and `refs/heads/main`
5. Add your environment variables
6. Deploy
7. Voila

## Troubleshooting

1. Local directory /home/shace/storage needs `chown -R 1000:1000 .`
2. You might need laravel clean up commands

    ```bash
    docker exec shace-api-v2 php artisan clear:data
    docker exec shace-api-v2 php artisan cache:clear 
    docker exec shace-api-v2 php artisan view:clear 
    docker exec shace-api-v2 php artisan route:clear 
    docker exec shace-api-v2 php artisan clear-compiled 
    docker exec shace-api-v2 php artisan config:cache
    docker exec shace-api-v2 php artisan key:generate (be cauctious with this one)
    docker exec shace-api-v2 php artisan storage:link
    docker exec shace-api-v2 php artisan migrate --seed (be cauctious with this one)
    ```