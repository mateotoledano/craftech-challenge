# Explicación del Diagrama de Red

El diagrama de red que diseñé para la aplicación web fue realizado con Lucidchart por la comodidad que brinda y porque tengo experiencia utilizándolo. Además, este cuenta con figuras oficiales de AWS, plataforma que elegí por conocimientos y experiencia en la misma. Esta arquitectura tiene como objetivo principal garantizar alta disponibilidad (HA), escalabilidad para manejar cargas variables y el uso de diferentes tipos de bases de datos (relacional y no relacional). A continuación, se describe cada componente y su función en la arquitectura:

- **Cliente**: Los usuarios acceden a la aplicación web a través de un navegador.
- **Amazon Route 53**: Proporciona servicios de DNS, resolviendo los nombres de dominio (como www.example.com) y dirigiendo el tráfico a Amazon CloudFront.
- **AWS WAF (Web Application Firewall) y AWS Shield**: Protegen la aplicación contra amenazas y ataques DDoS, asegurando la seguridad de la capa de presentación.
- **Amazon CloudFront**: Actúa como una red de entrega de contenido (CDN), distribuyendo el contenido de manera eficiente y rápida a los usuarios finales, mejorando la experiencia del usuario.
- **Amazon S3 (Simple Storage Service)**: Almacena archivos estáticos y backups de manera duradera y escalable.
- **VPC (Virtual Private Cloud)**: Proporciona un entorno de red virtual aislado donde se despliega la infraestructura de la aplicación.
- **Subredes Públicas y Privadas**: Las subredes públicas contienen los NAT Gateways, permitiendo a las instancias en subredes privadas acceder a Internet sin ser accesibles directamente desde Internet. Las subredes privadas alojan las instancias EC2 (tanto los servidores web como de aplicación) y las bases de datos.
- **NAT Gateways**: Permiten a las instancias en las subredes privadas conectarse a Internet para actualizaciones y dependencias externas.
- **Elastic Load Balancing (ELB)**: Distribuye el tráfico de red entrante entre las instancias de EC2 en múltiples zonas de disponibilidad, asegurando que la carga de trabajo esté equilibrada y manejando fallos de instancias.
- **Auto Scaling Groups**: Escalan automáticamente el número de instancias EC2 (servidores web y de aplicación) hacia arriba o hacia abajo según la demanda, asegurando que siempre haya suficientes recursos para manejar el tráfico.
- **Amazon EC2**: Hospeda los servidores web (frontend) que sirven la aplicación en JavaScript y los servidores de aplicación (backend) que gestionan la lógica de negocio.
- **Bases de Datos**:
  - **Amazon RDS (Relational Database Service)**: Proporciona una base de datos relacional para almacenar datos estructurados.
  - **Amazon DynamoDB**: Proporciona una base de datos no relacional para almacenar datos que requieren acceso rápido y flexible.
- **Amazon API Gateway y AWS Lambda**: El API Gateway gestiona las solicitudes de API hacia los microservicios. AWS Lambda ejecuta código en respuesta a estas solicitudes, consumiendo y procesando los datos requeridos por los microservicios.

# Justificación

- **Cargas Variables**: La arquitectura utiliza Auto Scaling Groups para ajustar automáticamente el número de instancias EC2 basándose en la demanda. Esto asegura que la infraestructura puede escalar hacia arriba durante los picos de tráfico y reducirse cuando la demanda es baja, optimizando costos.
- **Alta Disponibilidad (HA)**: Se despliegan instancias EC2 y bases de datos en múltiples zonas de disponibilidad (AZ). En caso de fallo en una AZ, las instancias en las otras AZs pueden manejar la carga, asegurando que la aplicación permanezca disponible.
- **Frontend en JavaScript**: El frontend está hospedado en las instancias EC2 que actúan como servidores web. Amazon CloudFront mejora la entrega de contenido estático y dinámico, proporcionando una experiencia de usuario rápida y eficiente.
- **Backend con Base de Datos Relacional y No Relacional**: La aplicación utiliza Amazon RDS para datos estructurados y Amazon DynamoDB para datos no estructurados, asegurando flexibilidad y eficiencia en el almacenamiento y acceso a los datos.
- **Consumo de Microservicios Externos**: Los microservicios se gestionan a través de Amazon API Gateway y se ejecutan en AWS Lambda. Esto permite a la aplicación backend consumir servicios externos de manera eficiente y escalable.

# Referencias

- [AWS Web Application Hosting Best Practices](https://docs.aws.amazon.com/pdfs/whitepapers/latest/web-application-hosting-best-practices/web-application-hosting-best-practices.pdf#welcome)
- [AWS Cloud Architecture for Web Hosting](https://docs.aws.amazon.com/es_es/whitepapers/latest/web-application-hosting-best-practices/an-aws-cloud-architecture-for-web-hosting.html)
- [AWS Pricing and Architecture](https://docs.aws.amazon.com/es_es/whitepapers/latest/how-aws-pricing-works/architecture.html)
- [Serverless Multi-Tier Architectures with API Gateway and Lambda](https://docs.aws.amazon.com/es_es/whitepapers/latest/serverless-multi-tier-architectures-api-gateway-lambda/microservices-with-lambda.html)





