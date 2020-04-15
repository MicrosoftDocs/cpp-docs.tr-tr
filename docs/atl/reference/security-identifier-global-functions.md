---
title: Güvenlik Tanımlayıcısı Genel İşlevleri
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
ms.openlocfilehash: 83326c13de7585806ab841f728f587f1131b5e8d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325989"
---
# <a name="security-identifier-global-functions"></a>Güvenlik Tanımlayıcısı Genel İşlevleri

Bu işlevler, yaygın olarak bilinen SID nesnelerini döndürer.

> [!IMPORTANT]
> Aşağıdaki tabloda listelenen işlevler Windows Runtime'da çalışan uygulamalarda kullanılamaz.

|||
|-|-|
|[Sids::AccountOps](#accountops)|DOMAIN_ALIAS_RID_ACCOUNT_OPS SID döndürür.|
|[Sids::Yöneticiler](#admins)|DOMAIN_ALIAS_RID_ADMINS SID döndürür.|
|[Sids::AnonimLogon](#anonymouslogon)|SECURITY_ANONYMOUS_LOGON_RID SID döndürür.|
|[Sids::AuthenticatedUser](#authenticateduser)|SECURITY_AUTHENTICATED_USER_RID SID döndürür.|
|[Sids::BackupOps](#backupops)|DOMAIN_ALIAS_RID_BACKUP_OPS SID döndürür.|
|[Sids::Toplu](#batch)|SECURITY_BATCH_RID SID döndürür.|
|[Sids::CreatorGroup](#creatorgroup)|SECURITY_CREATOR_GROUP_RID SID döndürür.|
|[Sids::CreatorGroupServer](#creatorgroupserver)|SECURITY_CREATOR_GROUP_SERVER_RID SID döndürür.|
|[Sids::CreatorOwner](#creatorowner)|SECURITY_CREATOR_OWNER_RID SID döndürür.|
|[Sids::CreatorOwnerServer](#creatorownerserver)|SECURITY_CREATOR_OWNER_SERVER_RID SID döndürür.|
|[Sids::Dialup](#dialup)|SECURITY_DIALUP_RID SID döndürür.|
|[Sids::Misafirler](#guests)|SIDDOMAIN_ALIAS_RID_GUESTS döndürür.|
|[Sids::Etkileşimli](#interactive)|SECURITY_INTERACTIVE_RID SID döndürür.|
|[Sids::Yerel](#local)|SECURITY_LOCAL_RID SID döndürür.|
|[Sids::Ağ](#network)|SECURITY_NETWORK_RID SID döndürür.|
|[Sids::NetworkService](#networkservice)|SECURITY_NETWORK_SERVICE_RID SID döndürür.|
|[Sids::Null](#null)|SECURITY_NULL_RID SID döndürür.|
|[Sids::PreW2KAccess](#prew2kaccess)|DOMAIN_ALIAS_RID_PREW2KCOMPACCESS SID döndürür.|
|[Sids::PowerKullanıcılar](#powerusers)|DOMAIN_ALIAS_RID_POWER_USERS SID döndürür.|
|[Sids::PrintOps](#printops)|DOMAIN_ALIAS_RID_PRINT_OPS SID döndürür.|
|[Sids::Proxy](#proxy)|SECURITY_PROXY_RID SID döndürür.|
|[Sids::RasServers](#rasservers)|DOMAIN_ALIAS_RID_RAS_SERVERS SID döndürür.|
|[Sids::Çoğaltıcı](#replicator)|DOMAIN_ALIAS_RID_REPLICATOR SID döndürür.|
|[Sids::RestrictedCode](#restrictedcode)|SECURITY_RESTRICTED_CODE_RID SID döndürür.|
|[Sids::Benlik](#self)|SECURITY_PRINCIPAL_SELF_RID SID döndürür.|
|[Sids::ServerLogon](#serverlogon)|SECURITY_SERVER_LOGON_RID SID döndürür.|
|[Sids::Servis](#service)|SECURITY_SERVICE_RID SID döndürür.|
|[Sids::Sistem](#system)|SECURITY_LOCAL_SYSTEM_RID SID döndürür.|
|[Sids::SystemOps](#systemops)|DOMAIN_ALIAS_RID_SYSTEM_OPS SID döndürür.|
|[Sids::TerminalServer](#terminalserver)|SECURITY_TERMINAL_SERVER_RID SID döndürür.|
|[Sids::Kullanıcılar](#users)|DOMAIN_ALIAS_RID_USERS SID döndürür.|
|[Sids::Dünya](#world)|SECURITY_WORLD_RID SID döndürür.|

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity.h

## <a name="sidsaccountops"></a><a name="accountops"></a>Sids::AccountOps

DOMAIN_ALIAS_RID_ACCOUNT_OPS SID döndürür.

```
CSid AccountOps() throw(...);
```

## <a name="sidsadmins"></a><a name="admins"></a>Sids::Yöneticiler

DOMAIN_ALIAS_RID_ADMINS SID döndürür.

```
CSid Admins() throw(...);
```

## <a name="sidsanonymouslogon"></a><a name="anonymouslogon"></a>Sids::AnonimLogon

SECURITY_ANONYMOUS_LOGON_RID SID döndürür.

```
CSid AnonymousLogon() throw(...);
```

## <a name="sidsauthenticateduser"></a><a name="authenticateduser"></a>Sids::AuthenticatedUser

SECURITY_AUTHENTICATED_USER_RID SID döndürür.

```
CSid AuthenticatedUser() throw(...);
```

## <a name="sidsbackupops"></a><a name="backupops"></a>Sids::BackupOps

DOMAIN_ALIAS_RID_BACKUP_OPS SID döndürür.

```
CSid BackupOps() throw(...);
```

## <a name="sidsbatch"></a><a name="batch"></a>Sids::Toplu

SECURITY_BATCH_RID SID döndürür.

```
CSid Batch() throw(...);
```

## <a name="sidscreatorgroup"></a><a name="creatorgroup"></a>Sids::CreatorGroup

SECURITY_CREATOR_GROUP_RID SID döndürür.

```
CSid CreatorGroup() throw(...);
```

## <a name="sidscreatorgroupserver"></a><a name="creatorgroupserver"></a>Sids::CreatorGroupServer

SECURITY_CREATOR_GROUP_SERVER_RID SID döndürür.

```
CSid CreatorGroupServer() throw(...);
```

## <a name="sidscreatorowner"></a><a name="creatorowner"></a>Sids::CreatorOwner

SECURITY_CREATOR_OWNER_RID SID döndürür.

```
CSid CreatorOwner() throw(...);
```

## <a name="sidscreatorownerserver"></a><a name="creatorownerserver"></a>Sids::CreatorOwnerServer

SECURITY_CREATOR_OWNER_SERVER_RID SID döndürür.

```
CSid CreatorOwnerServer() throw(...);
```

## <a name="sidsdialup"></a><a name="dialup"></a>Sids::Dialup

SECURITY_DIALUP_RID SID döndürür.

```
CSid Dialup() throw(...);
```

## <a name="sidsguests"></a><a name="guests"></a>Sids::Misafirler

SIDDOMAIN_ALIAS_RID_GUESTS döndürür.

```
CSid Guests() throw(...);
```

## <a name="sidsinteractive"></a><a name="interactive"></a>Sids::Etkileşimli

SECURITY_INTERACTIVE_RID SID döndürür.

```
CSid Interactive() throw(...);
```

## <a name="sidslocal"></a><a name="local"></a>Sids::Yerel

SECURITY_LOCAL_RID SID döndürür.

```
CSid Local() throw(...);
```

## <a name="sidsnetwork"></a><a name="network"></a>Sids::Ağ

SECURITY_NETWORK_RID SID döndürür.

```
CSid Network() throw(...);
```

## <a name="sidsnetworkservice"></a><a name="networkservice"></a>Sids::NetworkService

SECURITY_NETWORK_SERVICE_RID SID döndürür.

```
CSid NetworkService() throw(...);
```

### <a name="remarks"></a>Açıklamalar

NT AUTHORITY\NetworkService kullanıcısının bir CPerfMon güvenlik nesnesini okumasını sağlamak için NetworkService'i kullanın. NetworkService, DLL'nin Windows XP Home Edition, Windows XP Professional, Windows Server 2003 ve daha fazla işletim sisteminde NetworkService hesabı altında oturum açmasına olanak tanıyan ATLServer koduna bir SecurityAttribute ekler.

Perfmon MMC'de ATLServer CPerfMon sınıfıyla özel günlük sayaçları oluşturulduğunda, günlük dosyasını görüntülerken sayaçlar görünmeyebilir, ancak gerçek zamanlı görünümde doğru görünürler. CPerfMon özel performans sayaçları Windows XP Home Edition, Windows XP Professional, Windows Server 2003 (veya daha büyük) işletim sistemlerinde "Performans Günlükleri ve Uyarıları" hizmeti (smlogsvc.exe) altında çalıştırmak için gerekli izinlere sahip değildir. Bu hizmet "NT AUTHORITY\NetworkService" hesabı altında çalışır.

## <a name="sidsnull"></a><a name="null"></a>Sids::Null

SECURITY_NULL_RID SID döndürür.

```
CSid Null() throw(...);
```

## <a name="sidsprew2kaccess"></a><a name="prew2kaccess"></a>Sids::PreW2KAccess

DOMAIN_ALIAS_RID_PREW2KCOMPACCESS SID döndürür.

```
CSid PreW2KAccess() throw(...);
```

## <a name="sidspowerusers"></a><a name="powerusers"></a>Sids::PowerKullanıcılar

DOMAIN_ALIAS_RID_POWER_USERS SID döndürür.

```
CSid PowerUsers() throw(...);
```

## <a name="sidsprintops"></a><a name="printops"></a>Sids::PrintOps

DOMAIN_ALIAS_RID_PRINT_OPS SID döndürür.

```
CSid PrintOps() throw(...);
```

## <a name="sidsproxy"></a><a name="proxy"></a>Sids::Proxy

SECURITY_PROXY_RID SID döndürür.

```
CSid Proxy() throw(...);
```

## <a name="sidsrasservers"></a><a name="rasservers"></a>Sids::RasServers

DOMAIN_ALIAS_RID_RAS_SERVERS SID döndürür.

```
CSid RasServers() throw(...);
```

## <a name="sidsreplicator"></a><a name="replicator"></a>Sids::Çoğaltıcı

DOMAIN_ALIAS_RID_REPLICATOR SID döndürür.

```
CSid Replicator() throw(...);
```

## <a name="sidsrestrictedcode"></a><a name="restrictedcode"></a>Sids::RestrictedCode

SECURITY_RESTRICTED_CODE_RID SID döndürür.

```
CSid RestrictedCode() throw(...);
```

## <a name="sidsself"></a><a name="self"></a>Sids::Benlik

SECURITY_PRINCIPAL_SELF_RID SID döndürür.

```
CSid Self() throw(...);
```

## <a name="sidsserverlogon"></a><a name="serverlogon"></a>Sids::ServerLogon

SECURITY_SERVER_LOGON_RID SID döndürür.

```
CSid ServerLogon() throw(...);
```

## <a name="sidsservice"></a><a name="service"></a>Sids::Servis

SECURITY_SERVICE_RID SID döndürür.

```
CSid Service() throw(...);
```

## <a name="sidssystem"></a><a name="system"></a>Sids::Sistem

SECURITY_LOCAL_SYSTEM_RID SID döndürür.

```
CSid System() throw(...);
```

## <a name="sidssystemops"></a><a name="systemops"></a>Sids::SystemOps

DOMAIN_ALIAS_RID_SYSTEM_OPS SID döndürür.

```
CSid SystemOps() throw(...);
```

## <a name="sidsterminalserver"></a><a name="terminalserver"></a>Sids::TerminalServer

SECURITY_TERMINAL_SERVER_RID SID döndürür.

```
CSid TerminalServer() throw(...);
```

## <a name="sidsusers"></a><a name="users"></a>Sids::Kullanıcılar

DOMAIN_ALIAS_RID_USERS SID döndürür.

```
CSid Users() throw(...);
```

## <a name="sidsworld"></a><a name="world"></a>Sids::Dünya

SECURITY_WORLD_RID SID döndürür.

```
CSid World() throw(...);
```

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../../atl/reference/atl-functions.md)
