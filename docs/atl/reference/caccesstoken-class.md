---
title: CAccessToken sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAccessToken
- ATLSECURITY/ATL::CAccessToken
- ATLSECURITY/ATL::CAccessToken::Attach
- ATLSECURITY/ATL::CAccessToken::CheckTokenMembership
- ATLSECURITY/ATL::CAccessToken::CreateImpersonationToken
- ATLSECURITY/ATL::CAccessToken::CreatePrimaryToken
- ATLSECURITY/ATL::CAccessToken::CreateProcessAsUser
- ATLSECURITY/ATL::CAccessToken::CreateRestrictedToken
- ATLSECURITY/ATL::CAccessToken::Detach
- ATLSECURITY/ATL::CAccessToken::DisablePrivilege
- ATLSECURITY/ATL::CAccessToken::DisablePrivileges
- ATLSECURITY/ATL::CAccessToken::EnablePrivilege
- ATLSECURITY/ATL::CAccessToken::EnablePrivileges
- ATLSECURITY/ATL::CAccessToken::GetDefaultDacl
- ATLSECURITY/ATL::CAccessToken::GetEffectiveToken
- ATLSECURITY/ATL::CAccessToken::GetGroups
- ATLSECURITY/ATL::CAccessToken::GetHandle
- ATLSECURITY/ATL::CAccessToken::GetImpersonationLevel
- ATLSECURITY/ATL::CAccessToken::GetLogonSessionId
- ATLSECURITY/ATL::CAccessToken::GetLogonSid
- ATLSECURITY/ATL::CAccessToken::GetOwner
- ATLSECURITY/ATL::CAccessToken::GetPrimaryGroup
- ATLSECURITY/ATL::CAccessToken::GetPrivileges
- ATLSECURITY/ATL::CAccessToken::GetProcessToken
- ATLSECURITY/ATL::CAccessToken::GetProfile
- ATLSECURITY/ATL::CAccessToken::GetSource
- ATLSECURITY/ATL::CAccessToken::GetStatistics
- ATLSECURITY/ATL::CAccessToken::GetTerminalServicesSessionId
- ATLSECURITY/ATL::CAccessToken::GetThreadToken
- ATLSECURITY/ATL::CAccessToken::GetTokenId
- ATLSECURITY/ATL::CAccessToken::GetType
- ATLSECURITY/ATL::CAccessToken::GetUser
- ATLSECURITY/ATL::CAccessToken::HKeyCurrentUser
- ATLSECURITY/ATL::CAccessToken::Impersonate
- ATLSECURITY/ATL::CAccessToken::ImpersonateLoggedOnUser
- ATLSECURITY/ATL::CAccessToken::IsTokenRestricted
- ATLSECURITY/ATL::CAccessToken::LoadUserProfile
- ATLSECURITY/ATL::CAccessToken::LogonUser
- ATLSECURITY/ATL::CAccessToken::OpenCOMClientToken
- ATLSECURITY/ATL::CAccessToken::OpenNamedPipeClientToken
- ATLSECURITY/ATL::CAccessToken::OpenRPCClientToken
- ATLSECURITY/ATL::CAccessToken::OpenThreadToken
- ATLSECURITY/ATL::CAccessToken::PrivilegeCheck
- ATLSECURITY/ATL::CAccessToken::Revert
- ATLSECURITY/ATL::CAccessToken::SetDefaultDacl
- ATLSECURITY/ATL::CAccessToken::SetOwner
- ATLSECURITY/ATL::CAccessToken::SetPrimaryGroup
dev_langs:
- C++
helpviewer_keywords:
- CAccessToken class
ms.assetid: bb5c5945-56a5-4083-b442-76573cee83ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 881c86a75d9015117be4b51a8b7457bed4988fd3
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50078550"
---
# <a name="caccesstoken-class"></a>CAccessToken sınıfı

Bir erişim belirteci için bir sarmalayıcı sınıftır.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CAccessToken
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAccessToken:: ~ CAccessToken](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAccessToken::Attach](#attach)|Belirli bir erişim belirteci işleyici sahipliğini almak için bu yöntemi çağırın.|
|[CAccessToken::CheckTokenMembership](#checktokenmembership)|Belirtilen SID içinde etkin olup olmadığını belirlemek için bu yöntemi çağırın `CAccessToken` nesne.|
|[CAccessToken::CreateImpersonationToken](#createimpersonationtoken)|Yeni bir kimliğe bürünme erişim belirteci oluşturmak için bu yöntemi çağırın.|
|[CAccessToken::CreatePrimaryToken](#createprimarytoken)|Yeni bir birincil belirteç oluşturmak için bu yöntemi çağırın.|
|[CAccessToken::CreateProcessAsUser](#createprocessasuser)|Tarafından temsil edilen kullanıcı güvenlik bağlamında çalışan yeni bir işlem oluşturmak için bu yöntemi çağırın `CAccessToken` nesne.|
|[CAccessToken::CreateRestrictedToken](#createrestrictedtoken)|Yeni, oluşturmak için bu yöntemi çağırın kısıtlı `CAccessToken` nesne.|
|[CAccessToken::Detach](#detach)|Erişim belirteci sahipliğini iptal etmek için bu yöntemi çağırın.|
|[CAccessToken::DisablePrivilege](#disableprivilege)|Bir ayrıcalık devre dışı bırakmak için bu yöntemi çağırın `CAccessToken` nesne.|
|[CAccessToken::DisablePrivileges](#disableprivileges)|Bir veya daha fazla ayrıcalık devre dışı bırakmak için bu yöntemi çağırın `CAccessToken` nesne.|
|[CAccessToken::EnablePrivilege](#enableprivilege)|Bir ayrıcalık etkinleştirmek için bu yöntemi çağırın `CAccessToken` nesne.|
|[CAccessToken::EnablePrivileges](#enableprivileges)|Bir veya daha fazla ayrıcalık etkinleştirmek için bu yöntemi çağırın `CAccessToken` nesne.|
|[CAccessToken::GetDefaultDacl](#getdefaultdacl)|Döndürmek için bu yöntemi çağırın `CAccessToken` nesnenin varsayılan DACL.|
|[CAccessToken::GetEffectiveToken](#geteffectivetoken)|Almak için bu yöntemi çağırın `CAccessToken` nesne geçerli iş parçacığı için geçerli erişim belirteci eşittir.|
|[CAccessToken::GetGroups](#getgroups)|Döndürmek için bu yöntemi çağırın `CAccessToken` nesnesinin belirteç grupları.|
|[CAccessToken::GetHandle](#gethandle)|İşleyici erişim belirteci almak için bu yöntemi çağırın.|
|[CAccessToken::GetImpersonationLevel](#getimpersonationlevel)|Kimliğe bürünme düzeyi erişim belirteci almak için bu yöntemi çağırın.|
|[CAccessToken::GetLogonSessionId](#getlogonsessionid)|İlişkili oturum açma oturumu Kimliği almak için bu yöntemi çağırın `CAccessToken` nesne.|
|[CAccessToken::GetLogonSid](#getlogonsid)|İlişkili oturum açma SID almak için bu yöntemi çağırın `CAccessToken` nesne.|
|[CAccessToken::GetOwner](#getowner)|İle ilişkili sahibini almak için bu yöntemi çağırın `CAccessToken` nesne.|
|[CAccessToken::GetPrimaryGroup](#getprimarygroup)|İlişkili birincil grubu almak için bu yöntemi çağırın `CAccessToken` nesne.|
|[CAccessToken::GetPrivileges](#getprivileges)|İle ilişkili ayrıcalıklar almak için bu yöntemi çağırın `CAccessToken` nesne.|
|[CAccessToken::GetProcessToken](#getprocesstoken)|Başlatmak için bu yöntemi çağırın `CAccessToken` verilen işlemdeki erişim belirteci ile.|
|[CAccessToken::GetProfile](#getprofile)|İle ilişkili kullanıcı profili işaret tanıtıcı almak için bu yöntemi çağırın `CAccessToken` nesne.|
|[CAccessToken::GetSource](#getsource)|Kaynağını almak için bu yöntemi çağırın `CAccessToken` nesne.|
|[CAccessToken::GetStatistics](#getstatistics)|İle ilgili bilgi almak için bu yöntemi çağırın `CAccessToken` nesne.|
|[CAccessToken::GetTerminalServicesSessionId](#getterminalservicessessionid)|Terminal Hizmetleri oturum kimliği ile ilişkili almak için bu yöntemi çağırın `CAccessToken` nesne.|
|[CAccessToken::GetThreadToken](#getthreadtoken)|Başlatmak için bu yöntemi çağırın `CAccessToken` belirtilen iş parçacığından belirtecine sahip.|
|[CAccessToken::GetTokenId](#gettokenid)|Belirteç ile ilişkili Kimliği almak için bu yöntemi çağırın `CAccessToken` nesne.|
|[CAccessToken::GetType](#gettype)|Belirteç türünü almak için bu yöntemi çağırın `CAccessToken` nesne.|
|[CAccessToken::GetUser](#getuser)|İle ilişkili kullanıcıyı tanımlamak için bu yöntemi çağırın `CAccessToken` nesne.|
|[CAccessToken::HKeyCurrentUser](#hkeycurrentuser)|İle ilişkili kullanıcı profili işaret tanıtıcı almak için bu yöntemi çağırın `CAccessToken` nesne.|
|[CAccessToken::Impersonate](#impersonate)|Bir kimliğe bürünme atamak için bu yöntemi çağırın `CAccessToken` bir iş parçacığına.|
|[CAccessToken::ImpersonateLoggedOnUser](#impersonateloggedonuser)|Güvenlik bağlamı bir oturum açan kullanıcının kimliğine bürünmek çağıran iş parçacığına izin vermek için bu yöntemi çağırın.|
|[CAccessToken::IsTokenRestricted](#istokenrestricted)|Test için bu yöntemi çağırın `CAccessToken` nesne kısıtlı SID bir listesini içerir.|
|[CAccessToken::LoadUserProfile](#loaduserprofile)|İle ilişkili kullanıcı profili yüklemek için bu yöntemi çağıran `CAccessToken` nesne.|
|[CAccessToken::LogonUser](#logonuser)|Verilen kimlik bilgileriyle ilişkili kullanıcı için bir oturum açma oturumu oluşturmak için bu yöntemi çağırın.|
|[CAccessToken::OpenCOMClientToken](#opencomclienttoken)|İşleme başlatmak için bir çağrı bir istemciden bir COM sunucusu bu yöntemi çağırın `CAccessToken` COM istemcisi erişim belirteci ile.|
|[CAccessToken::OpenNamedPipeClientToken](#opennamedpipeclienttoken)|Bir sunucu içinde Bu yöntemden alma isteği başlatmak için bir adlandırılmış kanal üzerinde çağrı `CAccessToken` istemci erişim belirteciyle.|
|[CAccessToken::OpenRPCClientToken](#openrpcclienttoken)|Bir sunucu başlatmak için bir RPC istemcisini bir çağrıdan işleme içinde bu yöntemi çağırın `CAccessToken` istemci erişim belirteciyle.|
|[CAccessToken::OpenThreadToken](#openthreadtoken)|Kimliğe bürünme düzeyini ayarlayın ve ardından başlatmak için bu yöntemi çağırın `CAccessToken` belirtilen iş parçacığından belirtecine sahip.|
|[CAccessToken::PrivilegeCheck](#privilegecheck)|Belirtilen bir ayrıcalık kümesi etkin içinde olup olmadığını belirlemek için bu yöntemi çağırın `CAccessToken` nesne.|
|[CAccessToken::Revert](#revert)|Kimliğe bürünme belirtecini kullanarak bir iş parçacığını durdurmak için bu yöntemi çağırın.|
|[CAccessToken::SetDefaultDacl](#setdefaultdacl)|Varsayılan değer ayarlamak için bu yöntemi çağırın'ın DACL `CAccessToken` nesne.|
|[CAccessToken::SetOwner](#setowner)|Sahibi ayarlamak için bu yöntemi çağırın `CAccessToken` nesne.|
|[CAccessToken::SetPrimaryGroup](#setprimarygroup)|Birincil grup ayarlamak için bu yöntemi çağırın `CAccessToken` nesne.|

## <a name="remarks"></a>Açıklamalar

Bir [erişim belirteci](/windows/desktop/SecAuthZ/access-tokens) bir işlem veya iş parçacığı güvenlik bağlamı açıklayan ve Windows sisteminde oturum açmış her kullanıcı için ayrılan bir nesnedir.

Windows, erişim denetimi modeli için bir giriş için bkz [erişim denetimi](/windows/desktop/SecAuthZ/access-control) Windows SDK.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlsecurity.h

##  <a name="attach"></a>  CAccessToken::Attach

Belirli bir erişim belirteci işleyici sahipliğini almak için bu yöntemi çağırın.

```
void Attach(HANDLE hToken) throw();
```

### <a name="parameters"></a>Parametreler

*hToken*<br/>
Erişim belirteci işleyici.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir `CAccessToken` nesnesi zaten bir erişim belirteci sahipliğini sahiptir.

##  <a name="dtor"></a>  CAccessToken:: ~ CAccessToken

Yıkıcı.

```
virtual ~CAccessToken() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakır.

##  <a name="checktokenmembership"></a>  CAccessToken::CheckTokenMembership

Belirtilen SID içinde etkin olup olmadığını belirlemek için bu yöntemi çağırın `CAccessToken` nesne.

```
bool CheckTokenMembership(
    const CSid& rSid,
    bool* pbIsMember) const throw(...);
```

### <a name="parameters"></a>Parametreler

*rSid*<br/>
Başvuru bir [CSid sınıfı](../../atl/reference/csid-class.md) nesne.

*pbIsMember*<br/>
Sonuçlarını alır bir değişken işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

`CheckTokenMembership` Yöntemi SID kullanıcı ve Grup SID erişim belirtecinin varlığını denetler. SID varsa ve SE_GROUP_ENABLED özniteliğine sahip *pbIsMember* olduğunu ayarlamak için TRUE; tersi durumda FALSE olarak ayarlanır.

Hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir *pbIsMember* geçerli bir işaretçi değil.

> [!NOTE]
>  `CAccessToken` Kimliğe bürünme belirtecini ve bir birincil belirteç nesnesi olması gerekir.

##  <a name="createimpersonationtoken"></a>  CAccessToken::CreateImpersonationToken

Kimliğe bürünme erişim belirteci oluşturmak için bu yöntemi çağırın.

```
bool CreateImpersonationToken(
    CAccessToken* pImp,
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pImp*<br/>
İşaretçi yeni `CAccessToken` nesne.

*Sil*<br/>
Belirtir bir [SECURITY_IMPERSONATION_LEVEL](/windows/desktop/api/winnt/ne-winnt-_security_impersonation_level) listelenmiş yeni belirteç kimliğe bürünme düzeyini sağlayan türü.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

`CreateImpersonationToken` çağrıları [DuplicateToken](https://msdn.microsoft.com/library/windows/desktop/aa446616) yeni bir özellik alma belirteci oluşturmak için.

##  <a name="createprimarytoken"></a>  CAccessToken::CreatePrimaryToken

Yeni bir birincil belirteç oluşturmak için bu yöntemi çağırın.

```
bool CreatePrimaryToken(
    CAccessToken* pPri,
    DWORD dwDesiredAccess = MAXIMUM_ALLOWED,
    const CSecurityAttributes* pTokenAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pPri*<br/>
İşaretçi yeni `CAccessToken` nesne.

*dwDesiredAccess*<br/>
Yeni belirteç için istenen erişim haklarını belirtir. Varsayılan olarak, MAXIMUM_ALLOWED arayan için geçerli olan tüm erişim hakları ister. Bkz: [erişim hakları ve erişim maskesi](/windows/desktop/SecAuthZ/access-rights-and-access-masks) üzerinde daha fazla erişim hakları için.

*pTokenAttributes*<br/>
İşaretçi bir [SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560) yapısı, yeni belirteç için bir güvenlik tanımlayıcısının belirtir ve alt işlemlerin belirteç devralınabilir olup olmadığını belirler. Varsa *pTokenAttributes* NULL, varsayılan bir güvenlik tanımlayıcısı belirteci alır ve tanıtıcı devralınamaz.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

`CreatePrimaryToken` çağrıları [DuplicateTokenEx](https://msdn.microsoft.com/library/windows/desktop/aa446617) yeni bir birincil belirteç oluşturmak için.

##  <a name="createprocessasuser"></a>  CAccessToken::CreateProcessAsUser

Tarafından temsil edilen kullanıcı güvenlik bağlamında çalışan yeni bir işlem oluşturmak için bu yöntemi çağırın `CAccessToken` nesne.

```
bool CreateProcessAsUser(
    LPCTSTR pApplicationName,
    LPTSTR pCommandLine,
    LPPROCESS_INFORMATION pProcessInformation,
    LPSTARTUPINFO pStartupInfo,
    DWORD dwCreationFlags = NORMAL_PRIORITY_CLASS,
    bool bLoadProfile = false,
    const CSecurityAttributes* pProcessAttributes = NULL,
    const CSecurityAttributes* pThreadAttributes = NULL,
    bool bInherit = false,
    LPCTSTR pCurrentDirectory = NULL) throw();
```

### <a name="parameters"></a>Parametreler

*pApplicationName*<br/>
Yürütülecek modülü belirtiyorsa null ile sonlandırılmış bir dize işaretçisi. Bu parametre NULL olamaz.

*pCommandLine*<br/>
Yürütülecek komut satırı belirten bir null ile sonlandırılmış dize işaretçisi.

*pProcessInformation*<br/>
İşaretçi bir [PROCESS_INFORMATION](/windows/desktop/api/processthreadsapi/ns-processthreadsapi-_process_information) yapısı yeni işlem ile ilgili kimlik bilgilerini alır.

*pStartupInfo*<br/>
İşaretçi bir [değeri](/windows/desktop/api/processthreadsapi/ns-processthreadsapi-_startupinfoa) yeni işlemin ana penceresi nasıl görünmelidir belirten yapısı.

*dwCreationFlags*<br/>
Öncelik sınıfı ve işlem oluşturmayı denetleyen ek bayrakları belirtir. Win32 işlevi görmek [CreateProcessAsUser](https://msdn.microsoft.com/library/windows/desktop/ms682429) bayrakların listesi için.

*bLoadProfile*<br/>
TRUE ise, kullanıcının profili ile yüklenir [LoadUserProfile](/windows/desktop/api/userenv/nf-userenv-loaduserprofilea).

*pProcessAttributes*<br/>
İşaretçi bir [SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560) yapısı yeni işlem için bir güvenlik açıklayıcısı belirtir ve döndürülen tanıtıcının alt işlemler devralınabilir olup olmadığını belirler. Varsa *pProcessAttributes* NULL, işlem varsayılan bir güvenlik açıklayıcısı alır ve tanıtıcı devralınamaz.

*pThreadAttributes*<br/>
İşaretçi bir [SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560) yapısı, yeni iş parçacığı için bir güvenlik açıklayıcısı belirtir ve döndürülen tanıtıcının alt işlemler devralınabilir olup olmadığını belirler. Varsa *pThreadAttributes* NULL, iş parçacığı bir varsayılan güvenlik tanımlayıcısını alır ve tanıtıcı devralınamaz.

*bInherit*<br/>
Yeni işlem çağırma işlemden tanıtıcıları devralıp almadığını gösterir. TRUE ise, her devralınabilir açık tanıtıcı çağıran işlemin içinde yeni bir işlem tarafından devralınır. Devralınan tanıtıcıları özgün tanıtıcıları aynı değeri ve erişim ayrıcalıklarına sahiptir.

*pCurrentDirectory*<br/>
Geçerli bir sürücü ve dizini yeni işlemin belirten bir null ile sonlandırılmış dize işaretçisi. Dize, bir sürücü harfi içeren tam bir yol olmalıdır. Bu parametre NULL ise, yeni işlem çağırma işlemi aynı geçerli sürücü ve dizine sahip.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

`CreateProcessAsUser` kullanan `CreateProcessAsUser` tarafından temsil edilen kullanıcı güvenlik bağlamında çalışan yeni bir işlem oluşturmak için Win32 işlevini `CAccessToken` nesne. Açıklamasını görmek [CreateProcessAsUser](https://msdn.microsoft.com/library/windows/desktop/ms682429) Gerekli Parametreler tam bir irdelemesi için işlevi.

Başarılı olması bu yöntemin `CAccessToken` (kısıtlı bir belirteç olmadığı sürece), nesne AssignPrimaryToken tutun gerekir ve IncreaseQuota ayrıcalıkları.

##  <a name="createrestrictedtoken"></a>  CAccessToken::CreateRestrictedToken

Yeni, oluşturmak için bu yöntemi çağırın kısıtlı `CAccessToken` nesne.

```
bool CreateRestrictedToken(
    CAccessToken* pRestrictedToken,
    const CTokenGroups& SidsToDisable,
    const CTokenGroups& SidsToRestrict,
    const CTokenPrivileges& PrivilegesToDelete = CTokenPrivileges()) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pRestrictedToken*<br/>
Yeni, kısıtlı `CAccessToken` nesne.

*SidsToDisable*<br/>
A `CTokenGroups` yalnızca SID belirten bir nesne.

*SidsToRestrict*<br/>
A `CTokenGroups` kısıtlama SID belirten bir nesne.

*PrivilegesToDelete*<br/>
A `CTokenPrivileges` nesnesini silmek için ayrıcalıkları sınırlı belirteci belirtir. Varsayılan değer boş bir nesne oluşturur.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

`CreateRestrictedToken` kullanan [CreateRestrictedToken](https://msdn.microsoft.com/library/windows/desktop/aa446583) yeni bir Win32 işlevini `CAccessToken` kısıtlama nesnesi.

> [!IMPORTANT]
>  Kullanırken `CreateRestrictedToken`, aşağıdaki işlemleri yapmalısınız: mevcut bir belirteç geçerli (ve kullanıcı tarafından girilen) ve *SidsToDisable* ve *PrivilegesToDelete* hem geçerli (hem de kullanıcı tarafından girilen). Yöntem FALSE döndürürse, işlevselliği reddet.

##  <a name="detach"></a>  CAccessToken::Detach

Erişim belirteci sahipliğini iptal etmek için bu yöntemi çağırın.

```
HANDLE Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Tanıtıcısını döndürür `CAccessToken` , ayrılmış.

### <a name="remarks"></a>Açıklamalar

Bu yöntem iptal eder `CAccessToken`'s sahipliğini erişim belirteci.

##  <a name="disableprivilege"></a>  CAccessToken::DisablePrivilege

Bir ayrıcalık devre dışı bırakmak için bu yöntemi çağırın `CAccessToken` nesne.

```
bool DisablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>Parametreler

*pszPrivilege*<br/>
Devre dışı bırakmak için ayrıcalık içeren bir dize işaretçisine `CAccessToken` nesne.

*pPreviousState*<br/>
İşaretçi bir `CTokenPrivileges` ayrıcalıkları önceki durumunu içeren bir nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

##  <a name="disableprivileges"></a>  CAccessToken::DisablePrivileges

Bir veya daha fazla ayrıcalık devre dışı bırakmak için bu yöntemi çağırın `CAccessToken` nesne.

```
bool DisablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>Parametreler

*rPrivileges*<br/>
Bir dizinin devre dışı bırakmak için ayrıcalıkları içeren bir dize işaretçisi `CAccessToken` nesne.

*pPreviousState*<br/>
İşaretçi bir `CTokenPrivileges` ayrıcalıkları önceki durumunu içeren bir nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

##  <a name="enableprivilege"></a>  CAccessToken::EnablePrivilege

Bir ayrıcalık etkinleştirmek için bu yöntemi çağırın `CAccessToken` nesne.

```
bool EnablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>Parametreler

*pszPrivilege*<br/>
Etkinleştirmek için ayrıcalık içeren bir dize işaretçisine `CAccessToken` nesne.

*pPreviousState*<br/>
İşaretçi bir `CTokenPrivileges` ayrıcalıkları önceki durumunu içeren bir nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

##  <a name="enableprivileges"></a>  CAccessToken::EnablePrivileges

Bir veya daha fazla ayrıcalık etkinleştirmek için bu yöntemi çağırın `CAccessToken` nesne.

```
bool EnablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>Parametreler

*rPrivileges*<br/>
Bir dizinin etkinleştirmek için ayrıcalıkları içeren bir dize işaretçisi `CAccessToken` nesne.

*pPreviousState*<br/>
İşaretçi bir `CTokenPrivileges` ayrıcalıkları önceki durumunu içeren bir nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

##  <a name="getdefaultdacl"></a>  CAccessToken::GetDefaultDacl

Döndürmek için bu yöntemi çağırın `CAccessToken` nesnenin varsayılan DACL.

```
bool GetDefaultDacl(CDacl* pDacl) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pDacl*<br/>
İşaretçi [CDacl sınıfı](../../atl/reference/cdacl-class.md) alacak nesne `CAccessToken` nesnenin varsayılan DACL.

### <a name="return-value"></a>Dönüş Değeri

' % S'varsayılan DACL kurtarılan, yanlış Aksi durumda kalıp kalmadığını TRUE döndürür.

##  <a name="geteffectivetoken"></a>  CAccessToken::GetEffectiveToken

Almak için bu yöntemi çağırın `CAccessToken` nesne geçerli iş parçacığı için geçerli erişim belirteci eşittir.

```
bool GetEffectiveToken(DWORD dwDesiredAccess) throw();
```

### <a name="parameters"></a>Parametreler

*dwDesiredAccess*<br/>
İstenen erişim belirtecini erişim türlerini belirten bir erişim maskesi belirtir. Bu istenen erişim türleri, hangi erişimlerin verildiğini veya verilmediğini belirlemek için belirtecin DACL'si ile karşılaştırılır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

##  <a name="getgroups"></a>  CAccessToken::GetGroups

Döndürmek için bu yöntemi çağırın `CAccessToken` nesnesinin belirteç grupları.

```
bool GetGroups(CTokenGroups* pGroups) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pGroups*<br/>
İşaretçi [CTokenGroups sınıfı](../../atl/reference/ctokengroups-class.md) grup bilgilerini alacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

##  <a name="gethandle"></a>  CAccessToken::GetHandle

İşleyici erişim belirteci almak için bu yöntemi çağırın.

```
HANDLE GetHandle() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

İçin bir tanıtıcı döndürür `CAccessToken` nesnenin erişim belirteci.

##  <a name="getimpersonationlevel"></a>  CAccessToken::GetImpersonationLevel

Kimliğe bürünme düzeyi erişim belirteci almak için bu yöntemi çağırın.

```
bool GetImpersonationLevel(
    SECURITY_IMPERSONATION_LEVEL* pImpersonationLevel) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pImpersonationLevel*<br/>
İşaretçi bir [SECURITY_IMPERSONATION_LEVEL](/windows/desktop/api/winnt/ne-winnt-_security_impersonation_level) kimliğe bürünme düzeyi bilgileri alacak numaralandırma türü.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

##  <a name="getlogonsessionid"></a>  CAccessToken::GetLogonSessionId

İlişkili oturum açma oturumu Kimliği almak için bu yöntemi çağırın `CAccessToken` nesne.

```
bool GetLogonSessionId(LUID* pluid) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pluid*<br/>
İşaretçi bir [LUID'ini](/windows/desktop/api/winnt/ns-winnt-_luid) hangi alır oturum açma oturumu kimliği

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir *pluid* geçersiz bir değerdir.

##  <a name="getlogonsid"></a>  CAccessToken::GetLogonSid

İlişkili oturum açma SID almak için bu yöntemi çağırın `CAccessToken` nesne.

```
bool GetLogonSid(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>Parametreler

*Psıd*<br/>
İşaretçi bir [CSid sınıfı](../../atl/reference/csid-class.md) nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir *Psıd* geçersiz bir değerdir.

##  <a name="getowner"></a>  CAccessToken::GetOwner

İle ilişkili sahibini almak için bu yöntemi çağırın `CAccessToken` nesne.

```
bool GetOwner(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>Parametreler

*Psıd*<br/>
İşaretçi bir [CSid sınıfı](../../atl/reference/csid-class.md) nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

Sahip, bu erişim belirtecinin geçerli olduğu sırada oluşturulan tüm nesneler üzerinde varsayılan olarak ayarlanır.

##  <a name="getprimarygroup"></a>  CAccessToken::GetPrimaryGroup

İlişkili birincil grubu almak için bu yöntemi çağırın `CAccessToken` nesne.

```
bool GetPrimaryGroup(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>Parametreler

*Psıd*<br/>
İşaretçi bir [CSid sınıfı](../../atl/reference/csid-class.md) nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

Grup, bu erişim belirtecinin geçerli olduğu sırada oluşturulan tüm nesneler üzerinde varsayılan olarak ayarlanır.

##  <a name="getprivileges"></a>  CAccessToken::GetPrivileges

İle ilişkili ayrıcalıklar almak için bu yöntemi çağırın `CAccessToken` nesne.

```
bool GetPrivileges(CTokenPrivileges* pPrivileges) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pPrivileges*<br/>
İşaretçi bir [CTokenPrivileges sınıfı](../../atl/reference/ctokenprivileges-class.md) ayrıcalıkları alacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

##  <a name="getprocesstoken"></a>  CAccessToken::GetProcessToken

Başlatmak için bu yöntemi çağırın `CAccessToken` verilen işlemdeki erişim belirteci ile.

```
bool GetProcessToken(DWORD dwDesiredAccess, HANDLE hProcess = NULL) throw();
```

### <a name="parameters"></a>Parametreler

*dwDesiredAccess*<br/>
İstenen erişim belirtecini erişim türlerini belirten bir erişim maskesi belirtir. Bu istenen erişim türleri, hangi erişimlerin verildiğini veya verilmediğini belirlemek için belirtecin DACL'si ile karşılaştırılır.

*hProcess*<br/>
Erişim belirteci açık işlem işleyicisi. NULL varsayılan değeri kullanılıyorsa geçerli işlem kullanılır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

Çağrıları [OpenProcessToken](https://msdn.microsoft.com/library/aa379295) Win32 işlevi.

##  <a name="getprofile"></a>  CAccessToken::GetProfile

İle ilişkili kullanıcı profili işaret tanıtıcı almak için bu yöntemi çağırın `CAccessToken` nesne.

```
HANDLE GetProfile() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Profil yok, kullanıcı profili veya NULL işaret eden bir tanıtıcı döndürür.

##  <a name="getsource"></a>  CAccessToken::GetSource

Kaynağını almak için bu yöntemi çağırın `CAccessToken` nesne.

```
bool GetSource(TOKEN_SOURCE* pSource) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pSource*<br/>
İşaretçi bir [TOKEN_SOURCE](/windows/desktop/api/winnt/ns-winnt-_token_source) yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

##  <a name="getstatistics"></a>  CAccessToken::GetStatistics

İle ilgili bilgi almak için bu yöntemi çağırın `CAccessToken` nesne.

```
bool GetStatistics(TOKEN_STATISTICS* pStatistics) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pStatistics*<br/>
İşaretçi bir [TOKEN_STATISTICS](/windows/desktop/api/winnt/ns-winnt-_token_statistics) yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

##  <a name="getterminalservicessessionid"></a>  CAccessToken::GetTerminalServicesSessionId

Terminal Hizmetleri oturum kimliği ile ilişkili almak için bu yöntemi çağırın `CAccessToken` nesne.

```
bool GetTerminalServicesSessionId(DWORD* pdwSessionId) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pdwSessionId*<br/>
Terminal Hizmetleri oturum kimliği

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

##  <a name="getthreadtoken"></a>  CAccessToken::GetThreadToken

Başlatmak için bu yöntemi çağırın `CAccessToken` belirtilen iş parçacığından belirtecine sahip.

```
bool GetThreadToken(
    DWORD dwDesiredAccess,
    HANDLE hThread = NULL,
    bool bOpenAsSelf = true) throw();
```

### <a name="parameters"></a>Parametreler

*dwDesiredAccess*<br/>
İstenen erişim belirtecini erişim türlerini belirten bir erişim maskesi belirtir. Bu istenen erişim türleri, hangi erişimlerin verildiğini veya verilmediğini belirlemek için belirtecin DACL'si ile karşılaştırılır.

*hThread*<br/>
Erişim belirteci açık iş parçacığına işleyin.

*bOpenAsSelf*<br/>
Erişim denetimi iş parçacığı arama güvenlik bağlamında karşı yapılacak olup olmadığını belirten `GetThreadToken` yöntem veya işlem çağıran iş parçacığı için güvenlik bağlamı.

Bu parametre FALSE ise, erişim denetimi, çağıran iş parçacığı için güvenlik bağlamı kullanılarak gerçekleştirilir. İş parçacığı bir istemci kimliğine bürünme, bu güvenlik bağlamı, istemci işlemi olabilir. Bu parametre TRUE ise, erişim denetimi, çağıran iş parçacığı için işlem güvenlik bağlamını kullanarak yapılır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

##  <a name="gettokenid"></a>  CAccessToken::GetTokenId

Belirteç ile ilişkili Kimliği almak için bu yöntemi çağırın `CAccessToken` nesne.

```
bool GetTokenId(LUID* pluid) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pluid*<br/>
İşaretçi bir [LUID'ini](/windows/desktop/api/winnt/ns-winnt-_luid) hangi alır belirteç kimliği

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

##  <a name="gettype"></a>  CAccessToken::GetType

Belirteç türünü almak için bu yöntemi çağırın `CAccessToken` nesne.

```
bool GetType(TOKEN_TYPE* pType) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pType*<br/>
Adresi [TOKEN_TYPE](/windows/desktop/api/winnt/ne-winnt-_token_type) değişkeni, başarı, belirtecin türü alır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

TOKEN_TYPE numaralandırma türü, bir birincil belirteç kimliğe bürünme belirtecini ayırt değerlerini içerir.

##  <a name="getuser"></a>  CAccessToken::GetUser

İle ilişkili kullanıcıyı tanımlamak için bu yöntemi çağırın `CAccessToken` nesne.

```
bool GetUser(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>Parametreler

*Psıd*<br/>
İşaretçi bir [CSid sınıfı](../../atl/reference/csid-class.md) nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

##  <a name="hkeycurrentuser"></a>  CAccessToken::HKeyCurrentUser

İle ilişkili kullanıcı profili işaret tanıtıcı almak için bu yöntemi çağırın `CAccessToken` nesne.

```
HKEY HKeyCurrentUser() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Profil yok, kullanıcı profili veya NULL işaret eden bir tanıtıcı döndürür.

##  <a name="impersonate"></a>  CAccessToken::Impersonate

Bir kimliğe bürünme atamak için bu yöntemi çağırın `CAccessToken` bir iş parçacığına.

```
bool Impersonate(HANDLE hThread = NULL) const throw(...);
```

### <a name="parameters"></a>Parametreler

*hThread*<br/>
İş parçacığı için kimliğe bürünme belirtecini atamak için işleyin. Bu işleyici TOKEN_IMPERSONATE erişim haklarıyla açılmış olmalıdır. Varsa *hThread* null, yöntem bir kimliğe bürünme belirteci durdurmak iş parçacığı neden olur.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir `CAccessToken` belirteç geçerli bir işaretçi yok.

[Cautorevertımpersonation sınıfı](../../atl/reference/cautorevertimpersonation-class.md) başkasının kimliğine bürünülerek gerçekleştirilen bir erişim belirteci otomatik olarak geri almak için kullanılabilir.

##  <a name="impersonateloggedonuser"></a>  CAccessToken::ImpersonateLoggedOnUser

Güvenlik bağlamı bir oturum açan kullanıcının kimliğine bürünmek çağıran iş parçacığına izin vermek için bu yöntemi çağırın.

```
bool ImpersonateLoggedOnUser() const throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

> [!IMPORTANT]
>  Kimliğe bürünme işlevi çağrısı için herhangi bir nedenle başarısız olursa, istemci kimliğine bürünülen değildir ve istemci isteği Çağrının yapıldığı işlem güvenlik bağlamında yapılır. İşlem yüksek ayrıcalıklı bir hesap çalışıyor ya da bir yönetim grubunun bir üyesi olarak kullanıcı eylemleri gerçekleştiremezsiniz olabilir isterse aksi izni. Bu nedenle, bu işlevin dönüş değeri her zaman onaylanması.

##  <a name="istokenrestricted"></a>  CAccessToken::IsTokenRestricted

Test için bu yöntemi çağırın `CAccessToken` nesne kısıtlı SID bir listesini içerir.

```
bool IsTokenRestricted() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne hiçbir kısıtlama SID varsa SID yanlış sınırlama listesi içeriyorsa veya yöntem başarısız olursa TRUE değerini döndürür.

##  <a name="loaduserprofile"></a>  CAccessToken::LoadUserProfile

İle ilişkili kullanıcı profili yüklemek için bu yöntemi çağıran `CAccessToken` nesne.

```
bool LoadUserProfile() throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir `CAccessToken` geçerli bir belirteç içermiyor veya bir kullanıcı zaten profil yoksa.

##  <a name="logonuser"></a>  CAccessToken::LogonUser

Verilen kimlik bilgileriyle ilişkili kullanıcı için bir oturum açma oturumu oluşturmak için bu yöntemi çağırın.

```
bool LogonUser(
    LPCTSTR pszUserName,
    LPCTSTR pszDomain,
    LPCTSTR pszPassword,
    DWORD dwLogonType = LOGON32_LOGON_INTERACTIVE,
    DWORD dwLogonProvider = LOGON32_PROVIDER_DEFAULT) throw();
```

### <a name="parameters"></a>Parametreler

*pszUserName*<br/>
Kullanıcı adını belirten bir null ile sonlandırılmış dizeye yönelik işaretçi. Bu oturum için kullanıcı hesabının adıdır.

*pszDomain*<br/>
Etki alanı ya da içeren, hesap veritabanı sunucusu adını belirten bir null ile sonlandırılmış dize işaretçisine *pszUserName* hesabı.

*pszPassword*<br/>
Belirtilen kullanıcı hesabı için düz metin parolayı belirtir null ile sonlandırılmış bir dize işaretçisi *pszUserName*.

*dwLogonType*<br/>
Oturum açma işlemi gerçekleştirmek için türünü belirtir. Bkz: [LogonUser](/windows/desktop/api/winbase/nf-winbase-logonusera) daha fazla ayrıntı için.

*dwLogonProvider*<br/>
Oturum açma sağlayıcısını belirtir. Bkz: [LogonUser](/windows/desktop/api/winbase/nf-winbase-logonusera) daha fazla ayrıntı için.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

Erişim belirteci üzerinden oturum açma kaynaklanan ile ilişkili olabilir `CAccessToken`. Başarılı olması bu yöntemin `CAccessToken` nesnesi SE_TCB_NAME ayrıcalıklar, güvenilen bir bilgisayar temel bir parçası olarak sahibi tanımlayan tutar. Bkz: [LogonUser](/windows/desktop/api/winbase/nf-winbase-logonusera) gereken ayrıcalıklar ilgili daha fazla bilgi.

##  <a name="opencomclienttoken"></a>  CAccessToken::OpenCOMClientToken

İşleme başlatmak için bir çağrı bir istemciden bir COM sunucusu bu yöntemi çağırın `CAccessToken` COM istemcisi erişim belirteci ile.

```
bool OpenCOMClientToken(
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```

### <a name="parameters"></a>Parametreler

*dwDesiredAccess*<br/>
İstenen erişim belirtecini erişim türlerini belirten bir erişim maskesi belirtir. Bu istenen erişim türleri, hangi erişimlerin verildiğini veya verilmediğini belirlemek için belirtecin DACL'si ile karşılaştırılır.

*bImpersonate*<br/>
Bu çağrının başarıyla tamamlanırsa TRUE ise, geçerli iş parçacığı çağıran COM istemci kimliğine bürünür. FALSE ise, erişim belirtecini açılır, ancak bu çağrı tamamlandığında iş parçacığı kimliğe bürünme belirtecini olmaz.

*bOpenAsSelf*<br/>
Erişim denetimi iş parçacığı arama güvenlik bağlamında karşı yapılacak olup olmadığını belirten [GetThreadToken](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) yöntem veya işlem çağıran iş parçacığı için güvenlik bağlamı.

Bu parametre FALSE ise, erişim denetimi, çağıran iş parçacığı için güvenlik bağlamı kullanılarak gerçekleştirilir. İş parçacığı bir istemci kimliğine bürünme, bu güvenlik bağlamı, istemci işlemi olabilir. Bu parametre TRUE ise, erişim denetimi, çağıran iş parçacığı için işlem güvenlik bağlamını kullanarak yapılır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

[Cautorevertımpersonation sınıfı](../../atl/reference/cautorevertimpersonation-class.md) otomatik olarak ayarlanarak oluşturulmuş başkasının kimliğine bürünülerek gerçekleştirilen erişim belirteçleri geri almak için kullanılan *bImpersonate* bayrağı true.

##  <a name="opennamedpipeclienttoken"></a>  CAccessToken::OpenNamedPipeClientToken

Bir sunucu içinde Bu yöntemden alma isteği başlatmak için bir adlandırılmış kanal üzerinde çağrı `CAccessToken` istemci erişim belirteciyle.

```
bool OpenNamedPipeClientToken(
    HANDLE hPipe,
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```

### <a name="parameters"></a>Parametreler

*hPipe*<br/>
Bir adlandırılmış kanala işleyin.

*dwDesiredAccess*<br/>
İstenen erişim belirtecini erişim türlerini belirten bir erişim maskesi belirtir. Bu istenen erişim türleri, hangi erişimlerin verildiğini veya verilmediğini belirlemek için belirtecin DACL'si ile karşılaştırılır.

*bImpersonate*<br/>
Bu çağrının başarıyla tamamlanırsa TRUE ise, geçerli iş parçacığı çağıran kanal istemci kimliğine bürünür. FALSE ise, erişim belirtecini açılır, ancak bu çağrı tamamlandığında iş parçacığı kimliğe bürünme belirtecini olmaz.

*bOpenAsSelf*<br/>
Erişim denetimi iş parçacığı arama güvenlik bağlamında karşı yapılacak olup olmadığını belirten [GetThreadToken](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) yöntem veya işlem çağıran iş parçacığı için güvenlik bağlamı.

Bu parametre FALSE ise, erişim denetimi, çağıran iş parçacığı için güvenlik bağlamı kullanılarak gerçekleştirilir. İş parçacığı bir istemci kimliğine bürünme, bu güvenlik bağlamı, istemci işlemi olabilir. Bu parametre TRUE ise, erişim denetimi, çağıran iş parçacığı için işlem güvenlik bağlamını kullanarak yapılır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

[Cautorevertımpersonation sınıfı](../../atl/reference/cautorevertimpersonation-class.md) otomatik olarak ayarlanarak oluşturulmuş başkasının kimliğine bürünülerek gerçekleştirilen erişim belirteçleri geri almak için kullanılan *bImpersonate* bayrağı true.

##  <a name="openrpcclienttoken"></a>  CAccessToken::OpenRPCClientToken

Bir sunucu başlatmak için bir RPC istemcisini bir çağrıdan işleme içinde bu yöntemi çağırın `CAccessToken` istemci erişim belirteciyle.

```
bool OpenRPCClientToken(
    RPC_BINDING_HANDLE BindingHandle,
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```

### <a name="parameters"></a>Parametreler

*BindingHandle*<br/>
Bağlama işleci otomatik olarak sunucunun bir istemciye bağlamayı temsil eder.

*dwDesiredAccess*<br/>
İstenen erişim belirtecini erişim türlerini belirten bir erişim maskesi belirtir. Bu istenen erişim türleri, hangi erişimlerin verildiğini veya verilmediğini belirlemek için belirtecin DACL'si ile karşılaştırılır.

*bImpersonate*<br/>
Bu çağrının başarıyla tamamlanırsa TRUE ise, geçerli iş parçacığı çağıran RPC istemci kimliğine bürünür. FALSE ise, erişim belirtecini açılır, ancak bu çağrı tamamlandığında iş parçacığı kimliğe bürünme belirtecini olmaz.

*bOpenAsSelf*<br/>
Erişim denetimi iş parçacığı arama güvenlik bağlamında karşı yapılacak olup olmadığını belirten [GetThreadToken](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) yöntem veya işlem çağıran iş parçacığı için güvenlik bağlamı.

Bu parametre FALSE ise, erişim denetimi, çağıran iş parçacığı için güvenlik bağlamı kullanılarak gerçekleştirilir. İş parçacığı bir istemci kimliğine bürünme, bu güvenlik bağlamı, istemci işlemi olabilir. Bu parametre TRUE ise, erişim denetimi, çağıran iş parçacığı için işlem güvenlik bağlamını kullanarak yapılır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

[Cautorevertımpersonation sınıfı](../../atl/reference/cautorevertimpersonation-class.md) otomatik olarak ayarlanarak oluşturulmuş başkasının kimliğine bürünülerek gerçekleştirilen erişim belirteçleri geri almak için kullanılan *bImpersonate* bayrağı true.

##  <a name="openthreadtoken"></a>  CAccessToken::OpenThreadToken

Kimliğe bürünme düzeyini ayarlayın ve ardından başlatmak için bu yöntemi çağırın `CAccessToken` belirtilen iş parçacığından belirtecine sahip.

```
bool OpenThreadToken(
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true,
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) throw(...);
```

### <a name="parameters"></a>Parametreler

*dwDesiredAccess*<br/>
İstenen erişim belirtecini erişim türlerini belirten bir erişim maskesi belirtir. Bu istenen erişim türleri, hangi erişimlerin verildiğini veya verilmediğini belirlemek için belirtecin DACL'si ile karşılaştırılır.

*bImpersonate*<br/>
Bu yöntem tamamlandığında iş parçacığının TRUE ise istenen kimliğe bürünme düzeyinde kalır. FALSE ise, iş parçacığının kendi özgün kimliğe bürünme düzeyini döner.

*bOpenAsSelf*<br/>
Erişim denetimi iş parçacığı arama güvenlik bağlamında karşı yapılacak olup olmadığını belirten [GetThreadToken](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) yöntem veya işlem çağıran iş parçacığı için güvenlik bağlamı.

Bu parametre FALSE ise, erişim denetimi, çağıran iş parçacığı için güvenlik bağlamı kullanılarak gerçekleştirilir. İş parçacığı bir istemci kimliğine bürünme, bu güvenlik bağlamı, istemci işlemi olabilir. Bu parametre TRUE ise, erişim denetimi, çağıran iş parçacığı için işlem güvenlik bağlamını kullanarak yapılır.

*Sil*<br/>
Belirtir bir [SECURITY_IMPERSONATION_LEVEL](/windows/desktop/api/winnt/ne-winnt-_security_impersonation_level) listelenmiş belirteç kimliğe bürünme düzeyini sağlayan türü.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

`OpenThreadToken` benzer [CAccessToken::GetThreadToken](#getthreadtoken), ancak başlatmadan önce kimliğe bürünme düzeyini ayarlar `CAccessToken` gelen iş parçacığının erişim belirteci.

[Cautorevertımpersonation sınıfı](../../atl/reference/cautorevertimpersonation-class.md) otomatik olarak ayarlanarak oluşturulmuş başkasının kimliğine bürünülerek gerçekleştirilen erişim belirteçleri geri almak için kullanılan *bImpersonate* bayrağı true.

##  <a name="privilegecheck"></a>  CAccessToken::PrivilegeCheck

Belirtilen bir ayrıcalık kümesi etkin içinde olup olmadığını belirlemek için bu yöntemi çağırın `CAccessToken` nesne.

```
bool PrivilegeCheck(
    PPRIVILEGE_SET RequiredPrivileges,
    bool* pbResult) const throw();
```

### <a name="parameters"></a>Parametreler

*RequiredPrivileges*<br/>
İşaretçi bir [PRIVILEGE_SET](/windows/desktop/api/winnt/ns-winnt-_privilege_set) yapısı.

*pbResult*<br/>
Yöntem bir değere işaretçi ayarlar tüm belirtilen ayrıcalık içinde etkin olup olmadığını belirtmek için `CAccessToken` nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

Zaman `PrivilegeCheck` döndürür, `Attributes` her üyesi [LUID_AND_ATTRIBUTES konusuna](/windows/desktop/api/winnt/ns-winnt-_luid_and_attributes) karşılık gelen ayrıcalık etkinse yapısı SE_PRIVILEGE_USED_FOR_ACCESS için ayarlanır. Bu yöntemin çağırdığı [PrivilegeCheck](https://msdn.microsoft.com/library/windows/desktop/aa379304) Win32 işlevi.

##  <a name="revert"></a>  CAccessToken::Revert

Kimliğe bürünme belirtecini kullanarak bir iş parçacığını durdurmak için bu yöntemi çağırın.

```
bool Revert(HANDLE hThread = NULL) const throw();
```

### <a name="parameters"></a>Parametreler

*hThread*<br/>
İş parçacığı kimliğe bürünme geri dönmek için işleyin. Varsa *hThread* boş, geçerli iş parçacığı varsayılır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

Geri Al'kimliğe bürünme belirteçleri ile otomatik olarak gerçekleştirilebilir [Cautorevertımpersonation sınıfı](../../atl/reference/cautorevertimpersonation-class.md).

##  <a name="setdefaultdacl"></a>  CAccessToken::SetDefaultDacl

Varsayılan değer ayarlamak için bu yöntemi çağırın'ın DACL `CAccessToken` nesne.

```
bool SetDefaultDacl(const CDacl& rDacl) throw(...);
```

### <a name="parameters"></a>Parametreler

*rDacl*<br/>
Yeni varsayılan [CDacl sınıfı](../../atl/reference/cdacl-class.md) bilgileri.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

DACL yeni nesneleri bu erişim belirteciyle yürürlükte oluşturulduğunda, varsayılan olarak kullanılan DACL varsayılandır.

##  <a name="setowner"></a>  CAccessToken::SetOwner

Sahibi ayarlamak için bu yöntemi çağırın `CAccessToken` nesne.

```
bool SetOwner(const CSid& rSid) throw(...);
```

### <a name="parameters"></a>Parametreler

*rSid*<br/>
[CSid sınıfı](../../atl/reference/csid-class.md) sahibi bilgi içeren nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

Bu erişim belirteci etkin durumdayken oluşturulan yeni nesneler için kullanılan varsayılan sahibi sahibidir.

##  <a name="setprimarygroup"></a>  CAccessToken::SetPrimaryGroup

Birincil grup ayarlamak için bu yöntemi çağırın `CAccessToken` nesne.

```
bool SetPrimaryGroup(const CSid& rSid) throw(...);
```

### <a name="parameters"></a>Parametreler

*rSid*<br/>
[CSid sınıfı](../../atl/reference/csid-class.md) birincil grup bilgilerini içeren bir nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

Bu erişim belirteci etkin durumdayken oluşturulan yeni nesneler için varsayılan grup birincil grubudur.

## <a name="see-also"></a>Ayrıca Bkz.

[ATLSecurity örnek](../../visual-cpp-samples.md)<br/>
[Erişim belirteçleri](/windows/desktop/SecAuthZ/access-tokens)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
