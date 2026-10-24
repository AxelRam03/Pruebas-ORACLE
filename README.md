# Pruebas de automatización — NGINX

Repositorio de práctica de administración de servidores con Ansible.

## Playbook disponible
`install_nginx.yml` instala el paquete NGINX y habilita/inicia el servicio en los hosts definidos en el inventario.

## Requisitos
- Ansible instalado en la máquina de control.
- Inventario de hosts configurado.
- Acceso SSH y permisos de elevación adecuados en los servidores objetivo.
- Hosts compatibles con el módulo de paquetes utilizado por el playbook (actualmente `yum`).

## Ejecución de ejemplo
Revisa el inventario y la conectividad antes de ejecutar:

```bash
ansible-inventory -i inventory.ini --list
ansible all -i inventory.ini -m ping
ansible-playbook -i inventory.ini install_nginx.yml --check
ansible-playbook -i inventory.ini install_nginx.yml
```

El archivo `inventory.ini` del ejemplo debe crearse según tu laboratorio; no incluyas direcciones internas ni credenciales reales en el repositorio público.

## Mejoras siguientes
- [ ] Añadir un inventario de ejemplo sin datos reales.
- [ ] Definir `become` y requisitos por distribución.
- [ ] Validar idempotencia y compatibilidad con las distribuciones objetivo.
- [ ] Añadir lint de Ansible en CI.
