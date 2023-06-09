Separando tfstates por servicio de AWS
```
└── terraform
    ├── s3
		│   └── main.tf
		│   └── backend.tf //Key = s3/terraform.tfstate
		│   └── provider.tf
    ├── dynamodb
		│   └── main.tf
		│   └── backend.tf //Key = dynamodb/terraform.tfstate
		│   └── provider.tf
    └── lambda
		│   └── main.tf
		│   └── backend.tf //Key = lambda/terraform.tfstate
		│   └── provider.tf
```

Separando tfstates por aplicación y servicio
```
└── terraform
    ├── catalog
		│   └── s3
		│   │   └── main.tf
		│   │   └── backend.tf //Key = catalog/s3/terraform.tfstate
		│   │   └── provider.tf
	  │   └── dynamodb
		│   │   └── main.tf
		│   │   └── backend.tf //Key = catalog/dynamodb/terraform.tfstate
		│   │   └── provider.tf
	  │   └── lambda
		│       └── main.tf
		│       └── backend.tf //Key = catalog/lambda/terraform.tfstate
		│       └── provider.tf
    ├── stock
		│   └── s3
		│       └── main.tf
		│       └── backend.tf //Key = stock/s3/terraform.tfstate
		│       └── provider.tf
```


Separando tfstates por entorno, aplicación y servicio
```
└── terraform
    ├── dev
		│   └── catalog
		│   │   └── s3
		│		│   │   └── main.tf
		│		│   │   └── backend.tf //Key = dev/catalog/s3/terraform.tfstate
		│		│   │   └── provider.tf
		│		│   └── dynamodb
		│		│   │   └── main.tf
		│		│   │   └── backend.tf //Key = dev/catalog/dynamodb/terraform.tfstate
		│		│   │   └── provider.tf
		│		│   └── lambda
		│		│       └── main.tf
		│		│       └── backend.tf //Key = dev/catalog/lambda/terraform.tfstate
		│		│       └── provider.tf
		│   └── stock
		│       └── s3
		│		        └── main.tf
		│		        └── backend.tf //Key = dev/stock/s3/terraform.tfstate
		│		        └── provider.tf
    ├── pre
		│   └── catalog
		...
```

Separando tfstate por entorno y proposito

```
└── terraform
    ├── dev
		   └── base                            // Infra relacionadas con la configuracion base de la plataforma
		       └── aws-fiori-kubernetes        // Cuenta de Aws destinada a Kubernetes
		               └── network             // Infra relacionadas con el networking de la cuenta
                           └── vpc
                       └── Storage
                           └── S3
                           └── dynamoDb
                └── Azure                       // Cuenta de Azure
            └── services
                └── Catalog                     // Infra del servicio "Catalogo" 
                └── Stock                       // Infra del servicio "Stock"
                └── Orders                      // Infra del servicio "Pedidos" 
            └── shared                          // Infra compartida por varios equipos
                └── Jenkins
                └── Sonar
                └── Nexus
    ├── pre
    ...
    ├── pro
    ...
 ```


```
└── terraform
    ├── s3
		│   └── main.tf
		│   └── backend.tf //Key = s3/terraform.tfstate
		│   └── provider.tf
    ├── dynamodb
		│   └── main.tf
		│   └── backend.tf //Key = dynamodb/terraform.tfstate
		│   └── provider.tf
    └── lambda
		│   └── main.tf
		│   └── backend.tf //Key = lambda/terraform.tfstate
		│   └── provider.tf
        |   

```        
