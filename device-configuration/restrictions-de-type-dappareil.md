# Restrictions de type d'appareil

 Un appareil doit respecter les restrictions d'inscription affectées à l'utilisateur qui ont la priorité la plus haute. Vous pouvez faire glisser une restriction d'appareil pour changer sa priorité. Les restrictions par défaut ont la priorité la plus basse pour tous les utilisateurs et régissent les inscriptions sans utilisateur. Les restrictions par défaut peuvent être modifiées, mais pas supprimées.

![](../.gitbook/assets/image%20%282%29.png)

  


### Restrictions de type d'appareil

#### Selectionner les plateformes par défaut et autoriser l'inscription des plateformes

![](../.gitbook/assets/image%20%2811%29.png)

####  Configurer des plateformes

![](../.gitbook/assets/image%20%2820%29.png)

Limites d'appareil

## Bloquer les appareils Personnel



#### Microsoft Intune standalone

The configuration for Microsoft Intune standalone must be done by using the Azure portal. At this moment Microsoft Intune standalone supports the restriction on personally-owned devices for Android, iOS and macOS. This can be configured by simply following the next steps.

| **1** | Open the [Azure portal](https://portal.azure.com/) and navigate to **Intune** &gt; **Device enrollment** &gt; **Enrollment restrictions**to open the **Device enrollment – Enrollment restrictions** blade; |
| :--- | :--- |
| **2** | On the **Device enrollment – Enrollment restrictions** blade, select **Default** in the **Device Type Restrictions** section, to open the **All Users** blade; |
| **3** | On the **All Users** blade, select Platform Configurations to open the **All Users – Platform Configurations** blade; |
| **4** | [![BlockPersonal\_Standalone](https://i1.wp.com/www.petervanderwoude.nl/wordpress/wp-content/uploads/BlockPersonal_Standalone_thumb.jpg?zoom=2&resize=304%2C143&ssl=1)](https://i2.wp.com/www.petervanderwoude.nl/wordpress/wp-content/uploads/BlockPersonal_Standalone.jpg?ssl=1)On the **All Users – Platform Configurations** blade, select **Block**, in the **PERSONALLY OWNED** column, for the platforms of which personal-owned devices must be blocked and click **Save**. |

Note: To specify that a device is company-owned, ad the IMEI or serial number to the _Predeclared Devices list_ \(as shown [here](https://www.petervanderwoude.nl/post/easily-predeclaring-corporate-owned-devices/)\), or enroll it using Apple DEP \(iOS only\)..

