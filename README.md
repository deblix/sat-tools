# sat-tools

Colección de herramientas de línea de comandos para trabajar con
certificados y llaves del SAT (e.firma y sello digital).

> **Aviso:** Este proyecto no es oficial del SAT ni está afiliado,
> respaldado o patrocinado por el Servicio de Administración Tributaria.
> Es una herramienta independiente mantenida por Mario Oyorzabal Salgado.

## Herramientas

| Comando | Descripción |
|---|---|
| `sat-pair-check` | Verifica que un `.cer` y un `.key` formen par comparando sus modulus |

Más comandos se irán agregando conforme el proyecto crezca.

## Requisitos

- Bash 4.0 o superior
- OpenSSL 1.1.1 o superior
- Coreutils estándar

En Debian/Ubuntu:

```bash
sudo apt install openssl bash coreutils
```

## Uso

Cada comando tiene su propia ayuda:

```bash
sat-pair-check --help
```

### sat-pair-check

Verifica si un certificado `.cer` y una llave `.key` del SAT forman par.

```bash
SAT_KEY_PASSWORD='mi_contraseña' sat-pair-check --cert sello.cer --key sello.key
```

Opciones:

| Opción | Descripción |
|---|---|
| `-c, --cert ARCHIVO` | Ruta al certificado `.cer` |
| `-k, --key ARCHIVO` | Ruta a la llave privada `.key` |
| `-q, --quiet` | Sin salida, solo exit code |
| `-h, --help` | Muestra la ayuda |
| `-V, --version` | Muestra la versión |

#### Contraseña de la llave

El `.key` del SAT está protegido con contraseña. `sat-pair-check` la
toma de la variable de entorno `SAT_KEY_PASSWORD`.

Por seguridad, **no se acepta la contraseña como argumento en la línea
de comandos**, porque quedaría registrada en el historial del shell y
en la lista de procesos.

#### Códigos de salida

| Código | Significado |
|---|---|
| `0` | El certificado y la llave coinciden |
| `1` | El certificado y la llave no coinciden |
| `2` | Se mostró la ayuda o la versión (no se realizó la verificación) |
| `3` | Error |

## Donaciones

Este proyecto es software libre y gratuito. Si te resulta útil y
quieres apoyar su desarrollo, puedes hacer una donación:

- **PayPal:** [tu-enlace-paypal]
- **Ko-fi:** [tu-enlace-ko-fi]
- **GitHub Sponsors:** [tu-enlace-sponsors]
- **Bitcoin:** `tu-dirección-btc`

Las donaciones son completamente opcionales. El proyecto seguirá
siendo libre y abierto independientemente de ellas.

## Licencia

Copyright (C) 2026 Tu Nombre / deblix

Este programa es software libre: puedes redistribuirlo y/o modificarlo
bajo los términos de la GNU General Public License, versión 3 o
posterior, publicada por la Free Software Foundation.

Este programa se distribuye con la esperanza de que sea útil, pero
**SIN NINGUNA GARANTÍA**; ni siquiera la garantía implícita de
**COMERCIABILIDAD** o **IDONEIDAD PARA UN PROPÓSITO PARTICULAR**.
Consulta la GNU General Public License para más detalles.

Deberías haber recibido una copia de la GNU General Public License
junto con este programa. Si no, consulta
<https://www.gnu.org/licenses/>.

Ver [LICENSE](LICENSE) para el texto completo.
