# Configuración Centralizada (Spring Cloud Config)

>Almacenamiento de las configuraciones YAML de los microservicios, las cuales son consumidas por el **Microservicio de Spring Cloud Config** para poder distribuir cada configuración a su respectivo microservicio.
<p align="right">
  <a href="https://github.com/AlbertoDeTeresaChaves/moviesreview-config-server">
    <img src="https://img.shields.io/badge/Ver_Config_Server-007ACC?style=for-the-badge&logo=github&logoColor=white" alt="Ver Config Server" />
  </a>
</p>

---

## Flujo de Funcionamiento

<img width="1000" height="500" alt="Pasted image 20260921215839" src="https://github.com/user-attachments/assets/3d56eb3a-4f8d-4f99-88d1-867b52f497b5" />

1. **SOLICITO LAS CONFIGURACIONES**  
   Al iniciarse un microservicio, este le pide al Config Server que le mande las configuraciones YAML a través de una petición `HTTP GET`.

2. **DAME LAS CONFIGURACIONES**  
   El Config Server hace un `git fetch` o `git pull` para buscar los cambios más recientes del repositorio.

   > 💡
   > Al iniciarse el **Microservicio Config Server**, este realiza un `git clone` del repositorio central.

3. **TE DOY LAS CONF DEL REPO**  
   El repositorio alojado en **GitHub** le entrega las configuraciones más recientes de los archivos YAML.

4. **AQUÍ LAS TIENES**  
   El Config Server le retorna a los microservicios las configuraciones solicitadas en formato JSON.

