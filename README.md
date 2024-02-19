# AWS-KubeAutoScaling

**Objetivo:**

Implementar y escalar automáticamente una aplicación simple utilizando Kubernetes en AWS, demostrando cómo Kubernetes crea y destruye contenedores en función de la carga de trabajo y el tráfico.

_AWS-KubeAutoScaling utilizará Docker para empaquetar una aplicación en un contenedor, y Kubernetes para desplegar, administrar y escalar automáticamente esos contenedores en un clúster de AWS_

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

(*) _Utilizaremos Docker junto con Kubernetes. Docker es una plataforma de contenedores que permite empacar una aplicación y todas sus dependencias en una unidad estandarizada llamada contenedor._ 

(*) _Kubernetes es una plataforma de orquestación de contenedores de código abierto que facilita la administración y escalado de aplicaciones en contenedores. Proporciona un entorno para desplegar, administrar y escalar aplicaciones de manera eficiente._

_- Características de Kubernetes: Escalado automático; Balanceo de carga; Alta disponibilidad; Gestión declarativa (infraestructura como código)._

***

**Resumen de los pasos a seguir:**

**1**. Creación de un clúster de Kubernetes en Amazon EKS:

- Crear un clúster y sus nodos en Amazon EKS mediante consola AWS.
- Conectarse al clúster mediante CloudShell CLI.

**2**. Desarrollo de la aplicación:

- Crear una aplicación simple (API REST o servidor web) que devuelva información básica.
- Escribir un Dockerfile para construir la imagen del contenedor de la aplicación.
 
(*) _Un Dockerfile es un archivo de texto que contiene instrucciones para construir una imagen de contenedor de manera automatizada._

**3**. Creación de un archivo de manifiesto de Kubernetes:

- Crear un archivo YAML para describir los recursos de Kubernetes necesarios, como despliegues y servicios.
- Configurar la escala automática de los contenedores en función de la carga de trabajo y el tráfico.

**4**. Implementación de la aplicación en el clúster de Kubernetes:

- Construir la imagen del contenedor utilizando el Dockerfile.
- Aplicar el archivo de manifiesto de Kubernetes para desplegar la aplicación en el clúster.

**5**. Configuración del balanceador de carga:

- Crear un balanceador de carga en AWS para distribuir el tráfico entre las instancias de la aplicación.

**6**. Pruebas y observación del escalado automático:

- Generar tráfico y carga de trabajo en la aplicación para observar cómo Kubernetes crea y destruye contenedores según sea necesario.

***

## 1. Creación de un clúster de Kubernetes en Amazon EKS

Primero, necesitamos crear un role especifico: IAM > roles > create: EKS >  EKS - Cluster

![1 01_iam_role](https://github.com/ccalvop/AWS-KubeAutoScaling/assets/126183973/b770203d-e8b4-4af8-afe7-55003ce8fbe3)

Ya podemos crear el cluster de Kubernetes: en la consola de AWS > Amazon EKS: "Create cluster"

![1 0_eks](https://github.com/ccalvop/AWS-KubeAutoScaling/assets/126183973/5f2da40f-50d3-469a-b0cf-f3f60b690519)
![1 02_eks_create](https://github.com/ccalvop/AWS-KubeAutoScaling/assets/126183973/6e766b64-e3fa-4141-93fa-cc7a0e27e223)

Tras varios minutos...Cluster Kubernetes creado!

![1 03_eks_created](https://github.com/ccalvop/AWS-KubeAutoScaling/assets/126183973/3fe72eee-7b62-4ff2-922e-01600fb0075f)

Ahora crearemos un grupo de nodos unidos al cluster: entramos en el cluster creado > Compute y en Node groups "Add node group"

Necesitamos un nuevo role con los siguientes permisos:

![1 04_role_node](https://github.com/ccalvop/AWS-KubeAutoScaling/assets/126183973/dea520d5-5c1d-45f9-9c45-cb0aa9978429)

Podemos crear el Node groups

![1 05_node](https://github.com/ccalvop/AWS-KubeAutoScaling/assets/126183973/1652c81a-1413-4f01-aa07-f215a6431007)

![1 06_node](https://github.com/ccalvop/AWS-KubeAutoScaling/assets/126183973/0b31f61c-abab-4875-8f52-2ae8606d1f8b)



***
![underconstruction_ccalvop](https://user-images.githubusercontent.com/126183973/234037995-bbe36371-8cc2-47a6-9c4f-b2311c57018d.jpg)

TIME - 2024-02-19 13:21:26