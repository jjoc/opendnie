opendnie
========

Liberación de fuentes desarrollados ad-hoc para el DNIe sobre esquema PKCS#11.
Added a README thats describe 10 steps to build a OpenSC-DNIe release for Debian or derived distribution.

---------------------------------------
- Update repository info README file --
-                                    --
-    Contenido del repositorio       --
---------------------------------------

- dgp-sources
Copia literal de los fuentes publicados por la Dirección General de la Policía y la Guardia Civil en:
http://www.dnielectronico.es/descargas/codigo_fuente_pkcs11/src.zip

- opensc-dnie
Adaptación del driver original para que compile y ejecute correctamente con
OpenSC-0.12.x

- opensc-opendnie
Nuevo driver con licencia LGPL escrito desde cero, para su integración en el
proyecto OpenSC

- tests
Diversas aplicaciones de test

- packaging
Información adicional para los diversos sistemas de paquetería

Organización (jerarquía de directorios)
-----------------------------------------------------------------

·-root
\
|--packaging
|  \
|  |--debian
|  |  \
|  |  |--branches
|  |  |  \
|  |  |  |--0.11.12
|  |  |  |--0.11.13
|  |  |  ·--0.12.0
|  |  ·--trunk
|  |--fedora
|  |  \
|  |  |--branches
|  |  |  \
|  |  |  |--0.11.12
|  |  |  |--0.11.13
|  |  |  ·--0.12.0
|  |  ·--trunk
  (X) --ubuntu 12.04
|
|  .(más distribuciones)
|  .
|
  |--opensc-dnie
|  |--branches
|     |  ·--0.12.0
|  ·--trunk
|
|--opensc-opendnie
|  \
|  |--branches
|  |  \
|  |  .--0.12.0
|  ·--trunk
|
|--tests 
·--dgp-sources

  * Described how to build with svn-buildpackage under pbuilder.

packaging/debian/trunk:
  * Merge from Ubuntu precise.
  * Added OpenDNIe driver to support the Spanish ID electronic card.
  * debian/control:
    - Recommend libacr38u, libccid and libnss3-tools.
    - Removed dh-autoreconf as build-dependency.
  * debian/opensc.install:
    - Install dnie-tool and its man page.
    - Removed duplicated installation of profiles.
  * debian/watch:
    - Mangle download url to use http instead of https.
  * debian/rules:
    - Removed call to autoreconf sequence because it does not build in debian.

Vìa: https://forja.cenatic.es/scm/viewvc.php/?root=opendnie
