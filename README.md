# Drupal7-SimpleSAML-WSO2
Configuración Drupal7 SimpleSAMLPHP y WSO2.

vim /var/simplesamlphp/config/config.php

Cambiar a:
```
'auth.adminpassword' => 'MISUPER_PASSWORD',
```

Cambiar a:
```
// tr -c -d '0123456789abcdefghijklmnopqrstuvwxyz' </dev/urandom | dd bs=32 count=1 2>/dev/null;echo
'secretsalt' => 'NUMALEATEATORIO_COMANDO ANTERIOR',
```

Cambiar a:
```
'technicalcontact_name' => 'Jorge Useche',
'technicalcontact_email' => 'jorgenator2@yahoo.es',
```

vim /var/simplesamlphp/config/authsources.php

Agregar coherentemente:
```
    'wso2-sp' => array(

        'saml:SP',

        // The entity ID of this SP. 

        // Can be NULL/unset, in which case an entity ID is generated based on the metadata URL. 

        'entityID' => 'simplesaml',

        // The entity ID of the IdP this should SP should contact. 

        // Can be NULL/unset, in which case the user will be shown a list of available IdPs. 

        'idp' => 'https://devops.red:9443/samlsso',

        // The URL to the discovery service. 

        // Can be NULL/unset, in which case a builtin discovery service will be used. 

        'discoURL' => NULL,

    ),
```


Instalar en drupal https://www.drupal.org/project/simplesamlphp_auth

# Referencias comentadas
- Proxy reverse para wso2 con nginx https://docs.wso2.com/display/Carbon430/Adding+a+Custom+Proxy+Path
- Buenas prácticas en WSO2 AM https://wso2.com/library/articles/2017/03/api-management-best-practices-with-wso2-api-manager/
- Personalizar página de logueo autenticación https://docs.wso2.com/display/IS530/Customizing+Login+Pages+for+Service+Providers

# Referencias
- https://docs.wso2.com/display/IS500/SAML2+IdP+with+SimpleSAMLphp+Service+Provider
- https://docs.wso2.com/display/IS530/Configuring+SimpleSAMLphp+as+a+Service+Provider
- http://www.securityinternal.com/2015/05/setting-up-wso2-identity-server-as.html
- https://stackoverflow.com/questions/25428609/how-can-i-change-the-identity-as-an-idp-of-the-wso2-is
- https://www.drupal.org/node/157632
- http://wso2.com/library/articles/2014/10/wso2-identity-server-single-sign-on-with-drupal/
- https://pulasthiharasgama.wordpress.com/2015/11/26/integrating-drupal-with-wso2-identity-server/
- https://pulasthiharasgama.wordpress.com/tag/single-sign-on/
- https://stackoverflow.com/questions/21727087/wso2-identity-server-error-when-processing-request
