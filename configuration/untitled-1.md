# Configurer l’inscription automatique pour les appareils Windows 10



Connectez-vous à [Intune](https://aka.ms/intuneportal) en tant qu’administrateur général ou en tant qu’administrateur de services fédérés Intune.

### Configurer l’inscription automatique Windows 10 <a id="set-up-windows-10-automatic-enrollment"></a>

Dans cet exemple, vous allez utiliser l’inscription à MDM pour inscrire automatiquement les appareils d’entreprise et les appareils BYOD \(Apportez votre propre appareil\). 

1.  Dans Azure, choisissez **Azure Active Directory** &gt; **Mobility \(MDM et MAM\)**
2. Sélectionnez **Microsoft Intune**.

   ![Choisir Microsoft Intune dans la liste](https://docs.microsoft.com/fr-fr/intune/media/quickstart-setup-auto-enrollment/quickstart-setup-auto-enrollment-03.png)

3. Sélectionnez **Certains** dans **Portée de l’utilisateur GDR** pour utiliser l’inscription automatique à MDM et gérer les données d’entreprise sur les appareils Windows de votre personnel. L’inscription automatique à MDM sera configurée pour les appareils joints à AAD et les scénarios d’appareils BYOD \(Apportez votre propre appareil\).

   ![S&#xE9;lectionner &#xAB;&#xA0;Certains&#xA0;&#xBB; dans la liste Configurer](https://docs.microsoft.com/fr-fr/intune/media/quickstart-setup-auto-enrollment/quickstart-setup-auto-enrollment-04.png)

4.  Choisissez **Sélectionner des groupes** &gt; **Testeurs Contoso** &gt; **Sélectionner** comme groupe attribué.

   ![S&#xE9;lectionner le groupe &#xE0; inscrire](https://docs.microsoft.com/fr-fr/intune/media/quickstart-setup-auto-enrollment/quickstart-setup-auto-enrollment-05.png)

5. Sélectionnez **Certains** dans **Portée de l’utilisateur Gestion des applications mobiles** pour gérer les données sur les appareils de votre personnel.
6.  Choisissez **Sélectionner des groupes** &gt; **Testeurs Contoso** &gt; **Sélectionner** comme groupe attribué.
7. Utilisez les valeurs par défaut pour les options de configuration restantes.
8. Choisissez **Enregistrer**.

