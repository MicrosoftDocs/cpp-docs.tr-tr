---
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
ms.openlocfilehash: 33fbaae5dafaccdf7f7e6880eaa42dd68352e840
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78864872"
---
# <a name="caccesstoken-class"></a>CAccessToken sınıfı

Bu sınıf, erişim belirtecinin sarmalayıcısıdır.

> [!IMPORTANT]
>  Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CAccessToken
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAccessToken:: ~ CAccessToken](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAccessToken:: Attach](#attach)|Verilen erişim belirteci tanıtıcısının sahipliğini almak için bu yöntemi çağırın.|
|[CAccessToken:: CheckTokenMembership](#checktokenmembership)|`CAccessToken` nesnesinde belirtilen bir SID 'nin etkinleştirilip etkinleştirilmediğini anlamak için bu yöntemi çağırın.|
|[CAccessToken:: Createımpersonationtoken](#createimpersonationtoken)|Yeni bir kimliğe bürünme erişim belirteci oluşturmak için bu yöntemi çağırın.|
|[CAccessToken:: CreatePrimaryToken](#createprimarytoken)|Yeni bir birincil belirteç oluşturmak için bu yöntemi çağırın.|
|[CAccessToken:: CreateProcessAsUser](#createprocessasuser)|`CAccessToken` nesnesi tarafından temsil edilen kullanıcının güvenlik bağlamında çalışan yeni bir işlem oluşturmak için bu yöntemi çağırın.|
|[CAccessToken:: CreateRestrictedToken](#createrestrictedtoken)|Yeni, kısıtlanmış bir `CAccessToken` nesnesi oluşturmak için bu yöntemi çağırın.|
|[CAccessToken::D etach](#detach)|Erişim belirtecinin sahipliğini iptal etmek için bu yöntemi çağırın.|
|[CAccessToken::D isablePrivilege](#disableprivilege)|`CAccessToken` nesnesindeki bir ayrıcalığı devre dışı bırakmak için bu yöntemi çağırın.|
|[CAccessToken::D isablePrivileges](#disableprivileges)|`CAccessToken` nesnesindeki bir veya daha fazla ayrıcalığı devre dışı bırakmak için bu yöntemi çağırın.|
|[CAccessToken:: EnablePrivilege](#enableprivilege)|`CAccessToken` nesnesindeki bir ayrıcalığı etkinleştirmek için bu yöntemi çağırın.|
|[CAccessToken:: EnablePrivileges](#enableprivileges)|`CAccessToken` nesnesinde bir veya daha fazla ayrıcalığı etkinleştirmek için bu yöntemi çağırın.|
|[CAccessToken:: GetDefaultDacl](#getdefaultdacl)|`CAccessToken` nesnenin varsayılan DACL 'sini döndürmek için bu yöntemi çağırın.|
|[CAccessToken:: GetEffectiveToken](#geteffectivetoken)|`CAccessToken` nesnesini geçerli iş parçacığı için geçerli olan erişim belirtecine eşit almak için bu yöntemi çağırın.|
|[CAccessToken:: GetGroups](#getgroups)|`CAccessToken` nesnesinin belirteç gruplarını döndürmek için bu yöntemi çağırın.|
|[CAccessToken:: GetHandle](#gethandle)|Erişim belirtecine bir tanıtıcı almak için bu yöntemi çağırın.|
|[CAccessToken:: GetImpersonationLevel](#getimpersonationlevel)|Erişim belirtecinden kimliğe bürünme düzeyini almak için bu yöntemi çağırın.|
|[CAccessToken:: Getlogonsessionıd](#getlogonsessionid)|`CAccessToken` nesnesiyle ilişkili oturum açma oturum KIMLIĞINI almak için bu yöntemi çağırın.|
|[CAccessToken:: GetLogonSid](#getlogonsid)|`CAccessToken` nesnesiyle ilişkili oturum açma SID 'sini almak için bu yöntemi çağırın.|
|[CAccessToken:: GetOwner](#getowner)|`CAccessToken` nesnesiyle ilişkili sahibi almak için bu yöntemi çağırın.|
|[CAccessToken:: GetPrimaryGroup](#getprimarygroup)|`CAccessToken` nesnesiyle ilişkili birincil grubu almak için bu yöntemi çağırın.|
|[CAccessToken:: GetPrivileges](#getprivileges)|`CAccessToken` nesnesiyle ilişkili ayrıcalıkları almak için bu yöntemi çağırın.|
|[CAccessToken:: GetProcessToken](#getprocesstoken)|Verilen işlemden erişim belirteciyle `CAccessToken` başlatmak için bu yöntemi çağırın.|
|[CAccessToken:: GetProfile](#getprofile)|`CAccessToken` nesnesiyle ilişkili kullanıcı profilini işaret eden tanıtıcıyı almak için bu yöntemi çağırın.|
|[CAccessToken:: GetSource](#getsource)|`CAccessToken` nesnesinin kaynağını almak için bu yöntemi çağırın.|
|[CAccessToken:: GetStatistics](#getstatistics)|`CAccessToken` nesnesiyle ilişkili bilgileri almak için bu yöntemi çağırın.|
|[CAccessToken:: Getterminalservicessessionıd](#getterminalservicessessionid)|`CAccessToken` nesnesiyle ilişkili Terminal Hizmetleri oturum KIMLIĞINI almak için bu yöntemi çağırın.|
|[CAccessToken:: GetThreadToken](#getthreadtoken)|`CAccessToken` verilen iş parçacığından belirteç ile başlatmak için bu yöntemi çağırın.|
|[CAccessToken:: Gettokenıd](#gettokenid)|`CAccessToken` nesnesiyle ilişkili belirteç KIMLIĞINI almak için bu yöntemi çağırın.|
|[CAccessToken:: GetType](#gettype)|`CAccessToken` nesnesinin belirteç türünü almak için bu yöntemi çağırın.|
|[CAccessToken:: GetUser](#getuser)|`CAccessToken` nesnesiyle ilişkili kullanıcıyı tanımlamak için bu yöntemi çağırın.|
|[CAccessToken:: HKeyCurrentUser](#hkeycurrentuser)|`CAccessToken` nesnesiyle ilişkili kullanıcı profilini işaret eden tanıtıcıyı almak için bu yöntemi çağırın.|
|[CAccessToken:: Impersonate](#impersonate)|Bir iş parçacığına kimliğe bürünme `CAccessToken` atamak için bu yöntemi çağırın.|
|[CAccessToken:: ImpersonateLoggedOnUser](#impersonateloggedonuser)|Çağıran iş parçacığının, oturum açmış bir kullanıcının güvenlik bağlamını taklit etmesine izin vermek için bu yöntemi çağırın.|
|[CAccessToken:: ıstokenrestricted](#istokenrestricted)|`CAccessToken` nesnesi kısıtlı SID 'lerin listesini içerip içermiyorsa test etmek için bu yöntemi çağırın.|
|[CAccessToken:: LoadUserProfile](#loaduserprofile)|`CAccessToken` nesnesiyle ilişkili kullanıcı profilini yüklemek için bu yöntemi çağırın.|
|[CAccessToken:: LogonUser](#logonuser)|Verilen kimlik bilgileriyle ilişkili kullanıcı için bir oturum açma oturumu oluşturmak için bu yöntemi çağırın.|
|[CAccessToken:: OpenCOMClientToken](#opencomclienttoken)|Bu yöntemi, com istemcisinden bir istemciden gelen çağrıyı işleyen bir COM sunucusu içinden arayarak `CAccessToken`.|
|[CAccessToken:: OpenNamedPipeClientToken](#opennamedpipeclienttoken)|İstemciden erişim belirteciyle `CAccessToken` başlatmak için adlandırılmış bir kanal üzerinden istek alan bir sunucu içinden bu yöntemi çağırın.|
|[CAccessToken:: OpenRPCClientToken](#openrpcclienttoken)|İstemciden erişim belirteciyle `CAccessToken` başlatmak için RPC istemcisinden çağrıyı işleyen bir sunucu içinden bu yöntemi çağırın.|
|[CAccessToken:: OpenThreadToken](#openthreadtoken)|Kimliğe bürünme düzeyini ayarlamak için bu yöntemi çağırın ve ardından `CAccessToken` verilen iş parçacığından belirteç ile başlatın.|
|[CAccessToken::P rivilegeCheck](#privilegecheck)|`CAccessToken` nesnesinde belirtilen ayrıcalık kümesinin etkinleştirilip etkinleştirilmeyeceğini öğrenmek için bu yöntemi çağırın.|
|[CAccessToken:: çevir](#revert)|Kimliğe bürünme belirtecini kullanan bir iş parçacığını durdurmak için bu yöntemi çağırın.|
|[CAccessToken:: SetDefaultDacl](#setdefaultdacl)|`CAccessToken` nesnesinin varsayılan DACL 'sini ayarlamak için bu yöntemi çağırın.|
|[CAccessToken:: SetOwner](#setowner)|`CAccessToken` nesnesinin sahibini ayarlamak için bu yöntemi çağırın.|
|[CAccessToken:: SetPrimaryGroup](#setprimarygroup)|`CAccessToken` nesnesinin birincil grubunu ayarlamak için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

[Erişim belirteci](/windows/win32/SecAuthZ/access-tokens) bir işlemin veya iş parçacığının güvenlik bağlamını açıklayan ve bir Windows sisteminde oturum açan her kullanıcıya ayrılan bir nesnedir.

Windows 'daki erişim denetim modeline giriş için Windows SDK [Access Control](/windows/win32/SecAuthZ/access-control) bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity. h

##  <a name="attach"></a>CAccessToken:: Attach

Verilen erişim belirteci tanıtıcısının sahipliğini almak için bu yöntemi çağırın.

```
void Attach(HANDLE hToken) throw();
```

### <a name="parameters"></a>Parametreler

*hToken*<br/>
Erişim belirtecine yönelik bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, `CAccessToken` nesnenin zaten bir erişim belirtecinin sahipliği varsa bir onaylama hatası oluşur.

##  <a name="dtor"></a>CAccessToken:: ~ CAccessToken

Yok edicisi.

```
virtual ~CAccessToken() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakır.

##  <a name="checktokenmembership"></a>CAccessToken:: CheckTokenMembership

`CAccessToken` nesnesinde belirtilen bir SID 'nin etkinleştirilip etkinleştirilmediğini anlamak için bu yöntemi çağırın.

```
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

`CheckTokenMembership` yöntemi, erişim belirtecinin Kullanıcı ve Grup SID 'Lerine ait SID varlığını denetler. SID varsa ve SE_GROUP_ENABLED özniteliğine sahipse, *Pbismember* değeri true olarak ayarlanır; Aksi takdirde, FALSE olarak ayarlanır.

Hata ayıklama yapılarında, *Pbismember* geçerli bir işaretçi değilse bir onaylama hatası oluşur.

> [!NOTE]
>  `CAccessToken` nesnesi, birincil belirteç değil, kimliğe bürünme belirteci olmalıdır.

##  <a name="createimpersonationtoken"></a>CAccessToken:: Createımpersonationtoken

Kimliğe bürünme erişim belirteci oluşturmak için bu yöntemi çağırın.

```
bool CreateImpersonationToken(
    CAccessToken* pImp,
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pImp*<br/>
Yeni `CAccessToken` nesnesine yönelik işaretçi.

*Sil*<br/>
Yeni belirtecin kimliğe bürünme düzeyini sağlayan [SECURITY_IMPERSONATION_LEVEL](/windows/win32/api/winnt/ne-winnt-security_impersonation_level) numaralandırılmış bir tür belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

`CreateImpersonationToken`, yeni bir kimliğe bürünme belirteci oluşturmak için [DuplicateToken](/windows/win32/api/securitybaseapi/nf-securitybaseapi-duplicatetoken) çağırır.

##  <a name="createprimarytoken"></a>CAccessToken:: CreatePrimaryToken

Yeni bir birincil belirteç oluşturmak için bu yöntemi çağırın.

```
bool CreatePrimaryToken(
    CAccessToken* pPri,
    DWORD dwDesiredAccess = MAXIMUM_ALLOWED,
    const CSecurityAttributes* pTokenAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Parametreler

*Pprı*<br/>
Yeni `CAccessToken` nesnesine yönelik işaretçi.

*dwDesiredAccess*<br/>
Yeni belirteç için istenen erişim haklarını belirtir. Varsayılan, MAXIMUM_ALLOWED, çağıran için geçerli olan tüm erişim haklarını ister. Erişim hakları hakkında daha fazla bilgi için bkz. [erişim hakları ve erişim maskeleri](/windows/win32/SecAuthZ/access-rights-and-access-masks) .

*pTokenAttributes*<br/>
Yeni belirteç için bir güvenlik tanımlayıcısı belirten [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) yapısına yönelik işaretçi ve alt işlemlerin belirteci devralmasını belirler. *PTokenAttributes* null ise, belirteç varsayılan bir güvenlik tanımlayıcısı alır ve tanıtıcı devralınamaz.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

`CreatePrimaryToken`, yeni bir birincil belirteç oluşturmak için [DuplicateTokenEx](/windows/win32/api/securitybaseapi/nf-securitybaseapi-duplicatetokenex) çağırır.

##  <a name="createprocessasuser"></a>CAccessToken:: CreateProcessAsUser

`CAccessToken` nesnesi tarafından temsil edilen kullanıcının güvenlik bağlamında çalışan yeni bir işlem oluşturmak için bu yöntemi çağırın.

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

`CreateProcessAsUser`, `CAccessToken` nesnesi tarafından temsil edilen kullanıcının güvenlik bağlamında çalışan yeni bir işlem oluşturmak için `CreateProcessAsUser` Win32 işlevini kullanır. Gerekli parametrelerin tam bir tartışması için [CreateProcessAsUser](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessasuserw) işlevinin açıklamasına bakın.

Bu yöntemin başarılı olması için, `CAccessToken` nesnesi, Atamaprimarytoken 'ı (kısıtlı bir belirteç olmadığı müddetçe) ve IncreaseQuota ayrıcalıklarını tutmalıdır.

##  <a name="createrestrictedtoken"></a>CAccessToken:: CreateRestrictedToken

Yeni, kısıtlanmış bir `CAccessToken` nesnesi oluşturmak için bu yöntemi çağırın.

```
bool CreateRestrictedToken(
    CAccessToken* pRestrictedToken,
    const CTokenGroups& SidsToDisable,
    const CTokenGroups& SidsToRestrict,
    const CTokenPrivileges& PrivilegesToDelete = CTokenPrivileges()) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pRestrictedToken*<br/>
Yeni, kısıtlanmış `CAccessToken` nesnesi.

*Sıdstodisable*<br/>
Yalnızca reddetme SID 'Lerini belirten `CTokenGroups` nesnesi.

*Sıdstorestrict*<br/>
Kısıtlama SID 'Lerini belirten `CTokenGroups` nesnesi.

*PrivilegesToDelete*<br/>
Kısıtlanmış belirteçte silinecek ayrıcalıkları belirten `CTokenPrivileges` nesnesi. Varsayılan değer boş bir nesne oluşturur.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

`CreateRestrictedToken`, kısıtlamalarla yeni bir `CAccessToken` nesnesi oluşturmak için [CreateRestrictedToken](/windows/win32/api/securitybaseapi/nf-securitybaseapi-createrestrictedtoken) Win32 işlevini kullanır.

> [!IMPORTANT]
>  `CreateRestrictedToken`kullanırken, aşağıdakilerden emin olun: mevcut belirteç geçerli (ve Kullanıcı tarafından girilmemiş) ve *Sıdstodisable* ve *PrivilegesToDelete* öğelerinin ikisi de geçerli (ve Kullanıcı tarafından girilmemiş). Yöntem FALSE döndürürse, reddetme işlevselliği.

##  <a name="detach"></a>CAccessToken::D etach

Erişim belirtecinin sahipliğini iptal etmek için bu yöntemi çağırın.

```
HANDLE Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılan `CAccessToken` tanıtıcısını döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `CAccessToken`erişim belirtecinin sahipliğini iptal eder.

##  <a name="disableprivilege"></a>CAccessToken::D isablePrivilege

`CAccessToken` nesnesindeki bir ayrıcalığı devre dışı bırakmak için bu yöntemi çağırın.

```
bool DisablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>Parametreler

*pszPrivilege*<br/>
`CAccessToken` nesnesinde devre dışı bırakma ayrıcalığını içeren bir dize işaretçisi.

*pPreviousState*<br/>
Ayrıcalıkların önceki durumunu içeren `CTokenPrivileges` nesnesine yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

##  <a name="disableprivileges"></a>CAccessToken::D isablePrivileges

`CAccessToken` nesnesindeki bir veya daha fazla ayrıcalığı devre dışı bırakmak için bu yöntemi çağırın.

```
bool DisablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>Parametreler

*rPrivileges*<br/>
`CAccessToken` nesnesinde devre dışı bırakmak için ayrıcalıkları içeren dizeler dizisine yönelik işaretçi.

*pPreviousState*<br/>
Ayrıcalıkların önceki durumunu içeren `CTokenPrivileges` nesnesine yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

##  <a name="enableprivilege"></a>CAccessToken:: EnablePrivilege

`CAccessToken` nesnesindeki bir ayrıcalığı etkinleştirmek için bu yöntemi çağırın.

```
bool EnablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>Parametreler

*pszPrivilege*<br/>
`CAccessToken` nesnesinde etkinleştirilecek ayrıcalığı içeren bir dizeye yönelik işaretçi.

*pPreviousState*<br/>
Ayrıcalıkların önceki durumunu içeren `CTokenPrivileges` nesnesine yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

##  <a name="enableprivileges"></a>CAccessToken:: EnablePrivileges

`CAccessToken` nesnesinde bir veya daha fazla ayrıcalığı etkinleştirmek için bu yöntemi çağırın.

```
bool EnablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>Parametreler

*rPrivileges*<br/>
`CAccessToken` nesnesinde etkinleştirilecek ayrıcalıkları içeren dizeler dizisine yönelik işaretçi.

*pPreviousState*<br/>
Ayrıcalıkların önceki durumunu içeren `CTokenPrivileges` nesnesine yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

##  <a name="getdefaultdacl"></a>CAccessToken:: GetDefaultDacl

`CAccessToken` nesnenin varsayılan DACL 'sini döndürmek için bu yöntemi çağırın.

```
bool GetDefaultDacl(CDacl* pDacl) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pDacl*<br/>
`CAccessToken` nesnenin varsayılan DACL 'sini alacak olan [CDacl sınıf](../../atl/reference/cdacl-class.md) nesnesi işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Varsayılan DACL kurtarılırsa TRUE, aksi takdirde FALSE döndürür.

##  <a name="geteffectivetoken"></a>CAccessToken:: GetEffectiveToken

`CAccessToken` nesnesini geçerli iş parçacığı için geçerli olan erişim belirtecine eşit almak için bu yöntemi çağırın.

```
bool GetEffectiveToken(DWORD dwDesiredAccess) throw();
```

### <a name="parameters"></a>Parametreler

*dwDesiredAccess*<br/>
Erişim belirtecine istenen erişim türlerini belirten bir erişim maskesini belirtir. Bu istenen erişim türleri, hangi erişimlerin verildiğini veya reddedildiğini belirleyen belirtecin DACL 'si ile karşılaştırılır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

##  <a name="getgroups"></a>CAccessToken:: GetGroups

`CAccessToken` nesnesinin belirteç gruplarını döndürmek için bu yöntemi çağırın.

```
bool GetGroups(CTokenGroups* pGroups) const throw(...);
```

### <a name="parameters"></a>Parametreler

*Pgruplar*<br/>
Grup bilgilerini alacak [CTokenGroups sınıf](../../atl/reference/ctokengroups-class.md) nesnesine yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

##  <a name="gethandle"></a>CAccessToken:: GetHandle

Erişim belirtecine bir tanıtıcı almak için bu yöntemi çağırın.

```
HANDLE GetHandle() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CAccessToken` nesnenin erişim belirtecine bir tanıtıcı döndürür.

##  <a name="getimpersonationlevel"></a>CAccessToken:: GetImpersonationLevel

Erişim belirtecinden kimliğe bürünme düzeyini almak için bu yöntemi çağırın.

```
bool GetImpersonationLevel(
    SECURITY_IMPERSONATION_LEVEL* pImpersonationLevel) const throw(...);
```

### <a name="parameters"></a>Parametreler

*Pımpersonationlevel*<br/>
Kimliğe bürünme düzeyi bilgilerini alacak [SECURITY_IMPERSONATION_LEVEL](/windows/win32/api/winnt/ne-winnt-security_impersonation_level) numaralandırma türüne yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

##  <a name="getlogonsessionid"></a>CAccessToken:: Getlogonsessionıd

`CAccessToken` nesnesiyle ilişkili oturum açma oturum KIMLIĞINI almak için bu yöntemi çağırın.

```
bool GetLogonSessionId(LUID* pluid) const throw(...);
```

### <a name="parameters"></a>Parametreler

*plualıd*<br/>
Oturum açma oturum KIMLIĞINI alacak bir [LUID](/windows/win32/api/winnt/ns-winnt-luid) işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, *pluıd* geçersiz bir değer olduğunda bir onaylama hatası oluşur.

##  <a name="getlogonsid"></a>CAccessToken:: GetLogonSid

`CAccessToken` nesnesiyle ilişkili oturum açma SID 'sini almak için bu yöntemi çağırın.

```
bool GetLogonSid(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>Parametreler

*PSID*<br/>
[CSID sınıfı](../../atl/reference/csid-class.md) nesnesine yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama Derlemeleriyle, *PSID* geçersiz bir değer ise bir onaylama hatası meydana gelir.

##  <a name="getowner"></a>CAccessToken:: GetOwner

`CAccessToken` nesnesiyle ilişkili sahibi almak için bu yöntemi çağırın.

```
bool GetOwner(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>Parametreler

*PSID*<br/>
[CSID sınıfı](../../atl/reference/csid-class.md) nesnesine yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Sahip, bu erişim belirteci etkin durumdayken oluşturulan tüm nesnelerde varsayılan olarak ayarlanır.

##  <a name="getprimarygroup"></a>CAccessToken:: GetPrimaryGroup

`CAccessToken` nesnesiyle ilişkili birincil grubu almak için bu yöntemi çağırın.

```
bool GetPrimaryGroup(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>Parametreler

*PSID*<br/>
[CSID sınıfı](../../atl/reference/csid-class.md) nesnesine yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu erişim belirteci etkin durumdayken oluşturulan tüm nesnelerde grup varsayılan olarak ayarlanır.

##  <a name="getprivileges"></a>CAccessToken:: GetPrivileges

`CAccessToken` nesnesiyle ilişkili ayrıcalıkları almak için bu yöntemi çağırın.

```
bool GetPrivileges(CTokenPrivileges* pPrivileges) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pPrivileges*<br/>
Ayrıcalıkları alacak bir [CTokenPrivileges sınıfı](../../atl/reference/ctokenprivileges-class.md) nesnesine yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

##  <a name="getprocesstoken"></a>CAccessToken:: GetProcessToken

Verilen işlemden erişim belirteciyle `CAccessToken` başlatmak için bu yöntemi çağırın.

```
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

##  <a name="getprofile"></a>CAccessToken:: GetProfile

`CAccessToken` nesnesiyle ilişkili kullanıcı profilini işaret eden tanıtıcıyı almak için bu yöntemi çağırın.

```
HANDLE GetProfile() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı profiline işaret eden bir tanıtıcı döndürür veya profil yoksa NULL değeri döndürür.

##  <a name="getsource"></a>CAccessToken:: GetSource

`CAccessToken` nesnesinin kaynağını almak için bu yöntemi çağırın.

```
bool GetSource(TOKEN_SOURCE* pSource) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pSource*<br/>
[TOKEN_SOURCE](/windows/win32/api/winnt/ns-winnt-token_source) yapısına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

##  <a name="getstatistics"></a>CAccessToken:: GetStatistics

`CAccessToken` nesnesiyle ilişkili bilgileri almak için bu yöntemi çağırın.

```
bool GetStatistics(TOKEN_STATISTICS* pStatistics) const throw(...);
```

### <a name="parameters"></a>Parametreler

*Pstatıstıcs*<br/>
[TOKEN_STATISTICS](/windows/win32/api/winnt/ns-winnt-token_statistics) yapısına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

##  <a name="getterminalservicessessionid"></a>CAccessToken:: Getterminalservicessessionıd

`CAccessToken` nesnesiyle ilişkili Terminal Hizmetleri oturum KIMLIĞINI almak için bu yöntemi çağırın.

```
bool GetTerminalServicesSessionId(DWORD* pdwSessionId) const throw(...);
```

### <a name="parameters"></a>Parametreler

*Pdwsessionıd*<br/>
Terminal Hizmetleri oturum KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

##  <a name="getthreadtoken"></a>CAccessToken:: GetThreadToken

`CAccessToken` verilen iş parçacığından belirteç ile başlatmak için bu yöntemi çağırın.

```
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
`GetThreadToken` yöntemini çağıran iş parçacığının güvenlik bağlamına veya çağıran iş parçacığı için işlemin güvenlik bağlamına karşı erişim denetiminin yapılıp yapılmayacağını belirtir.

Bu parametre FALSE ise, erişim denetimi çağıran iş parçacığının güvenlik bağlamı kullanılarak gerçekleştirilir. İş parçacığı bir istemciyi taklit alıyorsa, bu güvenlik bağlamı bir istemci işlemi olabilir. Bu parametre TRUE ise, erişim denetimi çağıran iş parçacığı için işlemin güvenlik bağlamı kullanılarak yapılır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

##  <a name="gettokenid"></a>CAccessToken:: Gettokenıd

`CAccessToken` nesnesiyle ilişkili belirteç KIMLIĞINI almak için bu yöntemi çağırın.

```
bool GetTokenId(LUID* pluid) const throw(...);
```

### <a name="parameters"></a>Parametreler

*plualıd*<br/>
Belirteç KIMLIĞINI alacak bir [LUID](/windows/win32/api/winnt/ns-winnt-luid) işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

##  <a name="gettype"></a>CAccessToken:: GetType

`CAccessToken` nesnesinin belirteç türünü almak için bu yöntemi çağırın.

```
bool GetType(TOKEN_TYPE* pType) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pType*<br/>
Başarı durumunda belirtecin türünü alan [TOKEN_TYPE](/windows/win32/api/winnt/ne-winnt-token_type) değişkeninin adresi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

TOKEN_TYPE numaralandırma türü, bir birincil belirteç ve bir kimliğe bürünme belirteci ayırt eden değerleri içerir.

##  <a name="getuser"></a>CAccessToken:: GetUser

`CAccessToken` nesnesiyle ilişkili kullanıcıyı tanımlamak için bu yöntemi çağırın.

```
bool GetUser(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>Parametreler

*PSID*<br/>
[CSID sınıfı](../../atl/reference/csid-class.md) nesnesine yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

##  <a name="hkeycurrentuser"></a>CAccessToken:: HKeyCurrentUser

`CAccessToken` nesnesiyle ilişkili kullanıcı profilini işaret eden tanıtıcıyı almak için bu yöntemi çağırın.

```
HKEY HKeyCurrentUser() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı profiline işaret eden bir tanıtıcı döndürür veya profil yoksa NULL değeri döndürür.

##  <a name="impersonate"></a>CAccessToken:: Impersonate

Bir iş parçacığına kimliğe bürünme `CAccessToken` atamak için bu yöntemi çağırın.

```
bool Impersonate(HANDLE hThread = NULL) const throw(...);
```

### <a name="parameters"></a>Parametreler

*hThread*<br/>
Kimliğe bürünme belirtecini atamak için iş parçacığına olan tanıtıcı. Bu tanıtıcının TOKEN_IMPERSONATE erişim haklarıyla açılmış olması gerekir. *HThread* null ise, yöntemi, iş parçacığının kimliğe bürünme belirtecini kullanmayı durdurmasına neden olur.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, `CAccessToken` belirteç için geçerli bir işaretçiye sahip değilse bir onaylama hatası meydana gelir.

[CAutoRevertImpersonation sınıfı](../../atl/reference/cautorevertimpersonation-class.md) , kimliğe bürünme erişim belirteçlerini otomatik olarak dönüştürmek için kullanılabilir.

##  <a name="impersonateloggedonuser"></a>CAccessToken:: ImpersonateLoggedOnUser

Çağıran iş parçacığının, oturum açmış bir kullanıcının güvenlik bağlamını taklit etmesine izin vermek için bu yöntemi çağırın.

```
bool ImpersonateLoggedOnUser() const throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

> [!IMPORTANT]
>  Kimliğe bürünme işlevine yapılan bir çağrı herhangi bir nedenle başarısız olursa, istemci kimliğine bürünülemez ve istemci isteği Çağrının yapıldığı işlemin güvenlik bağlamında yapılır. İşlem yüksek ayrıcalıklı bir hesap olarak çalışıyorsa veya bir yönetim grubunun üyesi olarak, Kullanıcı Aksi takdirde izin verilmeyen eylemler gerçekleştirebilir. Bu nedenle, bu işlevin dönüş değeri her zaman onaylanır.

##  <a name="istokenrestricted"></a>CAccessToken:: ıstokenrestricted

`CAccessToken` nesnesi kısıtlı SID 'lerin listesini içerip içermiyorsa test etmek için bu yöntemi çağırın.

```
bool IsTokenRestricted() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne bir kısıtlama SID listesi içeriyorsa TRUE, hiçbir SID kısıtlaması yoksa veya yöntem başarısız olursa FALSE döndürür.

##  <a name="loaduserprofile"></a>CAccessToken:: LoadUserProfile

`CAccessToken` nesnesiyle ilişkili kullanıcı profilini yüklemek için bu yöntemi çağırın.

```
bool LoadUserProfile() throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, `CAccessToken` geçerli bir belirteç içermiyorsa veya bir kullanıcı profili zaten varsa bir onaylama hatası oluşur.

##  <a name="logonuser"></a>CAccessToken:: LogonUser

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
Kullanıcı adını belirten, null ile sonlandırılmış bir dize işaretçisi. Bu, oturum açmak için Kullanıcı hesabının adıdır.

*pszDomain*<br/>
Hesap veritabanı *pszUserName* hesabını içeren etki alanı veya sunucu adını belirten null ile sonlandırılmış bir dize işaretçisi.

*pszPassword*<br/>
*PszUserName*tarafından belirtilen kullanıcı hesabının şifresiz metin parolasını belirten null ile sonlandırılmış bir dize işaretçisi.

*dwLogonType*<br/>
Gerçekleştirilecek oturum açma işlemi türünü belirtir. Daha fazla ayrıntı için bkz. [LogonUser](/windows/win32/api/winbase/nf-winbase-logonuserw) .

*dwLogonProvider*<br/>
Oturum açma sağlayıcısını belirtir. Daha fazla ayrıntı için bkz. [LogonUser](/windows/win32/api/winbase/nf-winbase-logonuserw) .

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Oturum açma işleminden kaynaklanan erişim belirteci `CAccessToken`ilişkilendirilir. Bu yöntemin başarılı olması için `CAccessToken` nesnesi, güvenilir bilgisayar tabanının bir parçası olarak sahibini tanımlayarak SE_TCB_NAME ayrıcalıklarını tutmalıdır. Gerekli ayrıcalıklar hakkında daha fazla bilgi için bkz. [LogonUser](/windows/win32/api/winbase/nf-winbase-logonuserw) .

##  <a name="opencomclienttoken"></a>CAccessToken:: OpenCOMClientToken

Bu yöntemi, com istemcisinden bir istemciden gelen çağrıyı işleyen bir COM sunucusu içinden arayarak `CAccessToken`.

```
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

##  <a name="opennamedpipeclienttoken"></a>CAccessToken:: OpenNamedPipeClientToken

İstemciden erişim belirteciyle `CAccessToken` başlatmak için adlandırılmış bir kanal üzerinden istek alan bir sunucu içinden bu yöntemi çağırın.

```
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

##  <a name="openrpcclienttoken"></a>CAccessToken:: OpenRPCClientToken

İstemciden erişim belirteciyle `CAccessToken` başlatmak için RPC istemcisinden çağrıyı işleyen bir sunucu içinden bu yöntemi çağırın.

```
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

##  <a name="openthreadtoken"></a>CAccessToken:: OpenThreadToken

Kimliğe bürünme düzeyini ayarlamak için bu yöntemi çağırın ve ardından `CAccessToken` verilen iş parçacığından belirteç ile başlatın.

```
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

`OpenThreadToken`, [CAccessToken:: GetThreadToken](#getthreadtoken)öğesine benzerdir, ancak iş parçacığının erişim belirtecinden `CAccessToken` başlatmadan önce kimliğe bürünme düzeyini ayarlar.

[CAutoRevertImpersonation sınıfı](../../atl/reference/cautorevertimpersonation-class.md) , *BIMPERSONATE* bayrağı true olarak ayarlanarak oluşturulan kimliğe bürünme erişim belirteçlerini otomatik olarak geri almak için kullanılabilir.

##  <a name="privilegecheck"></a>CAccessToken::P rivilegeCheck

`CAccessToken` nesnesinde belirtilen ayrıcalık kümesinin etkinleştirilip etkinleştirilmeyeceğini öğrenmek için bu yöntemi çağırın.

```
bool PrivilegeCheck(
    PPRIVILEGE_SET RequiredPrivileges,
    bool* pbResult) const throw();
```

### <a name="parameters"></a>Parametreler

*RequiredPrivileges*<br/>
[PRIVILEGE_SET](/windows/win32/api/winnt/ns-winnt-privilege_set) yapısına yönelik işaretçi.

*pbResult*<br/>
Yöntemi, belirtilen ayrıcalığın herhangi birinin veya tümünün `CAccessToken` nesnesinde etkin olup olmadığını belirtmek için bir değere işaretçi olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

`PrivilegeCheck` döndürüldüğünde, ilgili ayrıcalık etkinse her [LUID_AND_ATTRIBUTES](/windows/win32/api/winnt/ns-winnt-luid_and_attributes) yapısının `Attributes` üyesi SE_PRIVILEGE_USED_FOR_ACCESS olarak ayarlanır. Bu yöntem, [PrivilegeCheck](/windows/win32/api/securitybaseapi/nf-securitybaseapi-privilegecheck) Win32 işlevini çağırır.

##  <a name="revert"></a>CAccessToken:: çevir

Bir iş parçacığını kimliğe bürünme belirtecini kullanarak durdurmak için bu yöntemi çağırın.

```
bool Revert(HANDLE hThread = NULL) const throw();
```

### <a name="parameters"></a>Parametreler

*hThread*<br/>
Kimliğe bürünme işleminden dönmek için iş parçacığına işleyin. *HThread* null ise, geçerli iş parçacığı kabul edilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Kimliğe bürünme belirteçlerinin yeniden sürümü [CAutoRevertImpersonation sınıfıyla](../../atl/reference/cautorevertimpersonation-class.md)otomatik olarak gerçekleştirilebilir.

##  <a name="setdefaultdacl"></a>CAccessToken:: SetDefaultDacl

`CAccessToken` nesnesinin varsayılan DACL 'sini ayarlamak için bu yöntemi çağırın.

```
bool SetDefaultDacl(const CDacl& rDacl) throw(...);
```

### <a name="parameters"></a>Parametreler

*rDacl*<br/>
Yeni varsayılan [CDacl sınıfı](../../atl/reference/cdacl-class.md) bilgileri.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Varsayılan DACL, bu erişim belirteci etkin olarak yeni nesneler oluşturulduğunda varsayılan olarak kullanılan DACL 'dir.

##  <a name="setowner"></a>CAccessToken:: SetOwner

`CAccessToken` nesnesinin sahibini ayarlamak için bu yöntemi çağırın.

```
bool SetOwner(const CSid& rSid) throw(...);
```

### <a name="parameters"></a>Parametreler

*Rsıd*<br/>
Sahip bilgilerini içeren [CSID sınıfı](../../atl/reference/csid-class.md) nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu erişim belirteci etkin durumdayken oluşturulan yeni nesneler için kullanılan varsayılan sahibdir.

##  <a name="setprimarygroup"></a>CAccessToken:: SetPrimaryGroup

`CAccessToken` nesnesinin birincil grubunu ayarlamak için bu yöntemi çağırın.

```
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
