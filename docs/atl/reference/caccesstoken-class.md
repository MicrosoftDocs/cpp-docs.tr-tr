---
title: CAccessToken Sınıfı
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
ms.openlocfilehash: 9ae63946dfa6244e97c376f9eccd9bab93586990
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319033"
---
# <a name="caccesstoken-class"></a>CAccessToken Sınıfı

Bu sınıf, erişim belirteci için bir sarmalayıcıdır.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CAccessToken
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAccessToken::~CAccessToken](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAccessToken::Ekle](#attach)|Verilen erişim belirteç tutamacının sahipliğini almak için bu yöntemi arayın.|
|[CAccessToken::CheckTokenÜyelik](#checktokenmembership)|Nesnede belirli bir SID etkin olup `CAccessToken` olmadığını belirlemek için bu yöntemi çağırın.|
|[CAccessToken::CreateImpersonationToken](#createimpersonationtoken)|Yeni bir kimliğe bürünme erişim jetonu oluşturmak için bu yöntemi arayın.|
|[CAccessToken::CreatePrimaryToken](#createprimarytoken)|Yeni bir birincil belirteç oluşturmak için bu yöntemi arayın.|
|[CAccessToken::CreateProcessAsUser](#createprocessasuser)|`CAccessToken` Nesne tarafından temsil edilen kullanıcının güvenlik bağlamında çalışan yeni bir işlem oluşturmak için bu yöntemi çağırın.|
|[CAccessToken::CreateRestrictedToken](#createrestrictedtoken)|Yeni, kısıtlanmış `CAccessToken` bir nesne oluşturmak için bu yöntemi çağırın.|
|[CAccessToken::Detach](#detach)|Erişim belirteci sahipliğini iptal etmek için bu yöntemi arayın.|
|[CAccessToken::DisablePrivilege](#disableprivilege)|Nesnedeki bir ayrıcalığı devre dışı `CAccessToken` kalmak için bu yöntemi çağırın.|
|[CAccessToken::DisableAyrıcalıklar](#disableprivileges)|Nesnedeki bir veya daha fazla ayrıcalığı `CAccessToken` devre dışı kıdamak için bu yöntemi çağırın.|
|[CAccessToken::Etkinleştirme Ayrıcalığı](#enableprivilege)|Nesnede bir ayrıcalık sağlamak `CAccessToken` için bu yöntemi çağırın.|
|[CAccessToken::Ayrıcalıkları Etkinleştir](#enableprivileges)|Nesnede bir veya daha fazla ayrıcalığı etkinleştirmek için bu yöntemi çağırın. `CAccessToken`|
|[CAccessToken::GetDefaultDacl](#getdefaultdacl)|Nesnenin `CAccessToken` varsayılan DACL'sini döndürmek için bu yöntemi çağırın.|
|[CAccessToken::GetEffectiveToken](#geteffectivetoken)|Geçerli iş parçacığı `CAccessToken` için geçerli olan erişim belirteci ne eşit nesne almak için bu yöntemi arayın.|
|[CAccessToken::GetGroups](#getgroups)|Nesnenin belirteç `CAccessToken` gruplarını döndürmek için bu yöntemi çağırın.|
|[CAccessToken::GetHandle](#gethandle)|Erişim belirteci için bir tanıtıcı almak için bu yöntemi arayın.|
|[CAccessToken::GetImpersonationLevel](#getimpersonationlevel)|Erişim jetonundan kimliğe bürünme düzeyini almak için bu yöntemi arayın.|
|[CAccessToken::GetLogonSessionId](#getlogonsessionid)|`CAccessToken` Nesneyle ilişkili Oturum Kimliği'ni almak için bu yöntemi arayın.|
|[CAccessToken::GetLogonSid](#getlogonsid)|`CAccessToken` Nesneyle ilişkili Logon SID'yi almak için bu yöntemi arayın.|
|[CAccessToken::GetOwner](#getowner)|Sahibinin `CAccessToken` nesneyle ilişkilendirilmesini sağlamak için bu yöntemi arayın.|
|[CAccessToken::GetPrimaryGroup](#getprimarygroup)|Nesneyle ilişkili birincil grubu almak `CAccessToken` için bu yöntemi çağırın.|
|[CAccessToken::Ayrıcalıkları Alın](#getprivileges)|`CAccessToken` Nesneyle ilişkili ayrıcalıkları almak için bu yöntemi arayın.|
|[CAccessToken::GetProcessToken](#getprocesstoken)|Verilen işlemden erişim `CAccessToken` belirteci ile başlatılması için bu yöntemi arayın.|
|[CAccessToken::GetProfile](#getprofile)|Nesneyle `CAccessToken` ilişkili kullanıcı profilini gösteren tutamacı almak için bu yöntemi arayın.|
|[CAccessToken::GetSource](#getsource)|`CAccessToken` Nesnenin kaynağını almak için bu yöntemi arayın.|
|[CAccessToken::İstatistik leri alın](#getstatistics)|`CAccessToken` Nesneyle ilişkili bilgileri almak için bu yöntemi arayın.|
|[CAccessToken::GetTerminalServicesSessionId](#getterminalservicessessionid)|`CAccessToken` Nesneyle ilişkili Terminal Hizmetleri Oturum Kimliği'ni almak için bu yöntemi arayın.|
|[CAccessToken::GetThreadToken](#getthreadtoken)|Verilen iş parçacığından `CAccessToken` belirteç ile baş harflerini almak için bu yöntemi arayın.|
|[CAccessToken::GetTokenId](#gettokenid)|`CAccessToken` Nesneyle ilişkili Token Kimliğini almak için bu yöntemi arayın.|
|[CAccessToken::GetType](#gettype)|`CAccessToken` Nesnenin belirteç türünü almak için bu yöntemi arayın.|
|[CAccessToken::GetUser](#getuser)|Nesneyle ilişkili kullanıcıyı tanımlamak `CAccessToken` için bu yöntemi çağırın.|
|[CAccessToken::HKeyCurrentUser](#hkeycurrentuser)|Nesneyle `CAccessToken` ilişkili kullanıcı profilini gösteren tutamacı almak için bu yöntemi arayın.|
|[CAccessToken::Kimliğime göre](#impersonate)|Bir iş parçacığına kimliğe `CAccessToken` bürünme atamak için bu yöntemi çağırın.|
|[CAccessToken::ImpersonateLoggedOnUser](#impersonateloggedonuser)|Arama iş parçacığının oturum açmış bir kullanıcının güvenlik bağlamını taklit etmesine izin vermek için bu yöntemi arayın.|
|[CAccessToken::IsTokenRestricted](#istokenrestricted)|Nesnenin `CAccessToken` kısıtlanmış SIT'lerin bir listesini içerip içermeden test etmek için bu yöntemi arayın.|
|[CAccessToken::LoadUserProfile](#loaduserprofile)|`CAccessToken` Nesneyle ilişkili kullanıcı profilini yüklemek için bu yöntemi arayın.|
|[CAccessToken::LogonUser](#logonuser)|Verilen kimlik bilgileriyle ilişkili kullanıcı için bir oturum açma oturumu oluşturmak için bu yöntemi arayın.|
|[CAccessToken::OpenCOMClientToken](#opencomclienttoken)|Bu yöntemi, com istemcisinden erişim belirteci `CAccessToken` ile başlatılması için bir istemciden bir çağrı işleme com sunucusu içinden arayın.|
|[CAccessToken::OpenNamedPipeClientToken](#opennamedpipeclienttoken)|İstemciden erişim belirteci `CAccessToken` ile baş harflerini almak için adlandırılmış bir boru üzerinden istek alarak bir sunucu içinden bu yöntemi arayın.|
|[CAccessToken::OpenRPCClientToken](#openrpcclienttoken)|Bu yöntemi, istemciden erişim belirteci `CAccessToken` yle birlikte başlatılması için bir RPC istemcisinden gelen bir aramayı işleyen bir sunucunun içinden arayın.|
|[CAccessToken::OpenThreadToken](#openthreadtoken)|Kimliğe bürünme düzeyini ayarlamak için bu `CAccessToken` yöntemi çağırın ve ardından verilen iş parçacığından belirteçle birlikte başlatılmasını önadlandırın.|
|[CAccessToken::PrivilegeCheck](#privilegecheck)|`CAccessToken` Nesnede belirli bir ayrıcalık kümesinin etkin olup olmadığını belirlemek için bu yöntemi çağırın.|
|[CAccessToken::Geri](#revert)|Kimliğe bürünme belirteci kullanan bir iş parçacığı durdurmak için bu yöntemi arayın.|
|[CAccessToken::SetDefaultDacl](#setdefaultdacl)|`CAccessToken` Nesnenin varsayılan DACL ayarlamak için bu yöntemi arayın.|
|[CAccessToken::SetSahibi](#setowner)|Nesnenin sahibini ayarlamak için `CAccessToken` bu yöntemi çağırın.|
|[CAccessToken::SetPrimaryGroup](#setprimarygroup)|Nesnenin birincil grubunu ayarlamak için `CAccessToken` bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

[Erişim belirteci,](/windows/win32/SecAuthZ/access-tokens) bir işlemin veya iş parçacığının güvenlik bağlamını açıklayan ve windows sistemine oturum açmış her kullanıcıya ayrılan bir nesnedir.

Windows'daki erişim denetimi modeline giriş için Windows SDK'daki [Access Denetimi'ne](/windows/win32/SecAuthZ/access-control) bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity.h

## <a name="caccesstokenattach"></a><a name="attach"></a>CAccessToken::Ekle

Verilen erişim belirteç tutamacının sahipliğini almak için bu yöntemi arayın.

```
void Attach(HANDLE hToken) throw();
```

### <a name="parameters"></a>Parametreler

*hToken*<br/>
Erişim jetonuna bir tutamaç.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama oluştururda, nesne zaten `CAccessToken` bir erişim belirteci sahipliğine sahipse bir tasnif hatası oluşur.

## <a name="caccesstokencaccesstoken"></a><a name="dtor"></a>CAccessToken::~CAccessToken

Yıkıcı.

```
virtual ~CAccessToken() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest sağlar.

## <a name="caccesstokenchecktokenmembership"></a><a name="checktokenmembership"></a>CAccessToken::CheckTokenÜyelik

Nesnede belirli bir SID etkin olup `CAccessToken` olmadığını belirlemek için bu yöntemi çağırın.

```
bool CheckTokenMembership(
    const CSid& rSid,
    bool* pbIsMember) const throw(...);
```

### <a name="parameters"></a>Parametreler

*rSid*<br/>
[CSid Sınıfı](../../atl/reference/csid-class.md) nesnesine başvuru.

*pbIsÜye*<br/>
Denetimin sonuçlarını alan bir değişkeni işaretleyin.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

Yöntem, `CheckTokenMembership` kullanıcıdaki SID'nin varlığını ve erişim belirteci grubundaki SID'lerin grup larını denetler. SID varsa ve SE_GROUP_ENABLED özniteliği varsa, *pbIsMember* TRUE olarak ayarlanır; aksi takdirde, FALSE olarak ayarlanır.

Hata ayıklama oluştururda, *pbIsMember* geçerli bir işaretçi değilse bir tasnif hatası oluşur.

> [!NOTE]
> Nesne `CAccessToken` birincil belirteç değil, bir kimliğe bürünme belirteci olmalıdır.

## <a name="caccesstokencreateimpersonationtoken"></a><a name="createimpersonationtoken"></a>CAccessToken::CreateImpersonationToken

Kimliğe bürünme erişim jetonu oluşturmak için bu yöntemi arayın.

```
bool CreateImpersonationToken(
    CAccessToken* pImp,
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pImp*<br/>
Yeni `CAccessToken` nesneye işaretçi.

*sil*<br/>
Yeni belirteçteki kimliğe bürünme düzeyini sağlayan [SECURITY_IMPERSONATION_LEVEL](/windows/win32/api/winnt/ne-winnt-security_impersonation_level) numaralandırılmış bir türü belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

`CreateImpersonationToken`yeni bir kimliğe bürünme belirteci oluşturmak için [Yinelenen Token'i](/windows/win32/api/securitybaseapi/nf-securitybaseapi-duplicatetoken) çağırır.

## <a name="caccesstokencreateprimarytoken"></a><a name="createprimarytoken"></a>CAccessToken::CreatePrimaryToken

Yeni bir birincil belirteç oluşturmak için bu yöntemi arayın.

```
bool CreatePrimaryToken(
    CAccessToken* pPri,
    DWORD dwDesiredAccess = MAXIMUM_ALLOWED,
    const CSecurityAttributes* pTokenAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pPri*<br/>
Yeni `CAccessToken` nesneye işaretçi.

*dwDesiredAccess*<br/>
Yeni belirteç için istenen erişim haklarını belirtir. Varsayılan, MAXIMUM_ALLOWED, arayan için geçerli olan tüm erişim haklarını ister. Erişim hakları hakkında daha fazla bilgi için [Erişim Hakları ve Erişim Maskeleri'ne](/windows/win32/SecAuthZ/access-rights-and-access-masks) bakın.

*pTokenAttributes*<br/>
Yeni belirteç için bir güvenlik tanımlayıcısı belirten ve alt işlemlerin belirteci devralıp alamadığını belirleyen [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) bir yapıyı işaretle. *pTokenÖzler* NULL ise, belirteç varsayılan güvenlik tanımlayıcısı alır ve tutamacı devralınamaz.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

`CreatePrimaryToken`yeni bir birincil belirteç oluşturmak için [DuplicateTokenEx](/windows/win32/api/securitybaseapi/nf-securitybaseapi-duplicatetokenex) çağırır.

## <a name="caccesstokencreateprocessasuser"></a><a name="createprocessasuser"></a>CAccessToken::CreateProcessAsUser

`CAccessToken` Nesne tarafından temsil edilen kullanıcının güvenlik bağlamında çalışan yeni bir işlem oluşturmak için bu yöntemi çağırın.

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
Yürütülecek modülü belirten null-sonlandırılan dize işaretçi. Bu parametre NULL olmayabilir.

*pCommandLine*<br/>
Yürütülecek komut satırını belirten null-sonlandırılan dize işaretçi.

*pProcessInformation*<br/>
Yeni işlem le ilgili kimlik bilgilerini alan PROCESS_INFORMATION bir [yapıyı](/windows/win32/api/processthreadsapi/ns-processthreadsapi-process_information) işaretçi.

*pStartupInfo*<br/>
Yeni işlem için ana pencerenin nasıl görüneceklerini belirten bir [STARTUPINFO](/windows/win32/api/processthreadsapi/ns-processthreadsapi-startupinfow) yapısıiçin işaretçi.

*dwCreationFlags*<br/>
Öncelik sınıfını ve işlemin oluşturulmasını denetleyen ek bayraklar belirtir. Bayrakların listesi için [CreateProcessAsUser](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessasuserw) win32 işlevine bakın.

*bLoadProfile*<br/>
TRUE ise, kullanıcının profili [LoadUserProfile](/windows/win32/api/userenv/nf-userenv-loaduserprofilew)ile yüklenir.

*pProcessAttributes*<br/>
Yeni işlem için bir güvenlik tanımlayıcısı belirten ve alt işlemlerin döndürülen tutamacı devralıp alamadığını belirleyen [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) bir yapıyı işaretle. *pProcessAttributes* NULL ise, işlem varsayılan bir güvenlik tanımlayıcısı alır ve tanıtıcı devralınamaz.

*pThreadAttributes*<br/>
Yeni iş parçacığı için bir güvenlik tanımlayıcısı belirten ve alt işlemlerin döndürülen tutamacı devralıp alamadığını belirleyen [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) bir yapıyı işaretle. *pThreadAttributes* NULL ise, iş parçacığı varsayılan güvenlik tanımlayıcısı alır ve işkolu devralınamaz.

*bInherit*<br/>
Yeni işlemin arama işleminden devralınıp devralmadığını gösterir. TRUE ise, arama işlemindeki her devralınabilen açık tanıtıcı yeni işlem tarafından devralır. Devralınan tutamaçları, özgün tutamaçlarıyla aynı değere ve erişim ayrıcalıklarına sahiptir.

*pCurrentDirectory*<br/>
Geçerli sürücüyü ve yeni işlem dizinini belirten null-sonlandırılan dizeişaretçi. Dize, sürücü harfi içeren tam bir yol olmalıdır. Bu parametre NULL ise, yeni işlem arama işlemiyle aynı geçerli sürücüye ve dizine sahip olur.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

`CreateProcessAsUser`nesne `CreateProcessAsUser` tarafından temsil edilen kullanıcının güvenlik bağlamında çalışan yeni bir işlem oluşturmak için Win32 işlevini kullanır. `CAccessToken` Gerekli parametrelerin tam olarak tartışılması için [CreateProcessAsUser](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessasuserw) işlevinin açıklamasına bakın.

Bu yöntemin başarılı `CAccessToken` olabilmesi için, nesnenin Birincil Belirteç Atama (sınırlı bir belirteç olmadığı sürece) ve ArtırKota ayrıcalıklarını tutması gerekir.

## <a name="caccesstokencreaterestrictedtoken"></a><a name="createrestrictedtoken"></a>CAccessToken::CreateRestrictedToken

Yeni, kısıtlanmış `CAccessToken` bir nesne oluşturmak için bu yöntemi çağırın.

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
Yalnızca `CTokenGroups` reddedilen SIT'leri belirten bir nesne.

*SidsToRestrict*<br/>
Kısıtlayan SIT'leri belirten bir `CTokenGroups` nesne.

*AyrıcalıklarToDelete*<br/>
Kısıtlanmış belirteçte silmek için ayrıcalıkları belirten bir `CTokenPrivileges` nesne. Varsayılan boş bir nesne oluşturur.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

`CreateRestrictedToken`kısıtlamalarla birlikte yeni `CAccessToken` bir nesne oluşturmak için [CreateRestrictedToken](/windows/win32/api/securitybaseapi/nf-securitybaseapi-createrestrictedtoken) Win32 işlevini kullanır.

> [!IMPORTANT]
> Kullanırken, `CreateRestrictedToken`aşağıdakileri sağlar: varolan belirteç geçerlidir (ve kullanıcı tarafından girilmez) ve *SidsToDisable* ve *PrivilegesToDelete* hem geçerlidir (hem de kullanıcı tarafından girilmez). Yöntem FALSE döndürürse, işlevselliği reddedin.

## <a name="caccesstokendetach"></a><a name="detach"></a>CAccessToken::Detach

Erişim belirteci sahipliğini iptal etmek için bu yöntemi arayın.

```
HANDLE Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Tutamacı ayrılmış `CAccessToken` olana döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `CAccessToken`erişim belirteci 'sahipliğini iptal eder.

## <a name="caccesstokendisableprivilege"></a><a name="disableprivilege"></a>CAccessToken::DisablePrivilege

Nesnedeki bir ayrıcalığı devre dışı `CAccessToken` kalmak için bu yöntemi çağırın.

```
bool DisablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>Parametreler

*pszPrivilege*<br/>
`CAccessToken` Nesnede devre dışı kalmak için ayrıcalığı içeren bir dize işaretçi.

*pPreviousState*<br/>
Ayrıcalıkların `CTokenPrivileges` önceki durumunu içerecek bir nesneye işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

## <a name="caccesstokendisableprivileges"></a><a name="disableprivileges"></a>CAccessToken::DisableAyrıcalıklar

Nesnedeki bir veya daha fazla ayrıcalığı `CAccessToken` devre dışı kıdamak için bu yöntemi çağırın.

```
bool DisablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>Parametreler

*rAyrıcalıklar*<br/>
`CAccessToken` Nesnede devre dışı kalmak için ayrıcalıkları içeren dizeleri bir dizi işaretçi.

*pPreviousState*<br/>
Ayrıcalıkların `CTokenPrivileges` önceki durumunu içerecek bir nesneye işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

## <a name="caccesstokenenableprivilege"></a><a name="enableprivilege"></a>CAccessToken::Etkinleştirme Ayrıcalığı

Nesnede bir ayrıcalık sağlamak `CAccessToken` için bu yöntemi çağırın.

```
bool EnablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>Parametreler

*pszPrivilege*<br/>
Nesnede etkinleştirmek için ayrıcalık içeren `CAccessToken` bir dize işaretçi.

*pPreviousState*<br/>
Ayrıcalıkların `CTokenPrivileges` önceki durumunu içerecek bir nesneye işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

## <a name="caccesstokenenableprivileges"></a><a name="enableprivileges"></a>CAccessToken::Ayrıcalıkları Etkinleştir

Nesnede bir veya daha fazla ayrıcalığı etkinleştirmek için bu yöntemi çağırın. `CAccessToken`

```
bool EnablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>Parametreler

*rAyrıcalıklar*<br/>
`CAccessToken` Nesnede etkinleştirmek için ayrıcalıkları içeren dizeleri bir dizi işaretçi.

*pPreviousState*<br/>
Ayrıcalıkların `CTokenPrivileges` önceki durumunu içerecek bir nesneye işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

## <a name="caccesstokengetdefaultdacl"></a><a name="getdefaultdacl"></a>CAccessToken::GetDefaultDacl

Nesnenin `CAccessToken` varsayılan DACL'sini döndürmek için bu yöntemi çağırın.

```
bool GetDefaultDacl(CDacl* pDacl) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pDacl*<br/>
Nesnenin varsayılan DACL'sini alacak `CAccessToken` [CDacl Sınıfı](../../atl/reference/cdacl-class.md) nesnesine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Varsayılan DACL kurtarıldıysa TRUE döndürür, aksi takdirde FALSE.

## <a name="caccesstokengeteffectivetoken"></a><a name="geteffectivetoken"></a>CAccessToken::GetEffectiveToken

Geçerli iş parçacığı `CAccessToken` için geçerli olan erişim belirteci ne eşit nesne almak için bu yöntemi arayın.

```
bool GetEffectiveToken(DWORD dwDesiredAccess) throw();
```

### <a name="parameters"></a>Parametreler

*dwDesiredAccess*<br/>
İstenilen erişim belirteci türlerini belirten bir erişim maskesi belirtir. İstenen bu erişim türleri, hangi erişimlerin verildiğini veya reddedildiğini belirlemek için belirteci'nin DACL'si ile karşılaştırılır.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

## <a name="caccesstokengetgroups"></a><a name="getgroups"></a>CAccessToken::GetGroups

Nesnenin belirteç `CAccessToken` gruplarını döndürmek için bu yöntemi çağırın.

```
bool GetGroups(CTokenGroups* pGroups) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pGroups*<br/>
Grup bilgilerini alacak [CTokenGroups Sınıf](../../atl/reference/ctokengroups-class.md) nesnesine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

## <a name="caccesstokengethandle"></a><a name="gethandle"></a>CAccessToken::GetHandle

Erişim belirteci için bir tanıtıcı almak için bu yöntemi arayın.

```
HANDLE GetHandle() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Nesnenin erişim `CAccessToken` belirteci için bir tanıtıcı döndürür.

## <a name="caccesstokengetimpersonationlevel"></a><a name="getimpersonationlevel"></a>CAccessToken::GetImpersonationLevel

Erişim jetonundan kimliğe bürünme düzeyini almak için bu yöntemi arayın.

```
bool GetImpersonationLevel(
    SECURITY_IMPERSONATION_LEVEL* pImpersonationLevel) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pImpersonationLevel*<br/>
Kimliğe bürünme düzeyi bilgilerini alacak [bir SECURITY_IMPERSONATION_LEVEL](/windows/win32/api/winnt/ne-winnt-security_impersonation_level) numaralandırma türüne işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

## <a name="caccesstokengetlogonsessionid"></a><a name="getlogonsessionid"></a>CAccessToken::GetLogonSessionId

`CAccessToken` Nesneyle ilişkili Oturum Kimliği'ni almak için bu yöntemi arayın.

```
bool GetLogonSessionId(LUID* pluid) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pluid*<br/>
Oturum Oturum Kimliği'ni alacak bir [LUID](/windows/win32/api/winnt/ns-winnt-luid) işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama oluştururda, *pluid* geçersiz bir değerse bir tasnif hatası oluşur.

## <a name="caccesstokengetlogonsid"></a><a name="getlogonsid"></a>CAccessToken::GetLogonSid

`CAccessToken` Nesneyle ilişkili Logon SID'yi almak için bu yöntemi arayın.

```
bool GetLogonSid(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pSid*<br/>
[CSid Sınıfı](../../atl/reference/csid-class.md) nesnesine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama oluştururda, *pSid* geçersiz bir değerse bir tasnif hatası oluşur.

## <a name="caccesstokengetowner"></a><a name="getowner"></a>CAccessToken::GetOwner

Sahibinin `CAccessToken` nesneyle ilişkilendirilmesini sağlamak için bu yöntemi arayın.

```
bool GetOwner(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pSid*<br/>
[CSid Sınıfı](../../atl/reference/csid-class.md) nesnesine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

Bu erişim belirteci etkinken oluşturulan tüm nesnelerde varsayılan olarak sahip olarak ayarlanır.

## <a name="caccesstokengetprimarygroup"></a><a name="getprimarygroup"></a>CAccessToken::GetPrimaryGroup

Nesneyle ilişkili birincil grubu almak `CAccessToken` için bu yöntemi çağırın.

```
bool GetPrimaryGroup(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pSid*<br/>
[CSid Sınıfı](../../atl/reference/csid-class.md) nesnesine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

Bu erişim belirteci etkinken oluşturulan tüm nesnelerde grup varsayılan olarak ayarlanır.

## <a name="caccesstokengetprivileges"></a><a name="getprivileges"></a>CAccessToken::Ayrıcalıkları Alın

`CAccessToken` Nesneyle ilişkili ayrıcalıkları almak için bu yöntemi arayın.

```
bool GetPrivileges(CTokenPrivileges* pPrivileges) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pAyrıcalıklar*<br/>
Ayrıcalıkları alacak bir [CTokenPrivileges Class](../../atl/reference/ctokenprivileges-class.md) nesnesi için işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

## <a name="caccesstokengetprocesstoken"></a><a name="getprocesstoken"></a>CAccessToken::GetProcessToken

Verilen işlemden erişim `CAccessToken` belirteci ile başlatılması için bu yöntemi arayın.

```
bool GetProcessToken(DWORD dwDesiredAccess, HANDLE hProcess = NULL) throw();
```

### <a name="parameters"></a>Parametreler

*dwDesiredAccess*<br/>
İstenilen erişim belirteci türlerini belirten bir erişim maskesi belirtir. İstenen bu erişim türleri, hangi erişimlerin verildiğini veya reddedildiğini belirlemek için belirteci'nin DACL'si ile karşılaştırılır.

*hProcess*<br/>
Erişim belirteci açılan işlemi işleme. NULL varsayılan değeri kullanılırsa, geçerli işlem kullanılır.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

[OpenProcessToken](/windows/win32/api/processthreadsapi/nf-processthreadsapi-openprocesstoken) Win32 işlevini çağırır.

## <a name="caccesstokengetprofile"></a><a name="getprofile"></a>CAccessToken::GetProfile

Nesneyle `CAccessToken` ilişkili kullanıcı profilini gösteren tutamacı almak için bu yöntemi arayın.

```
HANDLE GetProfile() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı profilini gösteren bir tanıtıcı döndürür veya profil yoksa NULL.

## <a name="caccesstokengetsource"></a><a name="getsource"></a>CAccessToken::GetSource

`CAccessToken` Nesnenin kaynağını almak için bu yöntemi arayın.

```
bool GetSource(TOKEN_SOURCE* pSource) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pKaynak*<br/>
[TOKEN_SOURCE](/windows/win32/api/winnt/ns-winnt-token_source) bir yapıya işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

## <a name="caccesstokengetstatistics"></a><a name="getstatistics"></a>CAccessToken::İstatistik leri alın

`CAccessToken` Nesneyle ilişkili bilgileri almak için bu yöntemi arayın.

```
bool GetStatistics(TOKEN_STATISTICS* pStatistics) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pİstatistikler*<br/>
[TOKEN_STATISTICS](/windows/win32/api/winnt/ns-winnt-token_statistics) bir yapıya işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

## <a name="caccesstokengetterminalservicessessionid"></a><a name="getterminalservicessessionid"></a>CAccessToken::GetTerminalServicesSessionId

`CAccessToken` Nesneyle ilişkili Terminal Hizmetleri Oturum Kimliği'ni almak için bu yöntemi arayın.

```
bool GetTerminalServicesSessionId(DWORD* pdwSessionId) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pdwSessionId*<br/>
Terminal Hizmetleri Oturum Kimliği.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

## <a name="caccesstokengetthreadtoken"></a><a name="getthreadtoken"></a>CAccessToken::GetThreadToken

Verilen iş parçacığından `CAccessToken` belirteç ile baş harflerini almak için bu yöntemi arayın.

```
bool GetThreadToken(
    DWORD dwDesiredAccess,
    HANDLE hThread = NULL,
    bool bOpenAsSelf = true) throw();
```

### <a name="parameters"></a>Parametreler

*dwDesiredAccess*<br/>
İstenilen erişim belirteci türlerini belirten bir erişim maskesi belirtir. İstenen bu erişim türleri, hangi erişimlerin verildiğini veya reddedildiğini belirlemek için belirteci'nin DACL'si ile karşılaştırılır.

*hThread*<br/>
Erişim belirteci açık olan iş parçacığına işle.

*bOpenAsSelf*<br/>
Erişim denetiminin `GetThreadToken` yöntemi çağıran iş parçacığının güvenlik bağlamına mı yoksa arama iş parçacığı için işlemin güvenlik bağlamına karşı mı yapılacağı nı gösterir.

Bu parametre FALSE ise, erişim denetimi arama iş parçacığı nın güvenlik bağlamı kullanılarak gerçekleştirilir. İş parçacığı istemci nin kimliğine bürünüyorsa, bu güvenlik bağlamı istemci işlemine ait olabilir. Bu parametre TRUE ise, erişim denetimi arama iş parçacığı için işlemin güvenlik bağlamı kullanılarak yapılır.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

## <a name="caccesstokengettokenid"></a><a name="gettokenid"></a>CAccessToken::GetTokenId

`CAccessToken` Nesneyle ilişkili Token Kimliğini almak için bu yöntemi arayın.

```
bool GetTokenId(LUID* pluid) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pluid*<br/>
Belirteç Kimliğini alacak bir [LUID](/windows/win32/api/winnt/ns-winnt-luid) işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

## <a name="caccesstokengettype"></a><a name="gettype"></a>CAccessToken::GetType

`CAccessToken` Nesnenin belirteç türünü almak için bu yöntemi arayın.

```
bool GetType(TOKEN_TYPE* pType) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pTipi*<br/>
Başarı üzerine belirteç türünü alan [TOKEN_TYPE](/windows/win32/api/winnt/ne-winnt-token_type) değişkenin adresi.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

TOKEN_TYPE numaralandırma türü, birincil belirteç ile kimliğe bürünme belirteci arasında ayrım yapan değerler içerir.

## <a name="caccesstokengetuser"></a><a name="getuser"></a>CAccessToken::GetUser

Nesneyle ilişkili kullanıcıyı tanımlamak `CAccessToken` için bu yöntemi çağırın.

```
bool GetUser(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pSid*<br/>
[CSid Sınıfı](../../atl/reference/csid-class.md) nesnesine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

## <a name="caccesstokenhkeycurrentuser"></a><a name="hkeycurrentuser"></a>CAccessToken::HKeyCurrentUser

Nesneyle `CAccessToken` ilişkili kullanıcı profilini gösteren tutamacı almak için bu yöntemi arayın.

```
HKEY HKeyCurrentUser() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı profilini gösteren bir tanıtıcı döndürür veya profil yoksa NULL.

## <a name="caccesstokenimpersonate"></a><a name="impersonate"></a>CAccessToken::Kimliğime göre

Bir iş parçacığına kimliğe `CAccessToken` bürünme atamak için bu yöntemi çağırın.

```
bool Impersonate(HANDLE hThread = NULL) const throw(...);
```

### <a name="parameters"></a>Parametreler

*hThread*<br/>
Kimliğe bürünme belirteci atamak için iş parçacığına işle. Bu tutamak TOKEN_IMPERSONATE erişim haklarıyla açılmış olmalıdır. *hThread* NULL ise, yöntem iş parçacığının bir kimliğe bürünme belirteci kullanarak durmasına neden olur.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama oluştururda, belirteç `CAccessToken` için geçerli bir işaretçi yoksa bir tasnif hatası oluşur.

[CAutoRevertImpersonation sınıfı,](../../atl/reference/cautorevertimpersonation-class.md) taklit edilen erişim belirteçlerini otomatik olarak geri almak için kullanılabilir.

## <a name="caccesstokenimpersonateloggedonuser"></a><a name="impersonateloggedonuser"></a>CAccessToken::ImpersonateLoggedOnUser

Arama iş parçacığının oturum açmış bir kullanıcının güvenlik bağlamını taklit etmesine izin vermek için bu yöntemi arayın.

```
bool ImpersonateLoggedOnUser() const throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

> [!IMPORTANT]
> Kimliğe bürünme işlevine yapılan bir çağrı herhangi bir nedenle başarısız olursa, istemci taklit edilmez ve istemci isteği aramanın yapıldığı işlemin güvenlik bağlamında yapılır. İşlem son derece ayrıcalıklı bir hesap olarak veya bir yönetim grubunun üyesi olarak çalışıyorsa, kullanıcı aksi takdirde izin verilmeyen eylemleri gerçekleştirebilir. Bu nedenle, bu işlevin iade değeri her zaman onaylanmalıdır.

## <a name="caccesstokenistokenrestricted"></a><a name="istokenrestricted"></a>CAccessToken::IsTokenRestricted

Nesnenin `CAccessToken` kısıtlanmış SIT'lerin bir listesini içerip içermeden test etmek için bu yöntemi arayın.

```
bool IsTokenRestricted() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne, SIT'leri kısıtlayan bir liste içeriyorsa TRUE'yu döndürür, kısıtlayıcı SIT'ler yoksa VEYA yöntem başarısız olursa FALSE' olur.

## <a name="caccesstokenloaduserprofile"></a><a name="loaduserprofile"></a>CAccessToken::LoadUserProfile

`CAccessToken` Nesneyle ilişkili kullanıcı profilini yüklemek için bu yöntemi arayın.

```
bool LoadUserProfile() throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama oluştururda, geçerli bir `CAccessToken` belirteç yoksa veya bir kullanıcı profili zaten varsa bir tasnif hatası oluşur.

## <a name="caccesstokenlogonuser"></a><a name="logonuser"></a>CAccessToken::LogonUser

Verilen kimlik bilgileriyle ilişkili kullanıcı için bir oturum açma oturumu oluşturmak için bu yöntemi arayın.

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
Kullanıcı adını belirten null-sonlandırılan dize işaretçi. Bu, oturum açmak için kullanıcı hesabının adıdır.

*pszDomain*<br/>
Hesap veritabanı *nda pszUserName* hesabını bulunan etki alanının veya sunucunun adını belirten, geçersiz sonlandırılmış bir dize işaretçisi.

*pszPassword*<br/>
*pszUserName*tarafından belirtilen kullanıcı hesabıiçin açık metin parolasını belirten null-sonlandırılmış bir dize işaretçi.

*dwLogonType*<br/>
Gerçekleşecek logon işlemi nin türünü belirtir. Daha fazla bilgi için [LogonUser'a](/windows/win32/api/winbase/nf-winbase-logonuserw) bakın.

*dwLogonSağlayıcı*<br/>
Oturum açma sağlayıcısını belirtir. Daha fazla bilgi için [LogonUser'a](/windows/win32/api/winbase/nf-winbase-logonuserw) bakın.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

Oturum açmadan kaynaklanan erişim belirteci ile `CAccessToken`ilişkilendirilecektir. Bu yöntemin başarılı `CAccessToken` olabilmesi için nesnenin SE_TCB_NAME ayrıcalıklara sahip olması ve sahibini güvenilen bilgisayar tabanının bir parçası olarak tanımlaması gerekir. Gerekli ayrıcalıklarla ilgili daha fazla bilgi için [LogonUser'a](/windows/win32/api/winbase/nf-winbase-logonuserw) bakın.

## <a name="caccesstokenopencomclienttoken"></a><a name="opencomclienttoken"></a>CAccessToken::OpenCOMClientToken

Bu yöntemi, com istemcisinden erişim belirteci `CAccessToken` ile başlatılması için bir istemciden bir çağrı işleme com sunucusu içinden arayın.

```
bool OpenCOMClientToken(
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```

### <a name="parameters"></a>Parametreler

*dwDesiredAccess*<br/>
İstenilen erişim belirteci türlerini belirten bir erişim maskesi belirtir. İstenen bu erişim türleri, hangi erişimlerin verildiğini veya reddedildiğini belirlemek için belirteci'nin DACL'si ile karşılaştırılır.

*bTaklite*<br/>
TRUE ise, bu çağrı başarıyla tamamlanırsa, geçerli iş parçacığı arama COM istemcisinin kimliğine bürünecektir. FALSE ise, erişim belirteci açılır, ancak bu çağrı tamamlandığında iş parçacığı bir kimliğe bürünme belirteci olmaz.

*bOpenAsSelf*<br/>
Erişim denetiminin [GetThreadToken](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) yöntemini çağıran iş parçacığının güvenlik bağlamına mı yoksa arama iş parçacığı için işlemin güvenlik bağlamına karşı mı yapılacağını gösterir.

Bu parametre FALSE ise, erişim denetimi arama iş parçacığı nın güvenlik bağlamı kullanılarak gerçekleştirilir. İş parçacığı istemci nin kimliğine bürünüyorsa, bu güvenlik bağlamı istemci işlemine ait olabilir. Bu parametre TRUE ise, erişim denetimi arama iş parçacığı için işlemin güvenlik bağlamı kullanılarak yapılır.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

[CAutoRevertImpersonation Class,](../../atl/reference/cautorevertimpersonation-class.md) *bImpersonate* bayrağını TRUE'ya ayarlayarak oluşturulan taklit edilmiş erişim belirteçlerini otomatik olarak geri almak için kullanılabilir.

## <a name="caccesstokenopennamedpipeclienttoken"></a><a name="opennamedpipeclienttoken"></a>CAccessToken::OpenNamedPipeClientToken

İstemciden erişim belirteci `CAccessToken` ile baş harflerini almak için adlandırılmış bir boru üzerinden istek alarak bir sunucu içinden bu yöntemi arayın.

```
bool OpenNamedPipeClientToken(
    HANDLE hPipe,
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```

### <a name="parameters"></a>Parametreler

*hPipe*<br/>
Adlandırılmış bir boruya sapla.

*dwDesiredAccess*<br/>
İstenilen erişim belirteci türlerini belirten bir erişim maskesi belirtir. İstenen bu erişim türleri, hangi erişimlerin verildiğini veya reddedildiğini belirlemek için belirteci'nin DACL'si ile karşılaştırılır.

*bTaklite*<br/>
TRUE ise, bu çağrı başarıyla tamamlanırsa, geçerli iş parçacığı arama boruistemcisi kimliğine bürünecektir. FALSE ise, erişim belirteci açılır, ancak bu çağrı tamamlandığında iş parçacığı bir kimliğe bürünme belirteci olmaz.

*bOpenAsSelf*<br/>
Erişim denetiminin [GetThreadToken](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) yöntemini çağıran iş parçacığının güvenlik bağlamına mı yoksa arama iş parçacığı için işlemin güvenlik bağlamına karşı mı yapılacağını gösterir.

Bu parametre FALSE ise, erişim denetimi arama iş parçacığı nın güvenlik bağlamı kullanılarak gerçekleştirilir. İş parçacığı istemci nin kimliğine bürünüyorsa, bu güvenlik bağlamı istemci işlemine ait olabilir. Bu parametre TRUE ise, erişim denetimi arama iş parçacığı için işlemin güvenlik bağlamı kullanılarak yapılır.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

[CAutoRevertImpersonation Class,](../../atl/reference/cautorevertimpersonation-class.md) *bImpersonate* bayrağını TRUE'ya ayarlayarak oluşturulan taklit edilmiş erişim belirteçlerini otomatik olarak geri almak için kullanılabilir.

## <a name="caccesstokenopenrpcclienttoken"></a><a name="openrpcclienttoken"></a>CAccessToken::OpenRPCClientToken

Bu yöntemi, istemciden erişim belirteci `CAccessToken` yle birlikte başlatılması için bir RPC istemcisinden gelen bir aramayı işleyen bir sunucunun içinden arayın.

```
bool OpenRPCClientToken(
    RPC_BINDING_HANDLE BindingHandle,
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```

### <a name="parameters"></a>Parametreler

*Bağlama Kolu*<br/>
İstemci için bir bağlama temsil eden sunucuda bağlama işteksi.

*dwDesiredAccess*<br/>
İstenilen erişim belirteci türlerini belirten bir erişim maskesi belirtir. İstenen bu erişim türleri, hangi erişimlerin verildiğini veya reddedildiğini belirlemek için belirteci'nin DACL'si ile karşılaştırılır.

*bTaklite*<br/>
TRUE ise, bu çağrı başarıyla tamamlanırsa, geçerli iş parçacığı çağıran RPC istemcisinin kimliğine bürünecektir. FALSE ise, erişim belirteci açılır, ancak bu çağrı tamamlandığında iş parçacığı bir kimliğe bürünme belirteci olmaz.

*bOpenAsSelf*<br/>
Erişim denetiminin [GetThreadToken](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) yöntemini çağıran iş parçacığının güvenlik bağlamına mı yoksa arama iş parçacığı için işlemin güvenlik bağlamına karşı mı yapılacağını gösterir.

Bu parametre FALSE ise, erişim denetimi arama iş parçacığı nın güvenlik bağlamı kullanılarak gerçekleştirilir. İş parçacığı istemci nin kimliğine bürünüyorsa, bu güvenlik bağlamı istemci işlemine ait olabilir. Bu parametre TRUE ise, erişim denetimi arama iş parçacığı için işlemin güvenlik bağlamı kullanılarak yapılır.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

[CAutoRevertImpersonation Class,](../../atl/reference/cautorevertimpersonation-class.md) *bImpersonate* bayrağını TRUE'ya ayarlayarak oluşturulan taklit edilmiş erişim belirteçlerini otomatik olarak geri almak için kullanılabilir.

## <a name="caccesstokenopenthreadtoken"></a><a name="openthreadtoken"></a>CAccessToken::OpenThreadToken

Kimliğe bürünme düzeyini ayarlamak için bu `CAccessToken` yöntemi çağırın ve ardından verilen iş parçacığından belirteçle birlikte başlatılmasını önadlandırın.

```
bool OpenThreadToken(
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true,
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) throw(...);
```

### <a name="parameters"></a>Parametreler

*dwDesiredAccess*<br/>
İstenilen erişim belirteci türlerini belirten bir erişim maskesi belirtir. İstenen bu erişim türleri, hangi erişimlerin verildiğini veya reddedildiğini belirlemek için belirteci'nin DACL'si ile karşılaştırılır.

*bTaklite*<br/>
TRUE ise, iş parçacığı bu yöntem tamamlandıktan sonra istenen kimliğe bürünme düzeyinde bırakılır. FALSE ise, iş parçacığı özgün kimliğe bürünme düzeyine geri döner.

*bOpenAsSelf*<br/>
Erişim denetiminin [GetThreadToken](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) yöntemini çağıran iş parçacığının güvenlik bağlamına mı yoksa arama iş parçacığı için işlemin güvenlik bağlamına karşı mı yapılacağını gösterir.

Bu parametre FALSE ise, erişim denetimi arama iş parçacığı nın güvenlik bağlamı kullanılarak gerçekleştirilir. İş parçacığı istemci nin kimliğine bürünüyorsa, bu güvenlik bağlamı istemci işlemine ait olabilir. Bu parametre TRUE ise, erişim denetimi arama iş parçacığı için işlemin güvenlik bağlamı kullanılarak yapılır.

*sil*<br/>
Belirteçteki kimliğe bürünme düzeyini sağlayan [numaralandırılmış SECURITY_IMPERSONATION_LEVEL](/windows/win32/api/winnt/ne-winnt-security_impersonation_level) bir tür belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

`OpenThreadToken`[CAccessToken benzer::GetThreadToken](#getthreadtoken), ancak iş parçacığının erişim belirteci `CAccessToken` nden başlatmadan önce kimliğe bürünme düzeyini ayarlar.

[CAutoRevertImpersonation Class,](../../atl/reference/cautorevertimpersonation-class.md) *bImpersonate* bayrağını TRUE'ya ayarlayarak oluşturulan taklit edilmiş erişim belirteçlerini otomatik olarak geri almak için kullanılabilir.

## <a name="caccesstokenprivilegecheck"></a><a name="privilegecheck"></a>CAccessToken::PrivilegeCheck

`CAccessToken` Nesnede belirli bir ayrıcalık kümesinin etkin olup olmadığını belirlemek için bu yöntemi çağırın.

```
bool PrivilegeCheck(
    PPRIVILEGE_SET RequiredPrivileges,
    bool* pbResult) const throw();
```

### <a name="parameters"></a>Parametreler

*Gerekli Ayrıcalıklar*<br/>
[PRIVILEGE_SET](/windows/win32/api/winnt/ns-winnt-privilege_set) bir yapıya işaretçi.

*pbSonuç*<br/>
Belirtilen ayrıcakın nesnede etkin olup olmadığını belirtmek için yöntemin `CAccessToken` ayarlığını belirleyen bir değer işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

İade `PrivilegeCheck` edildiğinde, `Attributes` her [LUID_AND_ATTRIBUTES](/windows/win32/api/winnt/ns-winnt-luid_and_attributes) yapının üyesi, ilgili ayrıcalık etkinleştirilirse SE_PRIVILEGE_USED_FOR_ACCESS olarak ayarlanır. Bu [yöntem, PrivilegeCheck](/windows/win32/api/securitybaseapi/nf-securitybaseapi-privilegecheck) Win32 işlevini çağırır.

## <a name="caccesstokenrevert"></a><a name="revert"></a>CAccessToken::Geri

Bir iş parçacığının kimliğe bürünme belirteci kullanmasını durdurmak için bu yöntemi çağırın.

```
bool Revert(HANDLE hThread = NULL) const throw();
```

### <a name="parameters"></a>Parametreler

*hThread*<br/>
Kimliğe bürünmeden geri dönmek için iş parçacığına işle. *hThread* NULL ise, geçerli iş parçacığı varsayılrılır.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

Kimliğe bürünme belirteçlerinin yeniden çevrilmesi [CAutoRevertImpersonation Class](../../atl/reference/cautorevertimpersonation-class.md)ile otomatik olarak gerçekleştirilebilir.

## <a name="caccesstokensetdefaultdacl"></a><a name="setdefaultdacl"></a>CAccessToken::SetDefaultDacl

`CAccessToken` Nesnenin varsayılan DACL ayarlamak için bu yöntemi arayın.

```
bool SetDefaultDacl(const CDacl& rDacl) throw(...);
```

### <a name="parameters"></a>Parametreler

*rDacl*<br/>
Yeni varsayılan [CDacl Sınıfı](../../atl/reference/cdacl-class.md) bilgileri.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

Varsayılan DACL, bu erişim belirteci etkin ken yeni nesneler oluşturulduğunda varsayılan olarak kullanılan DACL'dir.

## <a name="caccesstokensetowner"></a><a name="setowner"></a>CAccessToken::SetSahibi

Nesnenin sahibini ayarlamak için `CAccessToken` bu yöntemi çağırın.

```
bool SetOwner(const CSid& rSid) throw(...);
```

### <a name="parameters"></a>Parametreler

*rSid*<br/>
CSid [Sınıfı](../../atl/reference/csid-class.md) nesnesi sahibi bilgilerini içeren.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

Sahibi, bu erişim belirteci etkinken oluşturulan yeni nesneler için kullanılan varsayılan sahibidir.

## <a name="caccesstokensetprimarygroup"></a><a name="setprimarygroup"></a>CAccessToken::SetPrimaryGroup

Nesnenin birincil grubunu ayarlamak için `CAccessToken` bu yöntemi çağırın.

```
bool SetPrimaryGroup(const CSid& rSid) throw(...);
```

### <a name="parameters"></a>Parametreler

*rSid*<br/>
Birincil grup bilgilerini içeren [CSid Sınıfı](../../atl/reference/csid-class.md) nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

Birincil grup, bu erişim belirteci etkinken oluşturulan yeni nesneler için varsayılan gruptur.

## <a name="see-also"></a>Ayrıca bkz.

[ATLSecurity Örneği](../../overview/visual-cpp-samples.md)<br/>
[Erişim Belirteçleri](/windows/win32/SecAuthZ/access-tokens)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
