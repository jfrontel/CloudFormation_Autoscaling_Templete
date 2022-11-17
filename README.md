# CloudFormation_Autoscaling_Templete

Caso Práctico: Automatización y Elasticidad en AWS

El objetivo de este caso práctico es proporcionar una plantilla de CloudFormation que permita desplegar una arquitectura en alta disponibilidad. 
Para esto, debes crear lo siguiente:

Una plantilla CloudFormation que incluya lo siguiente:

  ++ Una VPC con 2 subnets públicas en zonas de disponibilidad distintas (puedes elegir las zonas de disponibilidad que consideres).

  ++ Un autoscaling group que despliegue un mínimo de 2 y un máximo de 4 instancias EC2 con la AMI Amazon Linux 2 y de tamaño t2.micro o t3.micro
(puedes elegir el tamaño). Las instancias deben tener instalado el servidor web Nginx utilizando un script User Data y también deben tener dirección IP
pública asignada. Estas instancias deben tener asociado un Security Group que solo permita el acceso a través del puerto 80 desde cualquier IP de origen.


<h2>¿Qué es CloudFormation?</h2>

AWS CloudFormation es un servicio que lo ayuda a modelar y configurar sus recursos de AWS para que pueda dedicar menos tiempo a administrar esos recursos y más tiempo a concentrarse en sus aplicaciones que se ejecutan en AWS. Usted crea una plantilla que describe todos los recursos de AWS que desea (como instancias de Amazon EC2 o instancias de base de datos de Amazon RDS), y CloudFormation se encarga de aprovisionar y configurar esos recursos por usted. No necesita crear y configurar individualmente los recursos de AWS y descubrir qué depende de qué; CloudFormation se encarga de eso. Los siguientes escenarios demuestran cómo puede ayudar CloudFormation.

<h3>Simplifique la gestión de la infraestructura</h3>
Para una aplicación web escalable que también incluye una base de datos back-end, puede usar un grupo de Auto Scaling, un balanceador de carga de Elastic Load Balancing y una instancia de base de datos de Amazon Relational Database Service. Puede usar cada servicio individual para aprovisionar estos recursos y, después de crear los recursos, debe configurarlos para que funcionen juntos. Todas estas tareas pueden agregar complejidad y tiempo antes incluso de que su aplicación esté en funcionamiento.

En su lugar, puede crear una plantilla de CloudFormation o modificar una existente. Una plantilla describe todos sus recursos y sus propiedades. Cuando utiliza esa plantilla para crear una pila de CloudFormation, CloudFormation le proporciona el grupo de Auto Scaling, el balanceador de carga y la base de datos. Una vez que la pila se ha creado correctamente, sus recursos de AWS están en funcionamiento. Puede eliminar la pila con la misma facilidad, lo que elimina todos los recursos de la pila. Al usar CloudFormation, administra fácilmente una colección de recursos como una sola unidad.

![image](https://user-images.githubusercontent.com/114813145/202518407-5d056c36-5c83-413c-845c-05f04efb15cb.png)


<h2>Caso Práctico: Automatización y Elasticidad en AWS por medio de Plantillas de CloudFormation</h2>

CloudFormation se puede utilizar para implementar casi cualquier servicio de AWS. En este proyecto, usaré una plantilla para crear un grupo de ajuste de escala automático usando instancias t2.micro EC2 en 2 subredes públicas en una VPC. Incluye una puerta de enlace de Internet para permitir el acceso a Internet a las instancias EC2. Junto con un grupo de seguridad del servidor web para permitir el tráfico entrante a través del puerto 80 desde cualquier IP de origen. Las instancias tendrán un servidor web Nginx utilizando un script User Data instalado en el momento del lanzamiento. El grupo de ajuste de escala automático proporcionará un mínimo de 2 instancias, un máximo de 4 instancias, la capacidad deseada la dejaremos en 3 y. Para probar que el ASG se está escalando, demostraré la terminación de 2 instancias.

<h3>Paso 1: Crear pila</h3>
En la consola de AWS, vaya a CloudFormation y haga clic en Crear pila.

![image](https://user-images.githubusercontent.com/114813145/202524100-ab712243-b181-4246-8178-fa996d30b7de.png)


<h3>Paso 2: Crear plantilla</h3>
Cogeremos una plantilla estandar de autoescalado en:
https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/sample-templates-services-us-west-2.html
y la versionaremos a nuestro gusto para lograr completar el caso práctico con éxito.

Ver en archivos my_templete_autoscaling

Este archivo que está compuesto por todo lo que necesitamos para implementar nuestra solución en AWS lo subiremos en:

![image](https://user-images.githubusercontent.com/114813145/202524817-d907e63a-0f18-45e2-99d4-cc2ee2aaf496.png)

Click en Next y esperamos a que se vaya ejecutando e implentando todo el código.
