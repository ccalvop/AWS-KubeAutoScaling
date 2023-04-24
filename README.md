# AWS-KubeAutoScaling

**Objetivo:**

Implementar y escalar automáticamente una aplicación simple utilizando Kubernetes en AWS, demostrando cómo Kubernetes crea y destruye contenedores en función de la carga de trabajo y el tráfico.

**Servicios de AWS involucrados:**

  - Amazon EKS (Elastic Kubernetes Service): para crear y gestionar el clúster de Kubernetes.
  - AWS Fargate: como opción de implementación sin servidor para Amazon EKS, permitiendo la ejecución automática de contenedores.
  - Amazon RDS (Relational Database Service): para alojar una base de datos simple en caso de que la aplicación lo requiera.
  - AWS Load Balancer: para distribuir el tráfico entre las instancias de la aplicación.

**Archivos y código a crear:**

  - Aplicación simple: una API REST básica o un servidor web que devuelva información básica.
  - Dockerfile: para crear la imagen del contenedor de la aplicación.
  - Archivo de manifiesto de Kubernetes: para describir los recursos necesarios, como despliegues, servicios y configuraciones de escalado automático.
  - Scripts de AWS CLI o CloudFormation (opcional): para automatizar la creación y configuración de recursos de AWS.

**Resultado esperado:**

Una aplicación web funcional que permita a los usuarios ingresar su enlace de perfil de LinkedIn y recibir un análisis detallado de su perfil, incluyendo una puntuación global y puntuaciones por secciones, así como gráficos y visualizaciones.

***
