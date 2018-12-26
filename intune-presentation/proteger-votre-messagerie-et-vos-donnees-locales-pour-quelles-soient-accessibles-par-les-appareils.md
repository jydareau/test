# Utilisation courante d'intune

### Protection de votre messagerie et de vos données locales pour qu’elles soient accessibles en toute sécurité par les appareils mobiles <a id="protecting-your-on-premises-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices"></a>

La plupart des stratégies de mobilité d’entreprise commencent par un plan pour permettre aux employés munis d’appareils mobiles qui se connectent à Internet d’accéder de manière sécurisée à leurs e-mails. De nombreuses organisations hébergent encore des données et des serveurs d’applications locaux, tels que Microsoft Exchange, sur leur réseau d’entreprise.

Intune et Microsoft Enterprise Mobility + Security \(EMS\) fournissent une [solution d’accès conditionnel](https://docs.microsoft.com/fr-fr/intune/conditional-access) unique et intégrée pour Exchange Server, qui garantit qu’aucune application mobile ne peut accéder aux e-mails tant que l’appareil n’est pas inscrit auprès d’Intune. Vous pouvez implémenter ce type d’accès sans avoir à déployer une autre passerelle à la périphérie de votre réseau d’entreprise.

Intune prend également en charge l’activation de l’accès aux applications mobiles qui nécessitent un accès sécurisé aux données locales, comme un serveur d’applications métier. Ce type d’accès s’effectue généralement à l’aide de [certificats gérés par Intune](https://docs.microsoft.com/fr-fr/intune/certificates-configure) pour le contrôle d’accès, combinés à une passerelle VPN standard ou à un proxy dans le périmètre, comme le proxy d’application Microsoft Azure Active Directory.

Dans ce cas, la seule façon d’accéder à des données d’entreprise consiste à inscrire l’appareil pour la gestion.Une fois que les appareils sont inscrits, le système de gestion vérifie qu’ils sont conformes à vos stratégies avant de leur permettre d’accéder aux données d’entreprise. Par ailleurs, [l’outil de création de package de restrictions d’application et le SDK d’application](https://docs.microsoft.com/fr-fr/intune/apps-prepare-mobile-application-management) Intune permettent de limiter les données accessibles de votre application métier pour ne pas transmettre les données d’entreprise à des applications ou services de particuliers.

### Protection de votre messagerie et de vos données Office 365 pour qu’elles soient accessibles en toute sécurité par les appareils mobiles <a id="protecting-your-office-365-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices"></a>

La protection des données d’entreprise dans Office 365 \(messagerie, documents, messages instantanés, contacts\) ne pourrait pas être plus facile pour vous ou plus transparente pour vos utilisateurs.

Intune et Microsoft Enterprise Mobility + Security fournissent une solution d’accès conditionnel intégrée unique qui garantit qu’aucun utilisateur, appareil ou application ne peut accéder aux données Office 365 s’ils ne répondent pas aux exigences de conformité de votre entreprise \(exécution de l’[authentification multifacteur](https://docs.microsoft.com/fr-fr/intune/multi-factor-authentication), inscription avec Intune, utilisation d’une application gérée, version de système d’exploitation prise en charge, code confidentiel d’appareil, profil utilisateur à faible risque, etc.\).

Les applications mobiles Office comprises dans leurs magasins d’applications respectifs sont prêtes à utiliser les stratégies de relation contenant-contenu de données que vous pouvez configurer via Intune. Vous pouvez ainsi empêcher des données d’être partagées avec des applications \(par exemple, avec des applications de messagerie natives\) et des emplacements de stockage \(par exemple, Dropbox\) qui ne sont pas gérés par IT.Toutes ces fonctionnalités sont intégrées à Office 365 et EMS. Vous n’avez aucune infrastructure supplémentaire à déployer.

Une pratique de déploiement Office 365 courante consiste à exiger l’inscription des appareils à des fins de gestion si des configurations d’applications, de certificats, Wi-Fi ou VPN d’entreprise doivent être entièrement définies, scénario fréquent pour les appareils d’entreprise.

Toutefois, si votre utilisateur doit simplement accéder aux e-mails et documents d’entreprise, ce qui est souvent le cas pour les appareils personnels, vous pouvez lui demander d’utiliser les applications mobiles Office \(auxquelles vous avez appliqué des [stratégies de protection des applications](https://docs.microsoft.com/fr-fr/intune/app-protection-policies)\) et d’ignorer le processus d’inscription de l’appareil.

Dans les deux cas, les données Office 365 seront sécurisées par des stratégies que vous aurez définies.

### Offrir un programme BYOD \(Apportez votre propre appareil\) à tous les employés <a id="offer-a-bring-your-own-device-program-to-all-employees"></a>

BYOD \(Apportez votre propre appareil\) continue d’accroître sa popularité comme approche visant à réduire les dépenses en matériel ou à augmenter les choix de productivité mobile pour les employés. De nos jours, presque tout le monde a un téléphone personnel. Pourquoi en mettre un autre dans leur poche ? Le défi principal a toujours été de convaincre les employés d’inscrire leur appareil personnel pour la gestion, car ils s’inquiètent de ce que leur service informatique pourra voir et faire avec leur appareil.

Quand l’inscription d’appareil n’est pas une option viable, Intune propose une autre approche BYOD consistant simplement à [gérer les applications qui contiennent des données d’entreprise](https://docs.microsoft.com/fr-fr/intune/app-protection-policies). Intune protège les données d’entreprise même si l’application en question accède à la fois à des données personnelles et des données d’entreprise, comme c’est le cas pour les applications mobiles Office.

En tant qu’administrateur, vous pouvez exiger des utilisateurs qu’ils accèdent à Office 365 à partir des applications mobiles Office et configurer les applications avec des stratégies de protection des données \(comme leur chiffrement, leur protection par code confidentiel, et ainsi de suite\). Ces stratégies de protection des applications évitent la perte de données à partir d’applications et d’emplacements de stockage non gérés, que ce soit à l’intérieur ou en dehors de ces applications. Par exemple, les stratégies empêchent un utilisateur de copier du texte à partir d’un profil de messagerie d’entreprise vers un profil de messagerie privé même si ces deux profils sont configurés dans Outlook Mobile. Vous pouvez déployer des configurations similaires pour d’autres services et applications dont vos utilisateurs BYOD ont besoin.

### Fournir des téléphones d’entreprise à votre personnel <a id="issue-corporate-owned-phones-to-your-employees"></a>

De nos jours, de nombreux employés sont mobiles. La productivité sur les appareils mobiles est donc un impératif de compétitivité. Ces employés doivent pouvoir accéder de manière transparente à toutes les applications et données d’entreprise, à tout moment, où qu’ils se trouvent. Vous devez garantir la sécurité des données d’entreprise et limiter les coûts d’administration.

Intune propose des [solutions de configuration et de gestion en bloc](https://docs.microsoft.com/fr-fr/intune/device-enrollment) qui sont intégrées aux principales plateformes de gestion d’appareils d’entreprise disponibles aujourd’hui sur le marché, notamment le Programme d’inscription des appareils d’Apple et la plateforme de sécurité mobile Samsung Knox. La création centralisée de configurations d’appareils avec Intune peut faire de la mise en service des appareils d’entreprise une tâche hautement automatisée.

Imaginez : vous remettez à un employé un iPhone dans son emballage d’origine. L’employé le met sous tension et suit un flux d’installation propre à l’entreprise qui lui impose de s’authentifier. L’iPhone est configuré avec les [stratégies de sécurité](https://docs.microsoft.com/fr-fr/intune/device-profiles) en arrière-plan.

Ensuite, l’employé lance l’application Portail d’entreprise Intune pour accéder aux applications d’entreprise facultatives mises à sa disposition.

### Fournir des tablettes partagées à utilisation limitée à vos employés <a id="issue-limited-use-shared-tablets-to-your-employees"></a>

Les employés utilisent de plus en plus les technologies mobiles. Par exemple, les tablettes partagées sont désormais courantes parmi les employés de magasins de vente au détail. Qu’elles servent à traiter une vente ou à vérifier instantanément le stock, les tablettes aident à créer de riches interactions avec les clients.

Dans ce cas, la simplicité de l’expérience utilisateur est essentielle. Pour cette raison, les tablettes sont généralement fournies aux employés dans un mode d’utilisation limitée \(par exemple, l’employé ne peut interagir qu’avec une application métier\). Avec Intune, vous pouvez provisionner en bloc, sécuriser et gérer de façon centralisée ces appareils partagés [iOS et Android](https://docs.microsoft.com/fr-fr/intune/device-profiles), qui peuvent être configurés pour s’exécuter dans ce mode d’utilisation limitée.

### Permettre à vos employés d’accéder en toute sécurité à Office 365 à partir d’une borne publique non gérée <a id="enable-your-employees-to-securely-access-office-365-from-an-unmanaged-public-kiosk"></a>

Vos employés doivent parfois utiliser des appareils, applications ou navigateurs que vous ne pouvez pas gérer, tels que des ordinateurs publics disponibles lors de salons commerciaux et dans des hôtels.

Devez-vous autoriser vos employés à accéder aux e-mails de l’entreprise à partir de ces ordinateurs ? Avec Intune et Microsoft Enterprise Mobility + Security, la réponse ne peut être que « non » en [autorisant l’accès aux e-mails uniquement sur les appareils gérés par votre organisation](https://docs.microsoft.com/fr-fr/intune/conditional-access). Ainsi, vos employés fortement authentifiés ne risquent pas de laisser accidentellement des données d’entreprise sur l’ordinateur non approuvé.

