# Access container
docker exec -it rabbitmq bash
# Enable UI: 
rabbitmq-plugins enable rabbitmq_management
# Create user:
rabbitmqctl add_user admin admin
rabbitmqctl set_user_tags admin administrator
rabbitmqctl set_permissions -p / admin ".*" ".*" ".*"
# Magento config
    'queue' => [
        'amqp' => [
            'host' => '127.0.0.1',
            'port' => '5672',
            'user' => 'admin',
            'password' => 'admin',
            'virtualhost' => '/'
        ],
        'consumers_wait_for_messages' => 1
    ]