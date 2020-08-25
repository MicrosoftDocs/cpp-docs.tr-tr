---
title: Güvenlik tanımlayıcısı genel Işlevleri
ms.date: 11/04/2016
f1_keywords:
- atlsecurity/ATL::Sids::AccountOps
- atlsecurity/ATL::Sids::Admins
- atlsecurity/ATL::Sids::AnonymousLogon
- atlsecurity/ATL::Sids::AuthenticatedUser
- atlsecurity/ATL::Sids::BackupOps
- atlsecurity/ATL::Sids::Batch
- atlsecurity/ATL::Sids::CreatorGroup
- atlsecurity/ATL::Sids::CreatorGroupServer
- atlsecurity/ATL::Sids::CreatorOwner
- atlsecurity/ATL::Sids::CreatorOwnerServer
- atlsecurity/ATL::Sids::Dialup
- atlsecurity/ATL::Sids::Guests
- atlsecurity/ATL::Sids::Interactive
- atlsecurity/ATL::Sids::Local
- atlsecurity/ATL::Sids::Network
- atlsecurity/ATL::Sids::NetworkService
- atlsecurity/ATL::Sids::Null
- atlsecurity/ATL::Sids::PowerUsers
- atlsecurity/ATL::Sids::PrintOps
- atlsecurity/ATL::Sids::Proxy
- atlsecurity/ATL::Sids::RasServers
- atlsecurity/ATL::Sids::Replicator
- atlsecurity/ATL::Sids::RestrictedCode
- atlsecurity/ATL::Sids::Self
- atlsecurity/ATL::Sids::ServerLogon
- atlsecurity/ATL::Sids::Service
- atlsecurity/ATL::Sids::System
- atlsecurity/ATL::Sids::SystemOps
- atlsecurity/ATL::Sids::TerminalServer
- atlsecurity/ATL::Sids::Users
- atlsecurity/ATL::Sids::World
helpviewer_keywords:
- security IDs [C++]
- SIDs [C++], returning SID objects
ms.assetid: 85404dcb-c59b-4535-ab3d-66cfa37e87de
ms.openlocfilehash: e040cbb76e851bd323360f4f5ae602f9c73651d1
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834485"
---
# <a name="security-identifier-global-functions"></a>Güvenlik tanımlayıcısı genel Işlevleri

Bu işlevler, yaygın olarak bilinen SID nesnelerini döndürür.

> [!IMPORTANT]
> Aşağıdaki tabloda listelenen işlevler, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

|Ad|Açıklama|
|-|-|
|[SID 'ler:: Accounler](#accountops)|DOMAIN_ALIAS_RID_ACCOUNT_OPS SID döndürür.|
|[SID 'ler:: Admins](#admins)|DOMAIN_ALIAS_RID_ADMINS SID döndürür.|
|[SID 'ler:: AnonymousLogon](#anonymouslogon)|SECURITY_ANONYMOUS_LOGON_RID SID döndürür.|
|[SID 'ler:: kimlik doğrulayan Teduser](#authenticateduser)|SECURITY_AUTHENTICATED_USER_RID SID döndürür.|
|[SID 'ler:: Backupop 'Lar](#backupops)|DOMAIN_ALIAS_RID_BACKUP_OPS SID döndürür.|
|[SID 'ler:: Batch](#batch)|SECURITY_BATCH_RID SID döndürür.|
|[SID 'ler:: CreatorGroup](#creatorgroup)|SECURITY_CREATOR_GROUP_RID SID döndürür.|
|[SID 'ler:: CreatorGroupServer](#creatorgroupserver)|SECURITY_CREATOR_GROUP_SERVER_RID SID döndürür.|
|[SID 'ler:: CreatorOwner](#creatorowner)|SECURITY_CREATOR_OWNER_RID SID döndürür.|
|[SID 'ler:: CreatorOwnerServer](#creatorownerserver)|SECURITY_CREATOR_OWNER_SERVER_RID SID döndürür.|
|[SID 'ler::D ıalup](#dialup)|SECURITY_DIALUP_RID SID döndürür.|
|[SID 'ler:: konuklar](#guests)|DOMAIN_ALIAS_RID_GUESTS SID döndürür.|
|[SID 'ler:: Interactive](#interactive)|SECURITY_INTERACTIVE_RID SID döndürür.|
|[SID 'ler:: Local](#local)|SECURITY_LOCAL_RID SID döndürür.|
|[SID 'ler:: Network](#network)|SECURITY_NETWORK_RID SID döndürür.|
|[SID 'ler:: NetworkService](#networkservice)|SECURITY_NETWORK_SERVICE_RID SID döndürür.|
|[SID:: null](#null)|SECURITY_NULL_RID SID döndürür.|
|[SID 'ler::P reW2KAccess](#prew2kaccess)|DOMAIN_ALIAS_RID_PREW2KCOMPACCESS SID döndürür.|
|[SID 'ler: owerUsers:P](#powerusers)|DOMAIN_ALIAS_RID_POWER_USERS SID döndürür.|
|[SID 'ler::P Rin](#printops)|DOMAIN_ALIAS_RID_PRINT_OPS SID döndürür.|
|[SID 'ler::P Roxy](#proxy)|SECURITY_PROXY_RID SID döndürür.|
|[SID 'ler:: RasServers](#rasservers)|DOMAIN_ALIAS_RID_RAS_SERVERS SID döndürür.|
|[SID 'ler:: çoğaltıcı](#replicator)|DOMAIN_ALIAS_RID_REPLICATOR SID döndürür.|
|[SID 'ler:: Kısıttedcode](#restrictedcode)|SECURITY_RESTRICTED_CODE_RID SID döndürür.|
|[SID 'ler:: Self](#self)|SECURITY_PRINCIPAL_SELF_RID SID döndürür.|
|[SID 'ler:: ServerLogon](#serverlogon)|SECURITY_SERVER_LOGON_RID SID döndürür.|
|[SID:: Service](#service)|SECURITY_SERVICE_RID SID döndürür.|
|[SID 'ler:: System](#system)|SECURITY_LOCAL_SYSTEM_RID SID döndürür.|
|[SID 'ler:: SystemOps](#systemops)|DOMAIN_ALIAS_RID_SYSTEM_OPS SID döndürür.|
|[SID 'ler:: TerminalServer](#terminalserver)|SECURITY_TERMINAL_SERVER_RID SID döndürür.|
|[SID 'ler:: kullanıcılar](#users)|DOMAIN_ALIAS_RID_USERS SID döndürür.|
|[SID 'ler:: World](#world)|SECURITY_WORLD_RID SID döndürür.|

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity. h

## <a name="sidsaccountops"></a><a name="accountops"></a> SID 'ler:: Accounler

DOMAIN_ALIAS_RID_ACCOUNT_OPS SID döndürür.

```
CSid AccountOps() throw(...);
```

## <a name="sidsadmins"></a><a name="admins"></a> SID 'ler:: Admins

DOMAIN_ALIAS_RID_ADMINS SID döndürür.

```
CSid Admins() throw(...);
```

## <a name="sidsanonymouslogon"></a><a name="anonymouslogon"></a> SID 'ler:: AnonymousLogon

SECURITY_ANONYMOUS_LOGON_RID SID döndürür.

```
CSid AnonymousLogon() throw(...);
```

## <a name="sidsauthenticateduser"></a><a name="authenticateduser"></a> SID 'ler:: kimlik doğrulayan Teduser

SECURITY_AUTHENTICATED_USER_RID SID döndürür.

```
CSid AuthenticatedUser() throw(...);
```

## <a name="sidsbackupops"></a><a name="backupops"></a> SID 'ler:: Backupop 'Lar

DOMAIN_ALIAS_RID_BACKUP_OPS SID döndürür.

```
CSid BackupOps() throw(...);
```

## <a name="sidsbatch"></a><a name="batch"></a> SID 'ler:: Batch

SECURITY_BATCH_RID SID döndürür.

```
CSid Batch() throw(...);
```

## <a name="sidscreatorgroup"></a><a name="creatorgroup"></a> SID 'ler:: CreatorGroup

SECURITY_CREATOR_GROUP_RID SID döndürür.

```
CSid CreatorGroup() throw(...);
```

## <a name="sidscreatorgroupserver"></a><a name="creatorgroupserver"></a> SID 'ler:: CreatorGroupServer

SECURITY_CREATOR_GROUP_SERVER_RID SID döndürür.

```
CSid CreatorGroupServer() throw(...);
```

## <a name="sidscreatorowner"></a><a name="creatorowner"></a> SID 'ler:: CreatorOwner

SECURITY_CREATOR_OWNER_RID SID döndürür.

```
CSid CreatorOwner() throw(...);
```

## <a name="sidscreatorownerserver"></a><a name="creatorownerserver"></a> SID 'ler:: CreatorOwnerServer

SECURITY_CREATOR_OWNER_SERVER_RID SID döndürür.

```
CSid CreatorOwnerServer() throw(...);
```

## <a name="sidsdialup"></a><a name="dialup"></a> SID 'ler::D ıalup

SECURITY_DIALUP_RID SID döndürür.

```
CSid Dialup() throw(...);
```

## <a name="sidsguests"></a><a name="guests"></a> SID 'ler:: konuklar

DOMAIN_ALIAS_RID_GUESTS SID döndürür.

```
CSid Guests() throw(...);
```

## <a name="sidsinteractive"></a><a name="interactive"></a> SID 'ler:: Interactive

SECURITY_INTERACTIVE_RID SID döndürür.

```
CSid Interactive() throw(...);
```

## <a name="sidslocal"></a><a name="local"></a> SID 'ler:: Local

SECURITY_LOCAL_RID SID döndürür.

```
CSid Local() throw(...);
```

## <a name="sidsnetwork"></a><a name="network"></a> SID 'ler:: Network

SECURITY_NETWORK_RID SID döndürür.

```
CSid Network() throw(...);
```

## <a name="sidsnetworkservice"></a><a name="networkservice"></a> SID 'ler:: NetworkService

SECURITY_NETWORK_SERVICE_RID SID döndürür.

```
CSid NetworkService() throw(...);
```

### <a name="remarks"></a>Açıklamalar

NT Authorıty\networkservice kullanıcısına CPerfMon güvenlik nesnesini okumasını sağlamak için NetworkService kullanın. NetworkService, DLL 'nin Windows XP Home Edition, Windows XP Professional, Windows Server 2003 ve daha sonraki işletim sistemlerinde NetworkService hesabı altında oturum açmasını sağlayacak olan ATLServer koduna bir SecurityAttribute ekler.

Özel günlük sayaçları, Perfmon MMC 'de ATLServer CPerfMon sınıfıyla oluşturulduğunda, gerçek zamanlı görünümde doğru şekilde görünebilse de, sayaçlar günlük dosyası görüntülenirken görünmeyebilir. CPerfMon özel performans sayaçları, Windows XP Home Edition, Windows XP Professional, Windows Server 2003 (veya üzeri) işletim sistemlerinde "Performans Günlükleri ve Uyarıları" hizmeti (smlogsvc.exe) altında çalıştırmak için gerekli izinlere sahip değildir. Bu hizmet "NT Authorıty\networkservice" hesabı altında çalışır.

## <a name="sidsnull"></a><a name="null"></a> SID:: null

SECURITY_NULL_RID SID döndürür.

```
CSid Null() throw(...);
```

## <a name="sidsprew2kaccess"></a><a name="prew2kaccess"></a> SID 'ler::P reW2KAccess

DOMAIN_ALIAS_RID_PREW2KCOMPACCESS SID döndürür.

```
CSid PreW2KAccess() throw(...);
```

## <a name="sidspowerusers"></a><a name="powerusers"></a> SID 'ler: owerUsers:P

DOMAIN_ALIAS_RID_POWER_USERS SID döndürür.

```
CSid PowerUsers() throw(...);
```

## <a name="sidsprintops"></a><a name="printops"></a> SID 'ler::P Rin

DOMAIN_ALIAS_RID_PRINT_OPS SID döndürür.

```
CSid PrintOps() throw(...);
```

## <a name="sidsproxy"></a><a name="proxy"></a> SID 'ler::P Roxy

SECURITY_PROXY_RID SID döndürür.

```
CSid Proxy() throw(...);
```

## <a name="sidsrasservers"></a><a name="rasservers"></a> SID 'ler:: RasServers

DOMAIN_ALIAS_RID_RAS_SERVERS SID döndürür.

```
CSid RasServers() throw(...);
```

## <a name="sidsreplicator"></a><a name="replicator"></a> SID 'ler:: çoğaltıcı

DOMAIN_ALIAS_RID_REPLICATOR SID döndürür.

```
CSid Replicator() throw(...);
```

## <a name="sidsrestrictedcode"></a><a name="restrictedcode"></a> SID 'ler:: Kısıttedcode

SECURITY_RESTRICTED_CODE_RID SID döndürür.

```
CSid RestrictedCode() throw(...);
```

## <a name="sidsself"></a><a name="self"></a> SID 'ler:: Self

SECURITY_PRINCIPAL_SELF_RID SID döndürür.

```
CSid Self() throw(...);
```

## <a name="sidsserverlogon"></a><a name="serverlogon"></a> SID 'ler:: ServerLogon

SECURITY_SERVER_LOGON_RID SID döndürür.

```
CSid ServerLogon() throw(...);
```

## <a name="sidsservice"></a><a name="service"></a> SID:: Service

SECURITY_SERVICE_RID SID döndürür.

```
CSid Service() throw(...);
```

## <a name="sidssystem"></a><a name="system"></a> SID 'ler:: System

SECURITY_LOCAL_SYSTEM_RID SID döndürür.

```
CSid System() throw(...);
```

## <a name="sidssystemops"></a><a name="systemops"></a> SID 'ler:: SystemOps

DOMAIN_ALIAS_RID_SYSTEM_OPS SID döndürür.

```
CSid SystemOps() throw(...);
```

## <a name="sidsterminalserver"></a><a name="terminalserver"></a> SID 'ler:: TerminalServer

SECURITY_TERMINAL_SERVER_RID SID döndürür.

```
CSid TerminalServer() throw(...);
```

## <a name="sidsusers"></a><a name="users"></a> SID 'ler:: kullanıcılar

DOMAIN_ALIAS_RID_USERS SID döndürür.

```
CSid Users() throw(...);
```

## <a name="sidsworld"></a><a name="world"></a> SID 'ler:: World

SECURITY_WORLD_RID SID döndürür.

```
CSid World() throw(...);
```

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../../atl/reference/atl-functions.md)
