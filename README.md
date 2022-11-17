# CloudFormation_Autoscaling_Templete

Caso Práctico: Automatización y Elasticidad en AWS

El objetivo de este caso práctico es proporcionar una plantilla de CloudFormation que permita
desplegar una arquitectura en alta disponibilidad. Para esto, debes crear lo siguiente:

Una plantilla CloudFormation que incluya lo siguiente:

  ++ Una VPC con 2 subnets públicas en zonas de disponibilidad distintas (puedes
elegir las zonas de disponibilidad que consideres).

  ++ Un autoscaling group que despliegue un mínimo de 2 y un máximo de 4
instancias EC2 con la AMI Amazon Linux 2 y de tamaño t2.micro o t3.micro
(puedes elegir el tamaño). Las instancias deben tener instalado el servidor web
Nginx utilizando un script User Data y también deben tener dirección IP
pública asignada. Estas instancias deben tener asociado un Security Group que
solo permita el acceso a través del puerto 80 desde cualquier IP de origen.
