---
title: Güvenlik tanımlayıcısı genel işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- security IDs [C++]
- SIDs [C++], returning SID objects
ms.assetid: 85404dcb-c59b-4535-ab3d-66cfa37e87de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 74836c06e4ff7a9188c9886087502ad4909aebf0
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43762420"
---
# <a name="security-identifier-global-functions"></a>Güvenlik tanımlayıcısı genel işlevleri

Bu işlevler, nesneler ortak iyi bilinen SID döndürür.

> [!IMPORTANT]
>  Aşağıdaki tabloda listelenen İşlevler, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

|||
|-|-|
|[Sids::AccountOps](#accountops)|DOMAIN_ALIAS_RID_ACCOUNT_OPS SID döndürür.|
|[Sids::Admins](#admins)|DOMAIN_ALIAS_RID_ADMINS SID döndürür.|
|[Sids::AnonymousLogon](#anonymouslogon)|SECURITY_ANONYMOUS_LOGON_RID SID döndürür.|
|[Sids::AuthenticatedUser](#authenticateduser)|SECURITY_AUTHENTICATED_USER_RID SID döndürür.|
|[Sids::BackupOps](#backupops)|DOMAIN_ALIAS_RID_BACKUP_OPS SID döndürür.|
|[Sids::batch](#batch)|SECURITY_BATCH_RID SID döndürür.|
|[Sids::CreatorGroup](#creatorgroup)|SECURITY_CREATOR_GROUP_RID SID döndürür.|
|[Sids::CreatorGroupServer](#creatorgroupserver)|SECURITY_CREATOR_GROUP_SERVER_RID SID döndürür.|
|[Sids::CreatorOwner](#creatorowner)|SECURITY_CREATOR_OWNER_RID SID döndürür.|
|[Sids::CreatorOwnerServer](#creatorownerserver)|SECURITY_CREATOR_OWNER_SERVER_RID SID döndürür.|
|[Sids::dialup](#dialup)|SECURITY_DIALUP_RID SID döndürür.|
|[Sids::Guests](#guests)|DOMAIN_ALIAS_RID_GUESTS SID döndürür.|
|[Sids::Interactive](#interactive)|SECURITY_INTERACTIVE_RID SID döndürür.|
|[Sids::Local](#local)|SECURITY_LOCAL_RID SID döndürür.|
|[Sids::Network](#network)|SECURITY_NETWORK_RID SID döndürür.|
|[Sids::NetworkService](#networkservice)|SECURITY_NETWORK_SERVICE_RID SID döndürür.|
|[Sids::null](#null)|SECURITY_NULL_RID SID döndürür.|
|[Sids::PreW2KAccess](#prew2kaccess)|DOMAIN_ALIAS_RID_PREW2KCOMPACCESS SID döndürür.|
|[Sids::PowerUsers](#powerusers)|DOMAIN_ALIAS_RID_POWER_USERS SID döndürür.|
|[Sids::PrintOps](#printops)|DOMAIN_ALIAS_RID_PRINT_OPS SID döndürür.|
|[Sids::proxy](#proxy)|SECURITY_PROXY_RID SID döndürür.|
|[Sids::RasServers](#rasservers)|DOMAIN_ALIAS_RID_RAS_SERVERS SID döndürür.|
|[Sids::Replicator](#replicator)|DOMAIN_ALIAS_RID_REPLICATOR SID döndürür.|
|[Sids::RestrictedCode](#restrictedcode)|SECURITY_RESTRICTED_CODE_RID SID döndürür.|
|[Sids::Self](#self)|SECURITY_PRINCIPAL_SELF_RID SID döndürür.|
|[Sids::ServerLogon](#serverlogon)|SECURITY_SERVER_LOGON_RID SID döndürür.|
|[Sids::Service](#service)|SECURITY_SERVICE_RID SID döndürür.|
|[Sids::System](#system)|SECURITY_LOCAL_SYSTEM_RID SID döndürür.|
|[Sids::SystemOps](#systemops)|DOMAIN_ALIAS_RID_SYSTEM_OPS SID döndürür.|
|[Sids::TerminalServer](#terminalserver)|SECURITY_TERMINAL_SERVER_RID SID döndürür.|
|[Sids::Users](#users)|DOMAIN_ALIAS_RID_USERS SID döndürür.|
|[Sids::World](#world)|SECURITY_WORLD_RID SID döndürür.|  

### <a name="requirements"></a>Gereksinimler

**Başlık:** atlsecurity.h 

##  <a name="accountops"></a>  Sids::AccountOps

DOMAIN_ALIAS_RID_ACCOUNT_OPS SID döndürür.

```
CSid AccountOps() throw(...);
```

##  <a name="admins"></a>  Sids::Admins

DOMAIN_ALIAS_RID_ADMINS SID döndürür.  
```
CSid Admins() throw(...);
```

##  <a name="anonymouslogon"></a>  Sids::AnonymousLogon

SECURITY_ANONYMOUS_LOGON_RID SID döndürür.  
```
CSid AnonymousLogon() throw(...);
```

##  <a name="authenticateduser"></a>  Sids::AuthenticatedUser

SECURITY_AUTHENTICATED_USER_RID SID döndürür.  
```
CSid AuthenticatedUser() throw(...);
```

##  <a name="backupops"></a>  Sids::BackupOps

DOMAIN_ALIAS_RID_BACKUP_OPS SID döndürür.  
```
CSid BackupOps() throw(...);
```

##  <a name="batch"></a>  Sids::batch

SECURITY_BATCH_RID SID döndürür.  
```
CSid Batch() throw(...);
```

##  <a name="creatorgroup"></a>  Sids::CreatorGroup

SECURITY_CREATOR_GROUP_RID SID döndürür.  
```
CSid CreatorGroup() throw(...);
```

##  <a name="creatorgroupserver"></a>  Sids::CreatorGroupServer

SECURITY_CREATOR_GROUP_SERVER_RID SID döndürür.  
```
CSid CreatorGroupServer() throw(...);
```

##  <a name="creatorowner"></a>  Sids::CreatorOwner

SECURITY_CREATOR_OWNER_RID SID döndürür.  
```
CSid CreatorOwner() throw(...);
```

##  <a name="creatorownerserver"></a>  Sids::CreatorOwnerServer

SECURITY_CREATOR_OWNER_SERVER_RID SID döndürür.  
```
CSid CreatorOwnerServer() throw(...);
```

##  <a name="dialup"></a>  Sids::dialup

SECURITY_DIALUP_RID SID döndürür.  
```
CSid Dialup() throw(...);
```

##  <a name="guests"></a>  Sids::Guests

DOMAIN_ALIAS_RID_GUESTS SID döndürür.  
```
CSid Guests() throw(...);
```

##  <a name="interactive"></a>  Sids::Interactive

SECURITY_INTERACTIVE_RID SID döndürür.  
```
CSid Interactive() throw(...);
```

##  <a name="local"></a>  Sids::Local

SECURITY_LOCAL_RID SID döndürür.  
```
CSid Local() throw(...);
```

##  <a name="network"></a>  Sids::Network

SECURITY_NETWORK_RID SID döndürür.  
```
CSid Network() throw(...);
```

##  <a name="networkservice"></a>  Sids::NetworkService

SECURITY_NETWORK_SERVICE_RID SID döndürür.  
```
CSid NetworkService() throw(...);
```

### <a name="remarks"></a>Açıklamalar

NetworkService CPerfMon güvenlik nesnesine okumak NT AUTHORITY\NetworkService kullanıcı etkinleştirmek için kullanın. NetworkService bir SecurityAttribute DLL Windows XP Home Edition, Windows XP Professional, Windows Server 2003 ve büyük işletim sistemi NetworkService hesabı altında oturum açmak için izin veren ATLServer kodu ekler.

Özel günlük sayaçları Perfmon MMC'de ATLServer CPerfMon sınıfı ile oluşturulduğunda sayaçları gerçek zamanlı Görünümü'nde doğru görünür ancak günlük dosyasını görüntülerken görünmeyebilir. Özel performans Sayaçlarınızı CPerfMon (smlogsvc.exe) "Performans Günlükleri ve Uyarıları" hizmetinin altında Windows XP Home Edition, Windows XP Professional, Windows Server 2003 (veya üstü) işletim sistemlerini çalıştıran için gerekli izniniz yok. Bu hizmet "NT AUTHORITY\NetworkService" hesabı altında çalışır.

##  <a name="null"></a>  Sids::null

SECURITY_NULL_RID SID döndürür.  
```
CSid Null() throw(...);
```

##  <a name="prew2kaccess"></a>  Sids::PreW2KAccess

DOMAIN_ALIAS_RID_PREW2KCOMPACCESS SID döndürür.  
```
CSid PreW2KAccess() throw(...);
```

##  <a name="powerusers"></a>  Sids::PowerUsers

DOMAIN_ALIAS_RID_POWER_USERS SID döndürür.  
```
CSid PowerUsers() throw(...);
```

##  <a name="printops"></a>  Sids::PrintOps

DOMAIN_ALIAS_RID_PRINT_OPS SID döndürür.  
```
CSid PrintOps() throw(...);
```

##  <a name="proxy"></a>  Sids::proxy

SECURITY_PROXY_RID SID döndürür.  
```
CSid Proxy() throw(...);
```

##  <a name="rasservers"></a>  Sids::RasServers

DOMAIN_ALIAS_RID_RAS_SERVERS SID döndürür.  
```
CSid RasServers() throw(...);
```

##  <a name="replicator"></a>  Sids::Replicator

DOMAIN_ALIAS_RID_REPLICATOR SID döndürür.  
```
CSid Replicator() throw(...);
```

##  <a name="restrictedcode"></a>  Sids::RestrictedCode

SECURITY_RESTRICTED_CODE_RID SID döndürür.  
```
CSid RestrictedCode() throw(...);
```

##  <a name="self"></a>  Sids::Self

SECURITY_PRINCIPAL_SELF_RID SID döndürür.  
```
CSid Self() throw(...);
```

##  <a name="serverlogon"></a>  Sids::ServerLogon

SECURITY_SERVER_LOGON_RID SID döndürür.  
```
CSid ServerLogon() throw(...);
```

##  <a name="service"></a>  Sids::Service

SECURITY_SERVICE_RID SID döndürür.  
```
CSid Service() throw(...);
```

##  <a name="system"></a>  Sids::System

SECURITY_LOCAL_SYSTEM_RID SID döndürür.  
```
CSid System() throw(...);
```

##  <a name="systemops"></a>  Sids::SystemOps

DOMAIN_ALIAS_RID_SYSTEM_OPS SID döndürür.  
```
CSid SystemOps() throw(...);
```

##  <a name="terminalserver"></a>  Sids::TerminalServer

SECURITY_TERMINAL_SERVER_RID SID döndürür.  
```
CSid TerminalServer() throw(...);
```

##  <a name="users"></a>  Sids::Users

DOMAIN_ALIAS_RID_USERS SID döndürür.  
```
CSid Users() throw(...);
```

##  <a name="world"></a>  Sids::World

SECURITY_WORLD_RID SID döndürür.  
```
CSid World() throw(...);
```

## <a name="see-also"></a>Ayrıca Bkz.

[İşlevler](../../atl/reference/atl-functions.md)
