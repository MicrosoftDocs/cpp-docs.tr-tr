---
description: 'Daha fazla bilgi edinin: CAccessToken sınıfı'
title: CAccessToken sınıfı
ms.date: 07/02/2019
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
helpviewer_keywords:
- CAccessToken class
ms.assetid: bb5c5945-56a5-4083-b442-76573cee83ab
ms.openlocfilehash: fdcef40948a19c5ffb69aa32b18566280d048697
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158549"
---
# <a name="caccesstoken-class"></a>CAccessToken sınıfı

Bu sınıf, erişim belirtecinin sarmalayıcısıdır.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Syntax

```cpp
class CAccessToken
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAccessToken:: ~ CAccessToken](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAccessToken:: Attach](#attach)|Verilen erişim belirteci tanıtıcısının sahipliğini almak için bu yöntemi çağırın.|
|[CAccessToken:: CheckTokenMembership](#checktokenmembership)|Nesnede belirtilen bir SID 'nin etkinleştirilip etkinleştirilmediğini anlamak için bu yöntemi çağırın `CAccessToken` .|
|[CAccessToken:: Createımpersonationtoken](#createimpersonationtoken)|Yeni bir kimliğe bürünme erişim belirteci oluşturmak için bu yöntemi çağırın.|
|[CAccessToken:: CreatePrimaryToken](#createprimarytoken)|Yeni bir birincil belirteç oluşturmak için bu yöntemi çağırın.|
|[CAccessToken:: CreateProcessAsUser](#createprocessasuser)|Nesne tarafından temsil edilen kullanıcının güvenlik bağlamında çalışan yeni bir işlem oluşturmak için bu yöntemi çağırın `CAccessToken` .|
|[CAccessToken:: CreateRestrictedToken](#createrestrictedtoken)|Yeni, kısıtlı bir nesne oluşturmak için bu yöntemi çağırın `CAccessToken` .|
|[CAccessToken::D etach](#detach)|Erişim belirtecinin sahipliğini iptal etmek için bu yöntemi çağırın.|
|[CAccessToken::D isablePrivilege](#disableprivilege)|Nesnedeki bir ayrıcalığı devre dışı bırakmak için bu yöntemi çağırın `CAccessToken` .|
|[CAccessToken::D isablePrivileges](#disableprivileges)|Nesnedeki bir veya daha fazla ayrıcalığı devre dışı bırakmak için bu yöntemi çağırın `CAccessToken` .|
|[CAccessToken:: EnablePrivilege](#enableprivilege)|Nesnede bir ayrıcalığı etkinleştirmek için bu yöntemi çağırın `CAccessToken` .|
|[CAccessToken:: EnablePrivileges](#enableprivileges)|Nesnedeki bir veya daha fazla ayrıcalığı etkinleştirmek için bu yöntemi çağırın `CAccessToken` .|
|[CAccessToken:: GetDefaultDacl](#getdefaultdacl)|Nesnenin varsayılan DACL 'sini döndürmek için bu yöntemi çağırın `CAccessToken` .|
|[CAccessToken:: GetEffectiveToken](#geteffectivetoken)|`CAccessToken`Nesnenin geçerli iş parçacığı için geçerli olan erişim belirtecine eşit olması için bu yöntemi çağırın.|
|[CAccessToken:: GetGroups](#getgroups)|Nesnenin belirteç gruplarını döndürmek için bu yöntemi çağırın `CAccessToken` .|
|[CAccessToken:: GetHandle](#gethandle)|Erişim belirtecine bir tanıtıcı almak için bu yöntemi çağırın.|
|[CAccessToken:: GetImpersonationLevel](#getimpersonationlevel)|Erişim belirtecinden kimliğe bürünme düzeyini almak için bu yöntemi çağırın.|
|[CAccessToken:: Getlogonsessionıd](#getlogonsessionid)|Nesneyle ilişkili oturum açma oturum KIMLIĞINI almak için bu yöntemi çağırın `CAccessToken` .|
|[CAccessToken:: GetLogonSid](#getlogonsid)|Nesneyle ilişkili oturum açma SID 'sini almak için bu yöntemi çağırın `CAccessToken` .|
|[CAccessToken:: GetOwner](#getowner)|Nesneyle ilişkili sahibi almak için bu yöntemi çağırın `CAccessToken` .|
|[CAccessToken:: GetPrimaryGroup](#getprimarygroup)|Nesneyle ilişkili birincil grubu almak için bu yöntemi çağırın `CAccessToken` .|
|[CAccessToken:: GetPrivileges](#getprivileges)|Nesneyle ilişkili ayrıcalıkları almak için bu yöntemi çağırın `CAccessToken` .|
|[CAccessToken:: GetProcessToken](#getprocesstoken)|`CAccessToken`Verilen işlemden erişim belirteci ile başlatmak için bu yöntemi çağırın.|
|[CAccessToken:: GetProfile](#getprofile)|Nesneyle ilişkili kullanıcı profiline işaret eden tanıtıcıyı almak için bu yöntemi çağırın `CAccessToken` .|
|[CAccessToken:: GetSource](#getsource)|Nesnenin kaynağını almak için bu yöntemi çağırın `CAccessToken` .|
|[CAccessToken:: GetStatistics](#getstatistics)|Nesneyle ilişkili bilgileri almak için bu yöntemi çağırın `CAccessToken` .|
|[CAccessToken:: Getterminalservicessessionıd](#getterminalservicessessionid)|Nesneyle ilişkili Terminal Hizmetleri oturum KIMLIĞINI almak için bu yöntemi çağırın `CAccessToken` .|
|[CAccessToken:: GetThreadToken](#getthreadtoken)|`CAccessToken`Verilen iş parçacığından belirteç ile başlatmak için bu yöntemi çağırın.|
|[CAccessToken:: Gettokenıd](#gettokenid)|Nesneyle ilişkili belirteç KIMLIĞINI almak için bu yöntemi çağırın `CAccessToken` .|
|[CAccessToken:: GetType](#gettype)|Nesnenin belirteç türünü almak için bu yöntemi çağırın `CAccessToken` .|
|[CAccessToken:: GetUser](#getuser)|Nesneyle ilişkili kullanıcıyı tanımlamak için bu yöntemi çağırın `CAccessToken` .|
|[CAccessToken:: HKeyCurrentUser](#hkeycurrentuser)|Nesneyle ilişkili kullanıcı profiline işaret eden tanıtıcıyı almak için bu yöntemi çağırın `CAccessToken` .|
|[CAccessToken:: Impersonate](#impersonate)|Bir iş parçacığına kimliğe bürünme atamak için bu yöntemi çağırın `CAccessToken` .|
|[CAccessToken:: ImpersonateLoggedOnUser](#impersonateloggedonuser)|Çağıran iş parçacığının, oturum açmış bir kullanıcının güvenlik bağlamını taklit etmesine izin vermek için bu yöntemi çağırın.|
|[CAccessToken:: ıstokenrestricted](#istokenrestricted)|`CAccessToken`Nesnenin kısıtlı SID 'lerin bir listesini içerip içermiyorsa test etmek için bu yöntemi çağırın.|
|[CAccessToken:: LoadUserProfile](#loaduserprofile)|Nesneyle ilişkili kullanıcı profilini yüklemek için bu yöntemi çağırın `CAccessToken` .|
|[CAccessToken:: LogonUser](#logonuser)|Verilen kimlik bilgileriyle ilişkili kullanıcı için bir oturum açma oturumu oluşturmak için bu yöntemi çağırın.|
|[CAccessToken:: OpenCOMClientToken](#opencomclienttoken)|Com istemcisinden erişim belirteci ile başlatmak için bir istemciden çağrıyı işleyen bir COM sunucusu içinden bu yöntemi çağırın `CAccessToken` .|
|[CAccessToken:: OpenNamedPipeClientToken](#opennamedpipeclienttoken)|İstemciden erişim belirteci ile başlatmak için adlandırılmış bir kanal üzerinden istek alan bir sunucu içinden bu yöntemi çağırın `CAccessToken` .|
|[CAccessToken:: OpenRPCClientToken](#openrpcclienttoken)|İstemciden erişim belirteci ile başlatmak için bir RPC istemcisinden çağrıyı işleyen bir sunucu içinden bu yöntemi çağırın `CAccessToken` .|
|[CAccessToken:: OpenThreadToken](#openthreadtoken)|Kimliğe bürünme düzeyini ayarlamak için bu yöntemi çağırın ve ardından öğesini `CAccessToken` verilen iş parçacığından belirteç ile başlatın.|
|[CAccessToken::P rivilegeCheck](#privilegecheck)|Nesnede belirtilen ayrıcalık kümesinin etkinleştirilip etkinleştirilmeyeceğini anlamak için bu yöntemi çağırın `CAccessToken` .|
|[CAccessToken:: çevir](#revert)|Kimliğe bürünme belirtecini kullanan bir iş parçacığını durdurmak için bu yöntemi çağırın.|
|[CAccessToken:: SetDefaultDacl](#setdefaultdacl)|Nesnenin varsayılan DACL 'sini ayarlamak için bu yöntemi çağırın `CAccessToken` .|
|[CAccessToken:: SetOwner](#setowner)|Nesnenin sahibini ayarlamak için bu yöntemi çağırın `CAccessToken` .|
|[CAccessToken:: SetPrimaryGroup](#setprimarygroup)|Nesnenin birincil grubunu ayarlamak için bu yöntemi çağırın `CAccessToken` .|

## <a name="remarks"></a>Açıklamalar

[Erişim belirteci](/windows/win32/SecAuthZ/access-tokens) bir işlemin veya iş parçacığının güvenlik bağlamını açıklayan ve bir Windows sisteminde oturum açan her kullanıcıya ayrılan bir nesnedir.

Windows 'daki erişim denetim modeline giriş için Windows SDK [Access Control](/windows/win32/SecAuthZ/access-control) bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity. h

## <a name="caccesstokenattach"></a><a name="attach"></a> CAccessToken:: Attach

Verilen erişim belirteci tanıtıcısının sahipliğini almak için bu yöntemi çağırın.

```cpp
void Attach(HANDLE hToken) throw();
```

### <a name="parameters"></a>Parametreler

*hToken*<br/>
Erişim belirtecine yönelik bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, `CAccessToken` nesne zaten bir erişim belirtecinin sahipliğini içeriyorsa bir onaylama hatası oluşur.

## <a name="caccesstokencaccesstoken"></a><a name="dtor"></a> CAccessToken:: ~ CAccessToken

Yok edicisi.

```cpp
virtual ~CAccessToken() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakır.

## <a name="caccesstokenchecktokenmembership"></a><a name="checktokenmembership"></a> CAccessToken:: CheckTokenMembership

Nesnede belirtilen bir SID 'nin etkinleştirilip etkinleştirilmediğini anlamak için bu yöntemi çağırın `CAccessToken` .

```cpp
bool CheckTokenMembership(
    const CSid& rSid,
    bool* pbIsMember) const throw(...);
```

### <a name="parameters"></a>Parametreler

*Rsıd*<br/>
Bir [CSID sınıfı](../../atl/reference/csid-class.md) nesnesine başvuru.

*pbIsMember*<br/>
Çekin sonuçlarını alan bir değişkene yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

`CheckTokenMembership`Yöntemi, erişim belirtecinin Kullanıcı ve Grup SID 'lerine AIT SID varlığını denetler. SID varsa ve SE_GROUP_ENABLED özniteliğine sahipse, *Pbismember* değeri true olarak ayarlanır; Aksi takdirde, FALSE olarak ayarlanır.

Hata ayıklama yapılarında, *Pbismember* geçerli bir işaretçi değilse bir onaylama hatası oluşur.

> [!NOTE]
> `CAccessToken`Nesne, birincil belirteç değil, kimliğe bürünme belirteci olmalıdır.

## <a name="caccesstokencreateimpersonationtoken"></a><a name="createimpersonationtoken"></a> CAccessToken:: Createımpersonationtoken

Kimliğe bürünme erişim belirteci oluşturmak için bu yöntemi çağırın.

```cpp
bool CreateImpersonationToken(
    CAccessToken* pImp,
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pImp*<br/>
Yeni `CAccessToken` nesne işaretçisi.

*Sil*<br/>
Yeni belirtecin kimliğe bürünme düzeyini sağlayan [SECURITY_IMPERSONATION_LEVEL](/windows/win32/api/winnt/ne-winnt-security_impersonation_level) numaralandırılmış bir tür belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

`CreateImpersonationToken` Yeni bir kimliğe bürünme belirteci oluşturmak için [DuplicateToken](/windows/win32/api/securitybaseapi/nf-securitybaseapi-duplicatetoken) çağırır.

## <a name="caccesstokencreateprimarytoken"></a><a name="createprimarytoken"></a> CAccessToken:: CreatePrimaryToken

Yeni bir birincil belirteç oluşturmak için bu yöntemi çağırın.

```cpp
bool CreatePrimaryToken(
    CAccessToken* pPri,
    DWORD dwDesiredAccess = MAXIMUM_ALLOWED,
    const CSecurityAttributes* pTokenAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Parametreler

*Pprı*<br/>
Yeni `CAccessToken` nesne işaretçisi.

*dwDesiredAccess*<br/>
Yeni belirteç için istenen erişim haklarını belirtir. Varsayılan, MAXIMUM_ALLOWED, çağıran için geçerli olan tüm erişim haklarını ister. Erişim hakları hakkında daha fazla bilgi için bkz. [erişim hakları ve erişim maskeleri](/windows/win32/SecAuthZ/access-rights-and-access-masks) .

*pTokenAttributes*<br/>
Yeni belirteç için bir güvenlik tanımlayıcısı belirten [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) yapısına yönelik işaretçi ve alt işlemlerin belirteci devralmasını belirler. *PTokenAttributes* null ise, belirteç varsayılan bir güvenlik tanımlayıcısı alır ve tanıtıcı devralınamaz.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

`CreatePrimaryToken` Yeni bir birincil belirteç oluşturmak için [DuplicateTokenEx](/windows/win32/api/securitybaseapi/nf-securitybaseapi-duplicatetokenex) çağırır.

## <a name="caccesstokencreateprocessasuser"></a><a name="createprocessasuser"></a> CAccessToken:: CreateProcessAsUser

Nesne tarafından temsil edilen kullanıcının güvenlik bağlamında çalışan yeni bir işlem oluşturmak için bu yöntemi çağırın `CAccessToken` .

```cpp
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
Yürütülecek modülü belirten, null ile sonlandırılmış bir dize işaretçisi. Bu parametre NULL olmayabilir.

*pCommandLine*<br/>
Yürütülecek komut satırını belirten, null ile sonlandırılmış bir dize işaretçisi.

*Pprocessınformation*<br/>
Yeni işlemle ilgili tanımlama bilgilerini alan [PROCESS_INFORMATION yapısına](/windows/win32/api/processthreadsapi/ns-processthreadsapi-process_information) yönelik işaretçi.

*Pstartupınfo*<br/>
Yeni işlemin ana penceresinin nasıl görüntüleneceğini belirten bir [STARTUPINFO](/windows/win32/api/processthreadsapi/ns-processthreadsapi-startupinfow) yapısına yönelik işaretçi.

*dwCreationFlags*<br/>
Öncelik sınıfını ve işlemin oluşturulmasını denetleyen ek bayrakları belirtir. Bayrakların listesi için [CreateProcessAsUser](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessasuserw) Win32 işlevine bakın.

*bLoadProfile*<br/>
TRUE ise, kullanıcının profili [LoadUserProfile](/windows/win32/api/userenv/nf-userenv-loaduserprofilew)ile yüklenir.

*pProcessAttributes*<br/>
Yeni işlem için bir güvenlik tanımlayıcısı belirten [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) yapısına yönelik işaretçi ve alt işlemlerin döndürülen tanıtıcıyı alıp almamayacağını belirler. *PProcessAttributes* null ise, işlem varsayılan bir güvenlik tanımlayıcısı alır ve tanıtıcı devralınmaz.

*pThreadAttributes*<br/>
Yeni iş parçacığı için bir güvenlik tanımlayıcısı belirten [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) yapısına yönelik işaretçi ve alt işlemlerin döndürülen tanıtıcıyı alıp almadığını belirler. *PThreadAttributes* null ise, iş parçacığı varsayılan bir güvenlik tanımlayıcısı alır ve tanıtıcı devralınamaz.

*bInherit*<br/>
Yeni işlemin, çağıran işlemden tutamaçları devralıp almadığını gösterir. TRUE ise, çağıran işlemdeki her devralınabilir açık tanıtıcı yeni işlem tarafından devralınır. Devralınan tutamaçlar, özgün tanıtıcılarla aynı değere ve erişim ayrıcalıklarına sahiptir.

*pCurrentDirectory*<br/>
Yeni işlemin geçerli sürücüsünü ve dizinini belirten, null ile sonlandırılmış bir dize işaretçisi. Dize, bir sürücü harfi içeren bir tam yol olmalıdır. Bu parametre NULL ise, yeni işlem çağıran işlemle aynı geçerli sürücü ve dizine sahip olur.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

`CreateProcessAsUser` , `CreateProcessAsUser` nesnesine göre temsil edilen kullanıcının güvenlik bağlamında çalışan yeni bir işlem oluşturmak için Win32 işlevini kullanır `CAccessToken` . Gerekli parametrelerin tam bir tartışması için [CreateProcessAsUser](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessasuserw) işlevinin açıklamasına bakın.

Bu yöntemin başarılı olması için, `CAccessToken` nesne Atamaprimarytoken 'ı (kısıtlı bir belirteç olmadığı müddetçe) ve IncreaseQuota ayrıcalıklarını tutmalıdır.

## <a name="caccesstokencreaterestrictedtoken"></a><a name="createrestrictedtoken"></a> CAccessToken:: CreateRestrictedToken

Yeni, kısıtlı bir nesne oluşturmak için bu yöntemi çağırın `CAccessToken` .

```cpp
bool CreateRestrictedToken(
    CAccessToken* pRestrictedToken,
    const CTokenGroups& SidsToDisable,
    const CTokenGroups& SidsToRestrict,
    const CTokenPrivileges& PrivilegesToDelete = CTokenPrivileges()) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pRestrictedToken*<br/>
Yeni, kısıtlı `CAccessToken` nesne.

*Sıdstodisable*<br/>
`CTokenGroups`Yalnızca reddetme SID 'lerini belirten bir nesne.

*Sıdstorestrict*<br/>
`CTokenGroups`Kısıtlama SID 'lerini belirten nesne.

*PrivilegesToDelete*<br/>
`CTokenPrivileges`Kısıtlanmış belirteçte silinecek ayrıcalıkları belirten nesne. Varsayılan değer boş bir nesne oluşturur.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

`CreateRestrictedToken` , kısıtlamalarla yeni bir nesne oluşturmak için [CreateRestrictedToken](/windows/win32/api/securitybaseapi/nf-securitybaseapi-createrestrictedtoken) Win32 işlevini kullanır `CAccessToken` .

> [!IMPORTANT]
> Kullanırken `CreateRestrictedToken` , aşağıdakilerden emin olun: mevcut belirteç geçerli (ve Kullanıcı tarafından girilmemiş) ve *Sıdstodisable* ve *PrivilegesToDelete* öğelerinin her ikisi de geçerlidir (ve Kullanıcı tarafından girilmez). Yöntem FALSE döndürürse, reddetme işlevselliği.

## <a name="caccesstokendetach"></a><a name="detach"></a> CAccessToken::D etach

Erişim belirtecinin sahipliğini iptal etmek için bu yöntemi çağırın.

```cpp
HANDLE Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CAccessToken`Ayrılan olan tanıtıcıyı döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `CAccessToken` erişim belirtecinin sahipliğini iptal eder.

## <a name="caccesstokendisableprivilege"></a><a name="disableprivilege"></a> CAccessToken::D isablePrivilege

Nesnedeki bir ayrıcalığı devre dışı bırakmak için bu yöntemi çağırın `CAccessToken` .

```cpp
bool DisablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>Parametreler

*pszPrivilege*<br/>
Nesnede devre dışı bırakmak için ayrıcalıkları içeren bir dize işaretçisi `CAccessToken` .

*pPreviousState*<br/>
`CTokenPrivileges`Ayrıcalıkların önceki durumunu içeren bir nesne işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

## <a name="caccesstokendisableprivileges"></a><a name="disableprivileges"></a> CAccessToken::D isablePrivileges

Nesnedeki bir veya daha fazla ayrıcalığı devre dışı bırakmak için bu yöntemi çağırın `CAccessToken` .

```cpp
bool DisablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>Parametreler

*rPrivileges*<br/>
Nesnede devre dışı bırakmak için ayrıcalıkları içeren dizeler dizisine yönelik işaretçi `CAccessToken` .

*pPreviousState*<br/>
`CTokenPrivileges`Ayrıcalıkların önceki durumunu içeren bir nesne işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

## <a name="caccesstokenenableprivilege"></a><a name="enableprivilege"></a> CAccessToken:: EnablePrivilege

Nesnede bir ayrıcalığı etkinleştirmek için bu yöntemi çağırın `CAccessToken` .

```cpp
bool EnablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>Parametreler

*pszPrivilege*<br/>
Nesnede etkinleştirilecek ayrıcalığını içeren bir dizeye yönelik işaretçi `CAccessToken` .

*pPreviousState*<br/>
`CTokenPrivileges`Ayrıcalıkların önceki durumunu içeren bir nesne işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

## <a name="caccesstokenenableprivileges"></a><a name="enableprivileges"></a> CAccessToken:: EnablePrivileges

Nesnedeki bir veya daha fazla ayrıcalığı etkinleştirmek için bu yöntemi çağırın `CAccessToken` .

```cpp
bool EnablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>Parametreler

*rPrivileges*<br/>
Nesnede etkinleştirilecek ayrıcalıkları içeren dizeler dizisine yönelik işaretçi `CAccessToken` .

*pPreviousState*<br/>
`CTokenPrivileges`Ayrıcalıkların önceki durumunu içeren bir nesne işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

## <a name="caccesstokengetdefaultdacl"></a><a name="getdefaultdacl"></a> CAccessToken:: GetDefaultDacl

Nesnenin varsayılan DACL 'sini döndürmek için bu yöntemi çağırın `CAccessToken` .

```cpp
bool GetDefaultDacl(CDacl* pDacl) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pDacl*<br/>
Nesnenin varsayılan DACL 'sini alacak olan [CDacl sınıf](../../atl/reference/cdacl-class.md) nesnesi işaretçisi `CAccessToken` .

### <a name="return-value"></a>Dönüş Değeri

Varsayılan DACL kurtarılırsa TRUE, aksi takdirde FALSE döndürür.

## <a name="caccesstokengeteffectivetoken"></a><a name="geteffectivetoken"></a> CAccessToken:: GetEffectiveToken

`CAccessToken`Nesnenin geçerli iş parçacığı için geçerli olan erişim belirtecine eşit olması için bu yöntemi çağırın.

```cpp
bool GetEffectiveToken(DWORD dwDesiredAccess) throw();
```

### <a name="parameters"></a>Parametreler

*dwDesiredAccess*<br/>
Erişim belirtecine istenen erişim türlerini belirten bir erişim maskesini belirtir. Bu istenen erişim türleri, hangi erişimlerin verildiğini veya reddedildiğini belirleyen belirtecin DACL 'si ile karşılaştırılır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

## <a name="caccesstokengetgroups"></a><a name="getgroups"></a> CAccessToken:: GetGroups

Nesnenin belirteç gruplarını döndürmek için bu yöntemi çağırın `CAccessToken` .

```cpp
bool GetGroups(CTokenGroups* pGroups) const throw(...);
```

### <a name="parameters"></a>Parametreler

*Pgruplar*<br/>
Grup bilgilerini alacak [CTokenGroups sınıf](../../atl/reference/ctokengroups-class.md) nesnesine yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

## <a name="caccesstokengethandle"></a><a name="gethandle"></a> CAccessToken:: GetHandle

Erişim belirtecine bir tanıtıcı almak için bu yöntemi çağırın.

```cpp
HANDLE GetHandle() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CAccessToken`Nesnenin erişim belirtecine bir tanıtıcı döndürür.

## <a name="caccesstokengetimpersonationlevel"></a><a name="getimpersonationlevel"></a> CAccessToken:: GetImpersonationLevel

Erişim belirtecinden kimliğe bürünme düzeyini almak için bu yöntemi çağırın.

```cpp
bool GetImpersonationLevel(
    SECURITY_IMPERSONATION_LEVEL* pImpersonationLevel) const throw(...);
```

### <a name="parameters"></a>Parametreler

*Pımpersonationlevel*<br/>
Kimliğe bürünme düzeyi bilgilerini alacak [SECURITY_IMPERSONATION_LEVEL](/windows/win32/api/winnt/ne-winnt-security_impersonation_level) numaralandırma türüne yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

## <a name="caccesstokengetlogonsessionid"></a><a name="getlogonsessionid"></a> CAccessToken:: Getlogonsessionıd

Nesneyle ilişkili oturum açma oturum KIMLIĞINI almak için bu yöntemi çağırın `CAccessToken` .

```cpp
bool GetLogonSessionId(LUID* pluid) const throw(...);
```

### <a name="parameters"></a>Parametreler

*plualıd*<br/>
Oturum açma oturum KIMLIĞINI alacak bir [LUID](/windows/win32/api/winnt/ns-winnt-luid) işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, *pluıd* geçersiz bir değer olduğunda bir onaylama hatası oluşur.

## <a name="caccesstokengetlogonsid"></a><a name="getlogonsid"></a> CAccessToken:: GetLogonSid

Nesneyle ilişkili oturum açma SID 'sini almak için bu yöntemi çağırın `CAccessToken` .

```cpp
bool GetLogonSid(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>Parametreler

*PSID*<br/>
[CSID sınıfı](../../atl/reference/csid-class.md) nesnesine yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama Derlemeleriyle, *PSID* geçersiz bir değer ise bir onaylama hatası meydana gelir.

## <a name="caccesstokengetowner"></a><a name="getowner"></a> CAccessToken:: GetOwner

Nesneyle ilişkili sahibi almak için bu yöntemi çağırın `CAccessToken` .

```cpp
bool GetOwner(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>Parametreler

*PSID*<br/>
[CSID sınıfı](../../atl/reference/csid-class.md) nesnesine yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Sahip, bu erişim belirteci etkin durumdayken oluşturulan tüm nesnelerde varsayılan olarak ayarlanır.

## <a name="caccesstokengetprimarygroup"></a><a name="getprimarygroup"></a> CAccessToken:: GetPrimaryGroup

Nesneyle ilişkili birincil grubu almak için bu yöntemi çağırın `CAccessToken` .

```cpp
bool GetPrimaryGroup(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>Parametreler

*PSID*<br/>
[CSID sınıfı](../../atl/reference/csid-class.md) nesnesine yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu erişim belirteci etkin durumdayken oluşturulan tüm nesnelerde grup varsayılan olarak ayarlanır.

## <a name="caccesstokengetprivileges"></a><a name="getprivileges"></a> CAccessToken:: GetPrivileges

Nesneyle ilişkili ayrıcalıkları almak için bu yöntemi çağırın `CAccessToken` .

```cpp
bool GetPrivileges(CTokenPrivileges* pPrivileges) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pPrivileges*<br/>
Ayrıcalıkları alacak bir [CTokenPrivileges sınıfı](../../atl/reference/ctokenprivileges-class.md) nesnesine yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

## <a name="caccesstokengetprocesstoken"></a><a name="getprocesstoken"></a> CAccessToken:: GetProcessToken

`CAccessToken`Verilen işlemden erişim belirteci ile başlatmak için bu yöntemi çağırın.

```cpp
bool GetProcessToken(DWORD dwDesiredAccess, HANDLE hProcess = NULL) throw();
```

### <a name="parameters"></a>Parametreler

*dwDesiredAccess*<br/>
Erişim belirtecine istenen erişim türlerini belirten bir erişim maskesini belirtir. Bu istenen erişim türleri, hangi erişimlerin verildiğini veya reddedildiğini belirleyen belirtecin DACL 'si ile karşılaştırılır.

*hProcess*<br/>
Erişim belirteci açık olan işlem için tanıtıcı. Varsayılan NULL değeri kullanılırsa, geçerli işlem kullanılır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

[OpenProcessToken](/windows/win32/api/processthreadsapi/nf-processthreadsapi-openprocesstoken) Win32 işlevini çağırır.

## <a name="caccesstokengetprofile"></a><a name="getprofile"></a> CAccessToken:: GetProfile

Nesneyle ilişkili kullanıcı profiline işaret eden tanıtıcıyı almak için bu yöntemi çağırın `CAccessToken` .

```cpp
HANDLE GetProfile() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı profiline işaret eden bir tanıtıcı döndürür veya profil yoksa NULL değeri döndürür.

## <a name="caccesstokengetsource"></a><a name="getsource"></a> CAccessToken:: GetSource

Nesnenin kaynağını almak için bu yöntemi çağırın `CAccessToken` .

```cpp
bool GetSource(TOKEN_SOURCE* pSource) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pSource*<br/>
[TOKEN_SOURCE](/windows/win32/api/winnt/ns-winnt-token_source) yapısına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

## <a name="caccesstokengetstatistics"></a><a name="getstatistics"></a> CAccessToken:: GetStatistics

Nesneyle ilişkili bilgileri almak için bu yöntemi çağırın `CAccessToken` .

```cpp
bool GetStatistics(TOKEN_STATISTICS* pStatistics) const throw(...);
```

### <a name="parameters"></a>Parametreler

*Pstatıstıcs*<br/>
[TOKEN_STATISTICS](/windows/win32/api/winnt/ns-winnt-token_statistics) yapısına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

## <a name="caccesstokengetterminalservicessessionid"></a><a name="getterminalservicessessionid"></a> CAccessToken:: Getterminalservicessessionıd

Nesneyle ilişkili Terminal Hizmetleri oturum KIMLIĞINI almak için bu yöntemi çağırın `CAccessToken` .

```cpp
bool GetTerminalServicesSessionId(DWORD* pdwSessionId) const throw(...);
```

### <a name="parameters"></a>Parametreler

*Pdwsessionıd*<br/>
Terminal Hizmetleri oturum KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

## <a name="caccesstokengetthreadtoken"></a><a name="getthreadtoken"></a> CAccessToken:: GetThreadToken

`CAccessToken`Verilen iş parçacığından belirteç ile başlatmak için bu yöntemi çağırın.

```cpp
bool GetThreadToken(
    DWORD dwDesiredAccess,
    HANDLE hThread = NULL,
    bool bOpenAsSelf = true) throw();
```

### <a name="parameters"></a>Parametreler

*dwDesiredAccess*<br/>
Erişim belirtecine istenen erişim türlerini belirten bir erişim maskesini belirtir. Bu istenen erişim türleri, hangi erişimlerin verildiğini veya reddedildiğini belirleyen belirtecin DACL 'si ile karşılaştırılır.

*hThread*<br/>
Erişim belirteci açık olan iş parçacığına yönelik tanıtıcı.

*bOpenAsSelf*<br/>
Erişim denetiminin, yöntemi çağıran iş parçacığının güvenlik bağlamına `GetThreadToken` veya çağıran iş parçacığı için işlemin güvenlik bağlamına karşı yapılıp yapılmayacağını belirtir.

Bu parametre FALSE ise, erişim denetimi çağıran iş parçacığının güvenlik bağlamı kullanılarak gerçekleştirilir. İş parçacığı bir istemciyi taklit alıyorsa, bu güvenlik bağlamı bir istemci işlemi olabilir. Bu parametre TRUE ise, erişim denetimi çağıran iş parçacığı için işlemin güvenlik bağlamı kullanılarak yapılır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

## <a name="caccesstokengettokenid"></a><a name="gettokenid"></a> CAccessToken:: Gettokenıd

Nesneyle ilişkili belirteç KIMLIĞINI almak için bu yöntemi çağırın `CAccessToken` .

```cpp
bool GetTokenId(LUID* pluid) const throw(...);
```

### <a name="parameters"></a>Parametreler

*plualıd*<br/>
Belirteç KIMLIĞINI alacak bir [LUID](/windows/win32/api/winnt/ns-winnt-luid) işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

## <a name="caccesstokengettype"></a><a name="gettype"></a> CAccessToken:: GetType

Nesnenin belirteç türünü almak için bu yöntemi çağırın `CAccessToken` .

```cpp
bool GetType(TOKEN_TYPE* pType) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pType*<br/>
Başarı durumunda belirtecin türünü alan [TOKEN_TYPE](/windows/win32/api/winnt/ne-winnt-token_type) değişkeninin adresi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

TOKEN_TYPE numaralandırma türü, bir birincil belirteç ve bir kimliğe bürünme belirteci ayırt eden değerleri içerir.

## <a name="caccesstokengetuser"></a><a name="getuser"></a> CAccessToken:: GetUser

Nesneyle ilişkili kullanıcıyı tanımlamak için bu yöntemi çağırın `CAccessToken` .

```cpp
bool GetUser(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>Parametreler

*PSID*<br/>
[CSID sınıfı](../../atl/reference/csid-class.md) nesnesine yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

## <a name="caccesstokenhkeycurrentuser"></a><a name="hkeycurrentuser"></a> CAccessToken:: HKeyCurrentUser

Nesneyle ilişkili kullanıcı profiline işaret eden tanıtıcıyı almak için bu yöntemi çağırın `CAccessToken` .

```cpp
HKEY HKeyCurrentUser() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı profiline işaret eden bir tanıtıcı döndürür veya profil yoksa NULL değeri döndürür.

## <a name="caccesstokenimpersonate"></a><a name="impersonate"></a> CAccessToken:: Impersonate

Bir iş parçacığına kimliğe bürünme atamak için bu yöntemi çağırın `CAccessToken` .

```cpp
bool Impersonate(HANDLE hThread = NULL) const throw(...);
```

### <a name="parameters"></a>Parametreler

*hThread*<br/>
Kimliğe bürünme belirtecini atamak için iş parçacığına olan tanıtıcı. Bu tanıtıcının TOKEN_IMPERSONATE erişim haklarıyla açılmış olması gerekir. *HThread* null ise, yöntemi, iş parçacığının kimliğe bürünme belirtecini kullanmayı durdurmasına neden olur.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, belirteç için geçerli bir işaretçi yoksa bir onaylama hatası meydana gelir `CAccessToken` .

[CAutoRevertImpersonation sınıfı](../../atl/reference/cautorevertimpersonation-class.md) , kimliğe bürünme erişim belirteçlerini otomatik olarak dönüştürmek için kullanılabilir.

## <a name="caccesstokenimpersonateloggedonuser"></a><a name="impersonateloggedonuser"></a> CAccessToken:: ImpersonateLoggedOnUser

Çağıran iş parçacığının, oturum açmış bir kullanıcının güvenlik bağlamını taklit etmesine izin vermek için bu yöntemi çağırın.

```cpp
bool ImpersonateLoggedOnUser() const throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

> [!IMPORTANT]
> Kimliğe bürünme işlevine yapılan bir çağrı herhangi bir nedenle başarısız olursa, istemci kimliğine bürünülemez ve istemci isteği Çağrının yapıldığı işlemin güvenlik bağlamında yapılır. İşlem yüksek ayrıcalıklı bir hesap olarak çalışıyorsa veya bir yönetim grubunun üyesi olarak, Kullanıcı Aksi takdirde izin verilmeyen eylemler gerçekleştirebilir. Bu nedenle, bu işlevin dönüş değeri her zaman onaylanır.

## <a name="caccesstokenistokenrestricted"></a><a name="istokenrestricted"></a> CAccessToken:: ıstokenrestricted

`CAccessToken`Nesnenin kısıtlı SID 'lerin bir listesini içerip içermiyorsa test etmek için bu yöntemi çağırın.

```cpp
bool IsTokenRestricted() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne bir kısıtlama SID listesi içeriyorsa TRUE, hiçbir SID kısıtlaması yoksa veya yöntem başarısız olursa FALSE döndürür.

## <a name="caccesstokenloaduserprofile"></a><a name="loaduserprofile"></a> CAccessToken:: LoadUserProfile

Nesneyle ilişkili kullanıcı profilini yüklemek için bu yöntemi çağırın `CAccessToken` .

```cpp
bool LoadUserProfile() throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, `CAccessToken` geçerli bir belirteç içermiyorsa veya bir kullanıcı profili zaten varsa bir onaylama hatası oluşur.

## <a name="caccesstokenlogonuser"></a><a name="logonuser"></a> CAccessToken:: LogonUser

Verilen kimlik bilgileriyle ilişkili kullanıcı için bir oturum açma oturumu oluşturmak için bu yöntemi çağırın.

```cpp
bool LogonUser(
    LPCTSTR pszUserName,
    LPCTSTR pszDomain,
    LPCTSTR pszPassword,
    DWORD dwLogonType = LOGON32_LOGON_INTERACTIVE,
    DWORD dwLogonProvider = LOGON32_PROVIDER_DEFAULT) throw();
```

### <a name="parameters"></a>Parametreler

*pszUserName*<br/>
Kullanıcı adını belirten, null ile sonlandırılmış bir dize işaretçisi. Bu, oturum açmak için Kullanıcı hesabının adıdır.

*pszDomain*<br/>
Hesap veritabanı *pszUserName* hesabını içeren etki alanı veya sunucu adını belirten null ile sonlandırılmış bir dize işaretçisi.

*pszPassword*<br/>
*PszUserName* tarafından belirtilen kullanıcı hesabının şifresiz metin parolasını belirten null ile sonlandırılmış bir dize işaretçisi.

*dwLogonType*<br/>
Gerçekleştirilecek oturum açma işlemi türünü belirtir. Daha fazla ayrıntı için bkz. [LogonUser](/windows/win32/api/winbase/nf-winbase-logonuserw) .

*dwLogonProvider*<br/>
Oturum açma sağlayıcısını belirtir. Daha fazla ayrıntı için bkz. [LogonUser](/windows/win32/api/winbase/nf-winbase-logonuserw) .

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Oturum açma işleminden kaynaklanan erişim belirteci ile ilişkilendirilir `CAccessToken` . Bu yöntemin başarılı olması için, `CAccessToken` nesnenin, güvenilir bilgisayar tabanının bir parçası olarak sahibini tanımlayarak SE_TCB_NAME ayrıcalıklarını tutması gerekir. Gerekli ayrıcalıklar hakkında daha fazla bilgi için bkz. [LogonUser](/windows/win32/api/winbase/nf-winbase-logonuserw) .

## <a name="caccesstokenopencomclienttoken"></a><a name="opencomclienttoken"></a> CAccessToken:: OpenCOMClientToken

Com istemcisinden erişim belirteci ile başlatmak için bir istemciden çağrıyı işleyen bir COM sunucusu içinden bu yöntemi çağırın `CAccessToken` .

```cpp
bool OpenCOMClientToken(
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```

### <a name="parameters"></a>Parametreler

*dwDesiredAccess*<br/>
Erişim belirtecine istenen erişim türlerini belirten bir erişim maskesini belirtir. Bu istenen erişim türleri, hangi erişimlerin verildiğini veya reddedildiğini belirleyen belirtecin DACL 'si ile karşılaştırılır.

*bImpersonate*<br/>
TRUE ise, bu çağrı başarıyla tamamlanırsa, geçerli iş parçacığı çağıran COM istemcisinin kimliğine bürünecektir. FALSE ise, erişim belirteci açılır, ancak bu çağrı tamamlandığında iş parçacığı kimliğe bürünme belirtecine sahip olmaz.

*bOpenAsSelf*<br/>
Erişim denetiminin, [GetThreadToken](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) metodunu çağıran iş parçacığının güvenlik bağlamına veya çağıran iş parçacığı için işlemin güvenlik bağlamına karşı yapılıp yapılmayacağını belirtir.

Bu parametre FALSE ise, erişim denetimi çağıran iş parçacığının güvenlik bağlamı kullanılarak gerçekleştirilir. İş parçacığı bir istemciyi taklit alıyorsa, bu güvenlik bağlamı bir istemci işlemi olabilir. Bu parametre TRUE ise, erişim denetimi çağıran iş parçacığı için işlemin güvenlik bağlamı kullanılarak yapılır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

[CAutoRevertImpersonation sınıfı](../../atl/reference/cautorevertimpersonation-class.md) , *BIMPERSONATE* bayrağı true olarak ayarlanarak oluşturulan kimliğe bürünme erişim belirteçlerini otomatik olarak geri almak için kullanılabilir.

## <a name="caccesstokenopennamedpipeclienttoken"></a><a name="opennamedpipeclienttoken"></a> CAccessToken:: OpenNamedPipeClientToken

İstemciden erişim belirteci ile başlatmak için adlandırılmış bir kanal üzerinden istek alan bir sunucu içinden bu yöntemi çağırın `CAccessToken` .

```cpp
bool OpenNamedPipeClientToken(
    HANDLE hPipe,
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```

### <a name="parameters"></a>Parametreler

*hPipe*<br/>
Adlandırılmış kanal için tanıtıcı.

*dwDesiredAccess*<br/>
Erişim belirtecine istenen erişim türlerini belirten bir erişim maskesini belirtir. Bu istenen erişim türleri, hangi erişimlerin verildiğini veya reddedildiğini belirleyen belirtecin DACL 'si ile karşılaştırılır.

*bImpersonate*<br/>
TRUE ise, bu çağrı başarıyla tamamlanırsa, geçerli iş parçacığı çağıran kanal istemcisinin kimliğine bürünecektir. FALSE ise, erişim belirteci açılır, ancak bu çağrı tamamlandığında iş parçacığı kimliğe bürünme belirtecine sahip olmaz.

*bOpenAsSelf*<br/>
Erişim denetiminin, [GetThreadToken](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) metodunu çağıran iş parçacığının güvenlik bağlamına veya çağıran iş parçacığı için işlemin güvenlik bağlamına karşı yapılıp yapılmayacağını belirtir.

Bu parametre FALSE ise, erişim denetimi çağıran iş parçacığının güvenlik bağlamı kullanılarak gerçekleştirilir. İş parçacığı bir istemciyi taklit alıyorsa, bu güvenlik bağlamı bir istemci işlemi olabilir. Bu parametre TRUE ise, erişim denetimi çağıran iş parçacığı için işlemin güvenlik bağlamı kullanılarak yapılır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

[CAutoRevertImpersonation sınıfı](../../atl/reference/cautorevertimpersonation-class.md) , *BIMPERSONATE* bayrağı true olarak ayarlanarak oluşturulan kimliğe bürünme erişim belirteçlerini otomatik olarak geri almak için kullanılabilir.

## <a name="caccesstokenopenrpcclienttoken"></a><a name="openrpcclienttoken"></a> CAccessToken:: OpenRPCClientToken

İstemciden erişim belirteci ile başlatmak için bir RPC istemcisinden çağrıyı işleyen bir sunucu içinden bu yöntemi çağırın `CAccessToken` .

```cpp
bool OpenRPCClientToken(
    RPC_BINDING_HANDLE BindingHandle,
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```

### <a name="parameters"></a>Parametreler

*BindingHandle*<br/>
Bir istemciye bağlamayı temsil eden sunucuda bağlama tanıtıcısı.

*dwDesiredAccess*<br/>
Erişim belirtecine istenen erişim türlerini belirten bir erişim maskesini belirtir. Bu istenen erişim türleri, hangi erişimlerin verildiğini veya reddedildiğini belirleyen belirtecin DACL 'si ile karşılaştırılır.

*bImpersonate*<br/>
DOĞRU ise, bu çağrı başarıyla tamamlanırsa, geçerli iş parçacığı çağıran RPC istemcisinin kimliğine bürünecektir. FALSE ise, erişim belirteci açılır, ancak bu çağrı tamamlandığında iş parçacığı kimliğe bürünme belirtecine sahip olmaz.

*bOpenAsSelf*<br/>
Erişim denetiminin, [GetThreadToken](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) metodunu çağıran iş parçacığının güvenlik bağlamına veya çağıran iş parçacığı için işlemin güvenlik bağlamına karşı yapılıp yapılmayacağını belirtir.

Bu parametre FALSE ise, erişim denetimi çağıran iş parçacığının güvenlik bağlamı kullanılarak gerçekleştirilir. İş parçacığı bir istemciyi taklit alıyorsa, bu güvenlik bağlamı bir istemci işlemi olabilir. Bu parametre TRUE ise, erişim denetimi çağıran iş parçacığı için işlemin güvenlik bağlamı kullanılarak yapılır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

[CAutoRevertImpersonation sınıfı](../../atl/reference/cautorevertimpersonation-class.md) , *BIMPERSONATE* bayrağı true olarak ayarlanarak oluşturulan kimliğe bürünme erişim belirteçlerini otomatik olarak geri almak için kullanılabilir.

## <a name="caccesstokenopenthreadtoken"></a><a name="openthreadtoken"></a> CAccessToken:: OpenThreadToken

Kimliğe bürünme düzeyini ayarlamak için bu yöntemi çağırın ve ardından öğesini `CAccessToken` verilen iş parçacığından belirteç ile başlatın.

```cpp
bool OpenThreadToken(
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true,
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) throw(...);
```

### <a name="parameters"></a>Parametreler

*dwDesiredAccess*<br/>
Erişim belirtecine istenen erişim türlerini belirten bir erişim maskesini belirtir. Bu istenen erişim türleri, hangi erişimlerin verildiğini veya reddedildiğini belirleyen belirtecin DACL 'si ile karşılaştırılır.

*bImpersonate*<br/>
TRUE ise, bu yöntem tamamlandıktan sonra iş parçacığı istenen kimliğe bürünme düzeyinde bırakılır. YANLıŞ ise, iş parçacığı özgün kimliğe bürünme düzeyine döndürülür.

*bOpenAsSelf*<br/>
Erişim denetiminin, [GetThreadToken](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) metodunu çağıran iş parçacığının güvenlik bağlamına veya çağıran iş parçacığı için işlemin güvenlik bağlamına karşı yapılıp yapılmayacağını belirtir.

Bu parametre FALSE ise, erişim denetimi çağıran iş parçacığının güvenlik bağlamı kullanılarak gerçekleştirilir. İş parçacığı bir istemciyi taklit alıyorsa, bu güvenlik bağlamı bir istemci işlemi olabilir. Bu parametre TRUE ise, erişim denetimi çağıran iş parçacığı için işlemin güvenlik bağlamı kullanılarak yapılır.

*Sil*<br/>
Belirtecin kimliğe bürünme düzeyini sağlayan [SECURITY_IMPERSONATION_LEVEL](/windows/win32/api/winnt/ne-winnt-security_impersonation_level) numaralandırılmış bir tür belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

`OpenThreadToken` , [CAccessToken:: GetThreadToken](#getthreadtoken)öğesine benzerdir, ancak `CAccessToken` iş parçacığının erişim belirtecinden başlatmadan önce kimliğe bürünme düzeyini ayarlar.

[CAutoRevertImpersonation sınıfı](../../atl/reference/cautorevertimpersonation-class.md) , *BIMPERSONATE* bayrağı true olarak ayarlanarak oluşturulan kimliğe bürünme erişim belirteçlerini otomatik olarak geri almak için kullanılabilir.

## <a name="caccesstokenprivilegecheck"></a><a name="privilegecheck"></a> CAccessToken::P rivilegeCheck

Nesnede belirtilen ayrıcalık kümesinin etkinleştirilip etkinleştirilmeyeceğini anlamak için bu yöntemi çağırın `CAccessToken` .

```cpp
bool PrivilegeCheck(
    PPRIVILEGE_SET RequiredPrivileges,
    bool* pbResult) const throw();
```

### <a name="parameters"></a>Parametreler

*RequiredPrivileges*<br/>
[PRIVILEGE_SET](/windows/win32/api/winnt/ns-winnt-privilege_set) yapısına yönelik işaretçi.

*pbResult*<br/>
Yöntemin bir değere işaretçisi, belirtilen ayrıcalığın herhangi birinin veya tümünün nesnede etkin olup olmadığını belirtmek için ayarlanır `CAccessToken` .

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

`PrivilegeCheck`Döndüğünde, `Attributes` her [LUID_AND_ATTRIBUTES](/windows/win32/api/winnt/ns-winnt-luid_and_attributes) yapısının üyesi, karşılık gelen ayrıcalık etkinse SE_PRIVILEGE_USED_FOR_ACCESS olarak ayarlanır. Bu yöntem, [PrivilegeCheck](/windows/win32/api/securitybaseapi/nf-securitybaseapi-privilegecheck) Win32 işlevini çağırır.

## <a name="caccesstokenrevert"></a><a name="revert"></a> CAccessToken:: çevir

Bir iş parçacığını kimliğe bürünme belirtecini kullanarak durdurmak için bu yöntemi çağırın.

```cpp
bool Revert(HANDLE hThread = NULL) const throw();
```

### <a name="parameters"></a>Parametreler

*hThread*<br/>
Kimliğe bürünme işleminden dönmek için iş parçacığına işleyin. *HThread* null ise, geçerli iş parçacığı kabul edilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Kimliğe bürünme belirteçlerinin yeniden sürümü [CAutoRevertImpersonation sınıfıyla](../../atl/reference/cautorevertimpersonation-class.md)otomatik olarak gerçekleştirilebilir.

## <a name="caccesstokensetdefaultdacl"></a><a name="setdefaultdacl"></a> CAccessToken:: SetDefaultDacl

Nesnenin varsayılan DACL 'sini ayarlamak için bu yöntemi çağırın `CAccessToken` .

```cpp
bool SetDefaultDacl(const CDacl& rDacl) throw(...);
```

### <a name="parameters"></a>Parametreler

*rDacl*<br/>
Yeni varsayılan [CDacl sınıfı](../../atl/reference/cdacl-class.md) bilgileri.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Varsayılan DACL, bu erişim belirteci etkin olarak yeni nesneler oluşturulduğunda varsayılan olarak kullanılan DACL 'dir.

## <a name="caccesstokensetowner"></a><a name="setowner"></a> CAccessToken:: SetOwner

Nesnenin sahibini ayarlamak için bu yöntemi çağırın `CAccessToken` .

```cpp
bool SetOwner(const CSid& rSid) throw(...);
```

### <a name="parameters"></a>Parametreler

*Rsıd*<br/>
Sahip bilgilerini içeren [CSID sınıfı](../../atl/reference/csid-class.md) nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu erişim belirteci etkin durumdayken oluşturulan yeni nesneler için kullanılan varsayılan sahibdir.

## <a name="caccesstokensetprimarygroup"></a><a name="setprimarygroup"></a> CAccessToken:: SetPrimaryGroup

Nesnenin birincil grubunu ayarlamak için bu yöntemi çağırın `CAccessToken` .

```cpp
bool SetPrimaryGroup(const CSid& rSid) throw(...);
```

### <a name="parameters"></a>Parametreler

*Rsıd*<br/>
Birincil grup bilgilerini içeren [CSID sınıfı](../../atl/reference/csid-class.md) nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Birincil grup, bu erişim belirteci etkin durumdayken oluşturulan yeni nesneler için varsayılan gruptur.

## <a name="see-also"></a>Ayrıca bkz.

[ATLSecurity örneği](../../overview/visual-cpp-samples.md)<br/>
[Erişim belirteçleri](/windows/win32/SecAuthZ/access-tokens)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
