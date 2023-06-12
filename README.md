# AWS-KubeAutoScaling

**Objetivo:**

Implementar y escalar automáticamente una aplicación simple utilizando Kubernetes en AWS, demostrando cómo Kubernetes crea y destruye contenedores en función de la carga de trabajo y el tráfico.

**Servicios de AWS involucrados:**

  - Amazon EKS (Elastic Kubernetes Service): para crear y gestionar el clúster de Kubernetes.
  - AWS Fargate: como opción de implementación sin servidor para Amazon EKS, permitiendo la ejecución automática de contenedores.
  - Amazon RDS (Relational Database Service): para alojar una base de datos simple en caso de que la aplicación lo requiera.
  - AWS Load Balancer: para distribuir el tráfico entre las instancias de la aplicación.

**Archivos:**

  - Aplicación simple: una API REST básica o un servidor web que devuelva información básica.
  - Dockerfile: para crear la imagen del contenedor de la aplicación.
  - Archivo de manifiesto de Kubernetes: para describir los recursos necesarios, como despliegues, servicios y configuraciones de escalado automático.
  - Scripts de AWS CLI o CloudFormation (opcional): para automatizar la creación y configuración de recursos de AWS.

**Resultado:**

Una aplicación simple alojada en un clúster de Kubernetes en AWS que escala automáticamente en función del tráfico y la carga de trabajo. La aplicación estará accesible a través de un balanceador de carga, y se observará cómo Kubernetes crea y destruye contenedores en función de la carga de trabajo y el tráfico.

***

![underconstruction_ccalvop](https://user-images.githubusercontent.com/126183973/234037995-bbe36371-8cc2-47a6-9c4f-b2311c57018d.jpg)
