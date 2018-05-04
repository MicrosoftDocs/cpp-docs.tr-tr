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
ms.openlocfilehash: 407652cc5a5e300a2e5eb9d6a5a07dd29209ffef
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="caccesstoken-class"></a>CAccessToken sınıfı
Bir erişim belirteci için bir sarmalayıcı sınıftır.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CAccessToken
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAccessToken:: ~ CAccessToken](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAccessToken::Attach](#attach)|Verilen erişim belirteci işleyici sahipliğini almak için bu yöntemi çağırın.|  
|[CAccessToken::CheckTokenMembership](#checktokenmembership)|Belirtilen SID, etkin olup olmadığını belirlemek için bu yöntemi çağırın `CAccessToken` nesnesi.|  
|[CAccessToken::CreateImpersonationToken](#createimpersonationtoken)|Yeni bir kimliğe bürünme erişim belirteci oluşturmak için bu yöntemi çağırın.|  
|[CAccessToken::CreatePrimaryToken](#createprimarytoken)|Yeni birincil belirteç oluşturmak için bu yöntemi çağırın.|  
|[CAccessToken::CreateProcessAsUser](#createprocessasuser)|Tarafından temsil edilen kullanıcının güvenlik bağlamında çalışan yeni bir işlem oluşturmak için bu yöntemi çağırın `CAccessToken` nesnesi.|  
|[CAccessToken::CreateRestrictedToken](#createrestrictedtoken)|Yeni, oluşturmak için bu yöntemi çağırın kısıtlı `CAccessToken` nesnesi.|  
|[CAccessToken::Detach](#detach)|Erişim belirteci sahipliğini iptal etmek için bu yöntemi çağırın.|  
|[CAccessToken::DisablePrivilege](#disableprivilege)|Bir ayrıcalık devre dışı bırakmak için bu yöntemi çağırabilmeniz `CAccessToken` nesnesi.|  
|[CAccessToken::DisablePrivileges](#disableprivileges)|Bir veya daha fazla ayrıcalık devre dışı bırakmak için bu yöntemi çağırabilmeniz `CAccessToken` nesnesi.|  
|[CAccessToken::EnablePrivilege](#enableprivilege)|Bir ayrıcalık etkinleştirmek için bu yöntemi çağırın `CAccessToken` nesnesi.|  
|[CAccessToken::EnablePrivileges](#enableprivileges)|Bir veya daha fazla ayrıcalık etkinleştirmek için bu yöntemi çağırın `CAccessToken` nesnesi.|  
|[CAccessToken::GetDefaultDacl](#getdefaultdacl)|Döndürmek için bu yöntemi çağırabilmeniz `CAccessToken` nesnenin varsayılan DACL.|  
|[CAccessToken::GetEffectiveToken](#geteffectivetoken)|Almak için bu yöntemi çağırın `CAccessToken` nesne geçerli iş parçacığının etkin için erişim belirtecini eşittir.|  
|[CAccessToken::GetGroups](#getgroups)|Döndürmek için bu yöntemi çağırabilmeniz `CAccessToken` nesnenin belirteç grupları.|  
|[CAccessToken::GetHandle](#gethandle)|Erişim belirteci işleyici almak için bu yöntemi çağırın.|  
|[CAccessToken::GetImpersonationLevel](#getimpersonationlevel)|Kimliğe bürünme düzeyi erişim belirtecinden almak için bu yöntemi çağırın.|  
|[CAccessToken::GetLogonSessionId](#getlogonsessionid)|İlişkili oturum açma oturum kimliği almak için bu yöntemi çağırın `CAccessToken` nesnesi.|  
|[CAccessToken::GetLogonSid](#getlogonsid)|İlişkili oturum açma SID almak için bu yöntemi çağırın `CAccessToken` nesnesi.|  
|[CAccessToken::GetOwner](#getowner)|İle ilişkili sahibi almak için bu yöntemi çağırın `CAccessToken` nesnesi.|  
|[CAccessToken::GetPrimaryGroup](#getprimarygroup)|İle ilişkili birincil grup almak için bu yöntemi çağırın `CAccessToken` nesnesi.|  
|[CAccessToken::GetPrivileges](#getprivileges)|İle ilişkili ayrıcalıklarını almak için bu yöntemi çağırın `CAccessToken` nesnesi.|  
|[CAccessToken::GetProcessToken](#getprocesstoken)|Başlatmak için bu yöntemi çağırın `CAccessToken` verilen işleminden erişim belirteci ile.|  
|[CAccessToken::GetProfile](#getprofile)|İle ilişkili kullanıcı profili işaret eden tanıtıcı almak için bu yöntemi çağırın `CAccessToken` nesnesi.|  
|[CAccessToken::GetSource](#getsource)|Kaynağını almak için bu yöntemi çağırın `CAccessToken` nesnesi.|  
|[CAccessToken::GetStatistics](#getstatistics)|İle ilgili bilgi almak için bu yöntemi çağırın `CAccessToken` nesnesi.|  
|[CAccessToken::GetTerminalServicesSessionId](#getterminalservicessessionid)|Terminal Hizmetleri oturum ile ilişkili Kimliği almak için bu yöntemi çağırın `CAccessToken` nesnesi.|  
|[CAccessToken::GetThreadToken](#getthreadtoken)|Başlatmak için bu yöntemi çağırın `CAccessToken` verilen iş parçacığı belirtecinden ile.|  
|[CAccessToken::GetTokenId](#gettokenid)|Belirteci ile ilişkili kimlik almak için bu yöntemi çağırın `CAccessToken` nesnesi.|  
|[CAccessToken::GetType](#gettype)|Belirteç türü almak için bu yöntemi çağırın `CAccessToken` nesnesi.|  
|[CAccessToken::GetUser](#getuser)|İle ilişkili kullanıcıyı tanımlamak için bu yöntemi çağırın `CAccessToken` nesnesi.|  
|[CAccessToken::HKeyCurrentUser](#hkeycurrentuser)|İle ilişkili kullanıcı profili işaret eden tanıtıcı almak için bu yöntemi çağırın `CAccessToken` nesnesi.|  
|[CAccessToken::Impersonate](#impersonate)|Bir kimliğe bürünme atamak için bu yöntemi çağırın `CAccessToken` bir iş parçacığı için.|  
|[CAccessToken::ImpersonateLoggedOnUser](#impersonateloggedonuser)|Çağıran iş parçacığı bir oturum açmış kullanıcının güvenlik bağlamı taklit etmesine izin vermek için bu yöntemi çağırın.|  
|[CAccessToken::IsTokenRestricted](#istokenrestricted)|Olmadığını sınamak için bu yöntemi çağırın `CAccessToken` nesne kısıtlı SID listesini içerir.|  
|[CAccessToken::LoadUserProfile](#loaduserprofile)|İle ilişkili kullanıcı profili yüklemek için bu yöntemi çağırın `CAccessToken` nesnesi.|  
|[CAccessToken::LogonUser](#logonuser)|Verilen kimlik bilgileriyle ilişkili kullanıcı için bir oturum açma oturumu oluşturmak için bu yöntemi çağırın.|  
|[CAccessToken::OpenCOMClientToken](#opencomclienttoken)|Başlatmak için bir çağrı istemciden gelen işleme COM sunucusu bu yöntemi çağırın `CAccessToken` COM istemcisinden erişim belirteci ile.|  
|[CAccessToken::OpenNamedPipeClientToken](#opennamedpipeclienttoken)|Bu bir sunucu içindeki alma isteği başlatmak için bir adlandırılmış kanal üzerinden çağırın `CAccessToken` istemci erişim belirteci ile.|  
|[CAccessToken::OpenRPCClientToken](#openrpcclienttoken)|Bir sunucu başlatmak için bir RPC istemci çağrısından işleme bu yöntemi çağırın `CAccessToken` istemci erişim belirteci ile.|  
|[CAccessToken::OpenThreadToken](#openthreadtoken)|Kimliğe bürünme düzeyini ayarlayın ve ardından başlatmak için bu yöntemi çağırın `CAccessToken` verilen iş parçacığı belirtecinden ile.|  
|[CAccessToken::PrivilegeCheck](#privilegecheck)|Belirtilen bir dizi ayrıcalık etkin içinde olup olmadığını belirlemek için bu yöntemi çağırın **CAccessToken** nesnesi.|  
|[CAccessToken::Revert](#revert)|Kimliğe bürünme simgesi kullanarak bir iş parçacığı durdurmak için bu yöntemi çağırın.|  
|[CAccessToken::SetDefaultDacl](#setdefaultdacl)|Varsayılan değer ayarlamak için bu yöntemi çağırın, DACL `CAccessToken` nesnesi.|  
|[CAccessToken::SetOwner](#setowner)|Sahibi ayarlamak için bu yöntemi çağırın `CAccessToken` nesnesi.|  
|[CAccessToken::SetPrimaryGroup](#setprimarygroup)|Birincil grup ayarlamak için bu yöntemi çağırın `CAccessToken` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir [erişim belirteci](http://msdn.microsoft.com/library/windows/desktop/aa374909) bir işlem veya iş parçacığı güvenlik bağlamında açıklayan ve bir Windows sisteminde oturum açmış her kullanıcı için ayrılan bir nesnedir.  
  
 Erişim denetimi modeli Windows giriş için bkz: [erişim denetimi](http://msdn.microsoft.com/library/windows/desktop/aa374860) Windows SDK'sındaki.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlsecurity.h  
  
##  <a name="attach"></a>  CAccessToken::Attach  
 Verilen erişim belirteci işleyici sahipliğini almak için bu yöntemi çağırın.  
  
```
void Attach(HANDLE hToken) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *hToken*  
 Erişim belirteci işleyici.  
  
### <a name="remarks"></a>Açıklamalar  
 Hata ayıklama derlemelerinde, bir onaylama hata oluşacaktır `CAccessToken` nesne zaten bir erişim belirteci sahipliğini içeriyor.  
  
##  <a name="dtor"></a>  CAccessToken:: ~ CAccessToken  
 Yok Edicisi.  
  
```
virtual ~CAccessToken() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrılan tüm kaynakları serbest bırakır.  
  
##  <a name="checktokenmembership"></a>  CAccessToken::CheckTokenMembership  
 Belirtilen SID, etkin olup olmadığını belirlemek için bu yöntemi çağırın `CAccessToken` nesnesi.  
  
```
bool CheckTokenMembership(
    const CSid& rSid, 
    bool* pbIsMember) const throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `rSid`  
 Başvuru bir [CSID sınıfı](../../atl/reference/csid-class.md) nesnesi.  
  
 `pbIsMember`  
 İşaretçi bir değişkene denetiminin sonuçlarını alır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 `CheckTokenMembership` Yöntemi kullanıcı ve Grup SID erişim belirtecinin SID varlığını denetler. SID varsa ve SE_GROUP_ENABLED özniteliğine sahip *pbIsMember* olan ayarlamak için true; içermiyorsa, false olarak ayarlanır.  
  
 Hata ayıklama derlemelerinde, bir onaylama hata oluşacaktır `pbIsMember` geçerli bir işaretçi değil.  
  
> [!NOTE]
>  `CAccessToken` Kimliğe bürünme simgesi ve bir birincil belirteç nesnesi olması gerekir.  
  
##  <a name="createimpersonationtoken"></a>  CAccessToken::CreateImpersonationToken  
 Kimliğe bürünme erişim belirteci oluşturmak için bu yöntemi çağırın.  
  
```
bool CreateImpersonationToken(
    CAccessToken* pImp, 
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) const throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `pImp`  
 İşaretçi yeni `CAccessToken` nesnesi.  
  
 `sil`  
 Belirten bir [SECURITY_IMPERSONATION_LEVEL](http://msdn.microsoft.com/library/windows/desktop/aa379572) numaralandırılmış yeni belirteci kimliğe bürünme düzeyini sağlayan türü.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 `CreateImpersonationToken` çağrıları [DuplicateToken](http://msdn.microsoft.com/library/windows/desktop/aa446616) yeni bir kimliğe bürünme belirteci oluşturmak için.  
  
##  <a name="createprimarytoken"></a>  CAccessToken::CreatePrimaryToken  
 Yeni birincil belirteç oluşturmak için bu yöntemi çağırın.  
  
```
bool CreatePrimaryToken(
    CAccessToken* pPri,
    DWORD dwDesiredAccess = MAXIMUM_ALLOWED,
    const CSecurityAttributes* pTokenAttributes = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 *pPri*  
 İşaretçi yeni `CAccessToken` nesnesi.  
  
 `dwDesiredAccess`  
 Yeni bir belirteç için istenen erişim haklarını belirtir. Varsayılan olarak, MAXIMUM_ALLOWED, çağıran için geçerli olan tüm erişim hakları ister. Bkz: [erişim haklarını ve erişim maskesi](http://msdn.microsoft.com/library/windows/desktop/aa374902) için daha fazla açık erişim hakları.  
  
 *pTokenAttributes*  
 İşaretçi bir [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) yeni belirteci için bir güvenlik tanımlayıcısı belirtir ve alt işlemleri belirteç devrettiği olup olmadığını belirleyen yapısı. Varsa *pTokenAttributes* NULL, varsayılan bir güvenlik açıklayıcısı belirtecini alır ve tanıtıcıyı devralınan.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 `CreatePrimaryToken` çağrıları [DuplicateTokenEx](http://msdn.microsoft.com/library/windows/desktop/aa446617) yeni birincil belirteç oluşturmak için.  
  
##  <a name="createprocessasuser"></a>  CAccessToken::CreateProcessAsUser  
 Tarafından temsil edilen kullanıcının güvenlik bağlamında çalışan yeni bir işlem oluşturmak için bu yöntemi çağırın `CAccessToken` nesnesi.  
  
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
 *pApplicationName*  
 İşaretçi null ile sonlandırılmış dizeye yürütmek için Modülü belirtir. Bu parametre NULL olamaz.  
  
 *pCommandLine*  
 İşaretçi null ile sonlandırılmış dizeye çalıştırılacak komut satırını belirtir.  
  
 *pProcessInformation*  
 İşaretçi bir [PROCESS_INFORMATION](http://msdn.microsoft.com/library/windows/desktop/ms684873) yapısı yeni işlemi tanımlama bilgilerini alır.  
  
 *pStartupInfo*  
 İşaretçi bir [değeri](http://msdn.microsoft.com/library/windows/desktop/ms686331) yeni işlem için ana pencere nasıl belirmelidir belirtir yapısı.  
  
 `dwCreationFlags`  
 Öncelik sınıfını ve işlem oluşturma denetleyen ek bayrakları belirtir. Win32 işlevi görmek [CreateProcessAsUser](http://msdn.microsoft.com/library/windows/desktop/ms682429) bayrakları listesi.  
  
 *bLoadProfile*  
 TRUE, kullanıcı profilinin ile yüklenen varsa [LoadUserProfile](http://msdn.microsoft.com/library/windows/desktop/bb762281).  
  
 *pProcessAttributes*  
 İşaretçi bir [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) yeni işlem için bir güvenlik tanımlayıcısı belirtir ve alt işlemleri döndürülen tanıtıcı devrettiği olup olmadığını belirleyen yapısı. Varsa *pProcessAttributes* NULL, işlem varsayılan bir güvenlik açıklayıcısı alır ve tanıtıcıyı devralınan.  
  
 *pThreadAttributes*  
 İşaretçi bir [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) yeni bir iş parçacığı için bir güvenlik tanımlayıcısı belirtir ve alt işlemleri döndürülen tanıtıcı devrettiği olup olmadığını belirleyen yapısı. Varsa *pThreadAttributes* NULL, varsayılan bir güvenlik açıklayıcısı iş parçacığı alır ve tanıtıcıyı devralınan.  
  
 *bInherit*  
 Yeni işlem arama işleminden tanıtıcıları devralıp almadığını gösterir. TRUE ise, her devralınabilir açık tanıtıcı arama işleminde yeni bir işlem tarafından devralınır. Devralınan tanıtıcıları özgün tanıtıcıları aynı değeri ve erişim ayrıcalıkları vardır.  
  
 *pCurrentDirectory*  
 İşaretçi null ile sonlandırılmış dizeye geçerli sürücü ve yeni işlem dizini belirtir. Dize, bir sürücü harfi içeren tam bir yol olmalıdır. Bu parametre NULL ise, yeni işlem çağırma işlemi aynı geçerli sürücü ve dizine sahip.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 **CreateProcessAsUser** kullanan `CreateProcessAsUser` tarafından temsil edilen kullanıcının güvenlik bağlamında çalışan yeni bir işlem oluşturmak için Win32 işlevi `CAccessToken` nesnesi. Açıklamasını görmek [CreateProcessAsUser](http://msdn.microsoft.com/library/windows/desktop/ms682429) işlevi tam bir irdelemesi için gereken parametrelerden biri.  
  
 Başarılı olması bu yöntem için `CAccessToken` (sınırlı bir belirteç değilse), nesne AssignPrimaryToken tutun gerekir ve IncreaseQuota ayrıcalıkları.  
  
##  <a name="createrestrictedtoken"></a>  CAccessToken::CreateRestrictedToken  
 Yeni, oluşturmak için bu yöntemi çağırın kısıtlı `CAccessToken` nesnesi.  
  
```
bool CreateRestrictedToken(
    CAccessToken* pRestrictedToken,
    const CTokenGroups& SidsToDisable,
    const CTokenGroups& SidsToRestrict,
    const CTokenPrivileges& PrivilegesToDelete = CTokenPrivileges()) const throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 *pRestrictedToken*  
 Yeni, kısıtlanmış `CAccessToken` nesnesi.  
  
 `SidsToDisable`  
 A `CTokenGroups` yalnızca Reddet SID'ler belirtir nesnesi.  
  
 *SidsToRestrict*  
 A `CTokenGroups` kısıtlama SID'ler belirtir nesnesi.  
  
 `PrivilegesToDelete`  
 A `CTokenPrivileges` silmek için ayrıcalıkları sınırlı belirteçte belirtir nesnesi. Varsayılan boş bir nesne oluşturur.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 `CreateRestrictedToken` kullanan [CreateRestrictedToken](http://msdn.microsoft.com/library/windows/desktop/aa446583) yeni Win32 işlevi `CAccessToken` nesnesiyle kısıtlamaları.  
  
> [!IMPORTANT]
>  Kullanırken `CreateRestrictedToken`, aşağıdakilerden emin olun: Varolan belirtecin geçerli (ve kullanıcı tarafından girilen) ve `SidsToDisable` ve `PrivilegesToDelete` hem geçerli (hem de kullanıcı tarafından girilen). Yöntem false değeri döndürülürse, işlevselliği reddedin.  
  
##  <a name="detach"></a>  CAccessToken::Detach  
 Erişim belirteci sahipliğini iptal etmek için bu yöntemi çağırın.  
  
```
HANDLE Detach() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşleyici döner `CAccessToken` , ayrılmış.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem iptal `CAccessToken`kişinin erişim belirteci sahipliğini.  
  
##  <a name="disableprivilege"></a>  CAccessToken::DisablePrivilege  
 Bir ayrıcalık devre dışı bırakmak için bu yöntemi çağırabilmeniz `CAccessToken` nesnesi.  
  
```
bool DisablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `pszPrivilege`  
 Devre dışı bırakmak için ayrıcalık içeren bir dize işaretçi `CAccessToken` nesnesi.  
  
 `pPreviousState`  
 İşaretçi bir `CTokenPrivileges` ayrıcalıkları önceki durumunu içeren nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
##  <a name="disableprivileges"></a>  CAccessToken::DisablePrivileges  
 Bir veya daha fazla ayrıcalık devre dışı bırakmak için bu yöntemi çağırabilmeniz `CAccessToken` nesnesi.  
  
```
bool DisablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `rPrivileges`  
 Devre dışı bırakmak için ayrıcalıkları içeren bir dizeler dizisi işaretçi `CAccessToken` nesnesi.  
  
 `pPreviousState`  
 İşaretçi bir `CTokenPrivileges` ayrıcalıkları önceki durumunu içeren nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
##  <a name="enableprivilege"></a>  CAccessToken::EnablePrivilege  
 Bir ayrıcalık etkinleştirmek için bu yöntemi çağırın `CAccessToken` nesnesi.  
  
```
bool EnablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `pszPrivilege`  
 Etkinleştirmek için ayrıcalık içeren bir dize işaretçi `CAccessToken` nesnesi.  
  
 `pPreviousState`  
 İşaretçi bir `CTokenPrivileges` ayrıcalıkları önceki durumunu içeren nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
##  <a name="enableprivileges"></a>  CAccessToken::EnablePrivileges  
 Bir veya daha fazla ayrıcalık etkinleştirmek için bu yöntemi çağırın `CAccessToken` nesnesi.  
  
```
bool EnablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `rPrivileges`  
 Etkinleştirmek için ayrıcalıkları içeren bir dizeler dizisi işaretçi `CAccessToken` nesnesi.  
  
 `pPreviousState`  
 İşaretçi bir `CTokenPrivileges` ayrıcalıkları önceki durumunu içeren nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
##  <a name="getdefaultdacl"></a>  CAccessToken::GetDefaultDacl  
 Döndürmek için bu yöntemi çağırabilmeniz `CAccessToken` nesnenin varsayılan DACL.  
  
```
bool GetDefaultDacl(CDacl* pDacl) const throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDacl`  
 İşaretçi [CDacl sınıfı](../../atl/reference/cdacl-class.md) alacak nesne **CAccessToken** nesnenin varsayılan DACL.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan DACL, aksi takdirde kurtarılan, yanlış olması durumunda true döndürür.  
  
##  <a name="geteffectivetoken"></a>  CAccessToken::GetEffectiveToken  
 Almak için bu yöntemi çağırın `CAccessToken` nesne geçerli iş parçacığının etkin için erişim belirtecini eşittir.  
  
```
bool GetEffectiveToken(DWORD dwDesiredAccess) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `dwDesiredAccess`  
 İstenen türlerde erişim belirtecini erişim belirten erişim maskesi belirtir. Bu istenen erişim türleri hangi erişim verilen veya reddedilen belirlemek için belirtecin DACL ile karşılaştırılır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
##  <a name="getgroups"></a>  CAccessToken::GetGroups  
 Döndürmek için bu yöntemi çağırabilmeniz `CAccessToken` nesnenin belirteç grupları.  
  
```
bool GetGroups(CTokenGroups* pGroups) const throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 *pGroups*  
 İşaretçi [CTokenGroups sınıfı](../../atl/reference/ctokengroups-class.md) grup bilgileri alacak nesnesidir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
##  <a name="gethandle"></a>  CAccessToken::GetHandle  
 Erişim belirteci işleyici almak için bu yöntemi çağırın.  
  
```
HANDLE GetHandle() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işleyici döner `CAccessToken` nesnenin erişim belirteci.  
  
##  <a name="getimpersonationlevel"></a>  CAccessToken::GetImpersonationLevel  
 Kimliğe bürünme düzeyi erişim belirtecinden almak için bu yöntemi çağırın.  
  
```
bool GetImpersonationLevel(
    SECURITY_IMPERSONATION_LEVEL* pImpersonationLevel) const throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 *pImpersonationLevel*  
 İşaretçi bir [SECURITY_IMPERSONATION_LEVEL](http://msdn.microsoft.com/library/windows/desktop/aa379572) kimliğe bürünme düzeyi bilgileri alacak numaralandırma türü.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
##  <a name="getlogonsessionid"></a>  CAccessToken::GetLogonSessionId  
 İlişkili oturum açma oturum kimliği almak için bu yöntemi çağırın `CAccessToken` nesnesi.  
  
```
bool GetLogonSessionId(LUID* pluid) const throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `pluid`  
 İşaretçi bir [LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261) hangi alır oturum açma oturum kimliği  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Hata ayıklama derlemelerinde, bir onaylama hata oluşacaktır `pluid` geçersiz bir değer.  
  
##  <a name="getlogonsid"></a>  CAccessToken::GetLogonSid  
 İlişkili oturum açma SID almak için bu yöntemi çağırın `CAccessToken` nesnesi.  
  
```
bool GetLogonSid(CSid* pSid) const throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `pSid`  
 İşaretçi bir [CSID sınıfı](../../atl/reference/csid-class.md) nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Hata ayıklama derlemelerinde, bir onaylama hata oluşacaktır *Psıd* geçersiz bir değer.  
  
##  <a name="getowner"></a>  CAccessToken::GetOwner  
 İle ilişkili sahibi almak için bu yöntemi çağırın `CAccessToken` nesnesi.  
  
```
bool GetOwner(CSid* pSid) const throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `pSid`  
 İşaretçi bir [CSID sınıfı](../../atl/reference/csid-class.md) nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Sahibi, bu erişim belirteci etkinken oluşturulan tüm nesneler üzerinde varsayılan olarak ayarlanır.  
  
##  <a name="getprimarygroup"></a>  CAccessToken::GetPrimaryGroup  
 İle ilişkili birincil grup almak için bu yöntemi çağırın `CAccessToken` nesnesi.  
  
```
bool GetPrimaryGroup(CSid* pSid) const throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `pSid`  
 İşaretçi bir [CSID sınıfı](../../atl/reference/csid-class.md) nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Grup, bu erişim belirteci etkinken oluşturulan tüm nesneler üzerinde varsayılan olarak ayarlanır.  
  
##  <a name="getprivileges"></a>  CAccessToken::GetPrivileges  
 İle ilişkili ayrıcalıklarını almak için bu yöntemi çağırın `CAccessToken` nesnesi.  
  
```
bool GetPrivileges(CTokenPrivileges* pPrivileges) const throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `pPrivileges`  
 İşaretçi bir [CTokenPrivileges sınıfı](../../atl/reference/ctokenprivileges-class.md) ayrıcalıkları alacak nesnesidir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
##  <a name="getprocesstoken"></a>  CAccessToken::GetProcessToken  
 Başlatmak için bu yöntemi çağırın `CAccessToken` verilen işleminden erişim belirteci ile.  
  
```
bool GetProcessToken(DWORD dwDesiredAccess, HANDLE hProcess = NULL) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `dwDesiredAccess`  
 İstenen türlerde erişim belirtecini erişim belirten erişim maskesi belirtir. Bu istenen erişim türleri hangi erişim verilen veya reddedilen belirlemek için belirtecin DACL ile karşılaştırılır.  
  
 *hProcess*  
 Erişim belirteci açıldığında işlem işleyin. Varsa varsayılan değer olan `NULL` olan kullanıldığında, geçerli işlemin kullanılır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `true` başarılı, `false` hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrıları [OpenProcessToken](http://msdn.microsoft.com/library/aa379295\(vs.85\).aspx) Win32 işlevi.  
  
##  <a name="getprofile"></a>  CAccessToken::GetProfile  
 İle ilişkili kullanıcı profili işaret eden tanıtıcı almak için bu yöntemi çağırın `CAccessToken` nesnesi.  
  
```
HANDLE GetProfile() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Profil yok, kullanıcı profili ya da NULL için işaret eden bir işleyici döner.  
  
##  <a name="getsource"></a>  CAccessToken::GetSource  
 Kaynağını almak için bu yöntemi çağırın `CAccessToken` nesnesi.  
  
```
bool GetSource(TOKEN_SOURCE* pSource) const throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 *pSource*  
 İşaretçi bir [TOKEN_SOURCE](http://msdn.microsoft.com/library/windows/desktop/aa379631) yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
##  <a name="getstatistics"></a>  CAccessToken::GetStatistics  
 İle ilgili bilgi almak için bu yöntemi çağırın `CAccessToken` nesnesi.  
  
```
bool GetStatistics(TOKEN_STATISTICS* pStatistics) const throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 *pStatistics*  
 İşaretçi bir [TOKEN_STATISTICS](http://msdn.microsoft.com/library/windows/desktop/aa379632) yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
##  <a name="getterminalservicessessionid"></a>  CAccessToken::GetTerminalServicesSessionId  
 Terminal Hizmetleri oturum ile ilişkili Kimliği almak için bu yöntemi çağırın `CAccessToken` nesnesi.  
  
```
bool GetTerminalServicesSessionId(DWORD* pdwSessionId) const throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 *pdwSessionId*  
 Terminal Hizmetleri oturum kimliği  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
##  <a name="getthreadtoken"></a>  CAccessToken::GetThreadToken  
 Başlatmak için bu yöntemi çağırın `CAccessToken` verilen iş parçacığı belirtecinden ile.  
  
```
bool GetThreadToken(
    DWORD dwDesiredAccess,
    HANDLE hThread = NULL,
    bool bOpenAsSelf = true) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `dwDesiredAccess`  
 İstenen türlerde erişim belirtecini erişim belirten erişim maskesi belirtir. Bu istenen erişim türleri hangi erişim verilen veya reddedilen belirlemek için belirtecin DACL ile karşılaştırılır.  
  
 `hThread`  
 Erişim belirteci açıldığında iş parçacığına işleyin.  
  
 `bOpenAsSelf`  
 Erişim denetimi iş parçacığı arama güvenlik bağlamı karşı yapılması olup olmadığını belirten `GetThreadToken` yöntem veya işlem çağıran iş parçacığı için güvenlik bağlamı karşı.  
  
 Bu parametre false ise, erişim denetimi çağıran iş parçacığı için güvenlik bağlamı kullanılarak gerçekleştirilir. İş parçacığı bir istemcinin kimliğine bürünüyor varsa, bu güvenlik bağlamı, bir istemci işlemi olabilir. Bu parametre true ise, erişim denetimi çağıran iş parçacığı için işlem güvenlik bağlamını kullanarak yapılır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
##  <a name="gettokenid"></a>  CAccessToken::GetTokenId  
 Belirteci ile ilişkili kimlik almak için bu yöntemi çağırın `CAccessToken` nesnesi.  
  
```
bool GetTokenId(LUID* pluid) const throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `pluid`  
 İşaretçi bir [LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261) hangi alır belirteç kimliği  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
##  <a name="gettype"></a>  CAccessToken::GetType  
 Belirteç türü almak için bu yöntemi çağırın `CAccessToken` nesnesi.  
  
```
bool GetType(TOKEN_TYPE* pType) const throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `pType`  
 Adres [TOKEN_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379633) , başarı, belirtecin türü aldığı değişkeni.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 **TOKEN_TYPE** numaralandırma türü birincil belirteç ve kimliğe bürünme simgesi arasında ayırt değerleri içerir.  
  
##  <a name="getuser"></a>  CAccessToken::GetUser  
 İle ilişkili kullanıcıyı tanımlamak için bu yöntemi çağırın `CAccessToken` nesnesi.  
  
```
bool GetUser(CSid* pSid) const throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `pSid`  
 İşaretçi bir [CSID sınıfı](../../atl/reference/csid-class.md) nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
##  <a name="hkeycurrentuser"></a>  CAccessToken::HKeyCurrentUser  
 İle ilişkili kullanıcı profili işaret eden tanıtıcı almak için bu yöntemi çağırın `CAccessToken` nesnesi.  
  
```
HKEY HKeyCurrentUser() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Profil yok, kullanıcı profili ya da NULL için işaret eden bir işleyici döner.  
  
##  <a name="impersonate"></a>  CAccessToken::Impersonate  
 Bir kimliğe bürünme atamak için bu yöntemi çağırın `CAccessToken` bir iş parçacığı için.  
  
```
bool Impersonate(HANDLE hThread = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `hThread`  
 İş parçacığı için kimliğe bürünme belirtecini atamak için işleyin. Bu işleyici TOKEN_IMPERSONATE erişim haklarıyla açılmış olmalıdır. Varsa `hThread` null, kimliğe bürünme simgesi kullanarak durdurmak iş parçacığı yöntemi neden olur.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Hata ayıklama derlemelerinde, bir onaylama hata oluşacaktır `CAccessToken` bir belirteci için geçerli bir işaretçi yok.  
  
 [CAutoRevertImpersonation sınıfı](../../atl/reference/cautorevertimpersonation-class.md) otomatik olarak Kimliğine bürünülen erişim belirteçleri geri dönmek için kullanılabilir.  
  
##  <a name="impersonateloggedonuser"></a>  CAccessToken::ImpersonateLoggedOnUser  
 Çağıran iş parçacığı bir oturum açmış kullanıcının güvenlik bağlamı taklit etmesine izin vermek için bu yöntemi çağırın.  
  
```
bool ImpersonateLoggedOnUser() const throw(...);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!IMPORTANT]
>  Kimliğe bürünme işlevi çağrısı herhangi bir nedenle başarısız olursa, istemci kimliğine bürünülen değildir ve istemci isteği çağrı yapıldığı işlem güvenlik bağlamında yapılır. Bir yönetici grubunun bir üyesi olarak kullanıcı eylemleri gerçekleştirmek olabilir veya işlem yüksek ayrıcalıklı bir hesap çalışıyorsa çözemiyorsa aksi izni. Bu nedenle, bu işlev için dönüş değeri her zaman onaylanması.  
  
##  <a name="istokenrestricted"></a>  CAccessToken::IsTokenRestricted  
 Olmadığını sınamak için bu yöntemi çağırın `CAccessToken` nesne kısıtlı SID listesini içerir.  
  
```
bool IsTokenRestricted() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Nesne SID'leri, hiçbir kısıtlama SID varsa false kısıtlama listesi içeriyorsa veya yöntem başarısız olursa true değerini döndürür.  
  
##  <a name="loaduserprofile"></a>  CAccessToken::LoadUserProfile  
 İle ilişkili kullanıcı profili yüklemek için bu yöntemi çağırın `CAccessToken` nesnesi.  
  
```
bool LoadUserProfile() throw(...);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Hata ayıklama derlemelerinde, bir onaylama hata oluşacaktır `CAccessToken` geçerli bir belirteci içermiyor veya zaten bir kullanıcı profili varsa.  
  
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
 `pszUserName`  
 İşaretçi null ile sonlandırılmış dizeye kullanıcı adını belirtir. Bu oturum için kullanıcı hesabının adıdır.  
  
 *pszDomain*  
 Etki alanı veya sunucu, hesap veritabanı adını belirten null ile sonlandırılmış bir dize işaretçi `pszUserName` hesabı.  
  
 `pszPassword`  
 İşaretçi tarafından belirtilen kullanıcı hesabı için düz metin parola belirten null ile sonlandırılmış bir dizeye `pszUserName`.  
  
 *dwLogonType*  
 Gerçekleştirmek için oturum açma işlemi türünü belirtir. Bkz: [LogonUser](http://msdn.microsoft.com/library/windows/desktop/aa378184) daha fazla ayrıntı için.  
  
 *dwLogonProvider*  
 Oturum açma sağlayıcısı belirtir. Bkz: [LogonUser](http://msdn.microsoft.com/library/windows/desktop/aa378184) daha fazla ayrıntı için.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirteç oturum açma konumundan kaynaklanan ilişkilendirilebilir erişim `CAccessToken`. Başarılı olması bu yöntem için `CAccessToken` nesne sahibi güvenilen bir bilgisayar temel bir parçası olarak tanımlayan SE_TCB_NAME ayrıcalıkları tutun gerekir. Bkz: [LogonUser](http://msdn.microsoft.com/library/windows/desktop/aa378184) gereken ayrıcalıklar ilgili daha fazla bilgi.  
  
##  <a name="opencomclienttoken"></a>  CAccessToken::OpenCOMClientToken  
 Başlatmak için bir çağrı istemciden gelen işleme COM sunucusu bu yöntemi çağırın `CAccessToken` COM istemcisinden erişim belirteci ile.  
  
```
bool OpenCOMClientToken(
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwDesiredAccess`  
 İstenen türlerde erişim belirtecini erişim belirten erişim maskesi belirtir. Bu istenen erişim türleri hangi erişim verilen veya reddedilen belirlemek için belirtecin DACL ile karşılaştırılır.  
  
 `bImpersonate`  
 Bu çağrı başarıyla tamamlarsa true ise, geçerli iş parçacığı arama COM istemcinin. False ise, erişim belirteci açılacak ancak bu çağrıyı tamamlandığında iş parçacığı kimliğe bürünme simgesi sahip olmaz.  
  
 `bOpenAsSelf`  
 Erişim denetimi iş parçacığı arama güvenlik bağlamı karşı yapılması olup olmadığını belirten [GetThreadToken](http://msdn.microsoft.com/library/windows/desktop/ms683182) yöntem veya işlem çağıran iş parçacığı için güvenlik bağlamı karşı.  
  
 Bu parametre false ise, erişim denetimi çağıran iş parçacığı için güvenlik bağlamı kullanılarak gerçekleştirilir. İş parçacığı bir istemcinin kimliğine bürünüyor varsa, bu güvenlik bağlamı, bir istemci işlemi olabilir. Bu parametre true ise, erişim denetimi çağıran iş parçacığı için işlem güvenlik bağlamını kullanarak yapılır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 [CAutoRevertImpersonation sınıfı](../../atl/reference/cautorevertimpersonation-class.md) otomatik olarak ayarlayarak oluşturulan Kimliğine bürünülen erişim belirteçleri geri döndürmek için kullanılan `bImpersonate` bayrağını *doğru*.  
  
##  <a name="opennamedpipeclienttoken"></a>  CAccessToken::OpenNamedPipeClientToken  
 Bu bir sunucu içindeki alma isteği başlatmak için bir adlandırılmış kanal üzerinden çağırın `CAccessToken` istemci erişim belirteci ile.  
  
```
bool OpenNamedPipeClientToken(
    HANDLE hPipe,
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 *hPipe*  
 Bir adlandırılmış kanal işleyin.  
  
 `dwDesiredAccess`  
 İstenen türlerde erişim belirtecini erişim belirten erişim maskesi belirtir. Bu istenen erişim türleri hangi erişim verilen veya reddedilen belirlemek için belirtecin DACL ile karşılaştırılır.  
  
 `bImpersonate`  
 Bu çağrı başarıyla tamamlarsa true ise, geçerli iş parçacığı arama kanal istemci kimliğine. False ise, erişim belirteci açılacak ancak bu çağrıyı tamamlandığında iş parçacığı kimliğe bürünme simgesi sahip olmaz.  
  
 `bOpenAsSelf`  
 Erişim denetimi iş parçacığı arama güvenlik bağlamı karşı yapılması olup olmadığını belirten [GetThreadToken](http://msdn.microsoft.com/library/windows/desktop/ms683182) yöntem veya işlem çağıran iş parçacığı için güvenlik bağlamı karşı.  
  
 Bu parametre false ise, erişim denetimi çağıran iş parçacığı için güvenlik bağlamı kullanılarak gerçekleştirilir. İş parçacığı bir istemcinin kimliğine bürünüyor varsa, bu güvenlik bağlamı, bir istemci işlemi olabilir. Bu parametre true ise, erişim denetimi çağıran iş parçacığı için işlem güvenlik bağlamını kullanarak yapılır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 [CAutoRevertImpersonation sınıfı](../../atl/reference/cautorevertimpersonation-class.md) otomatik olarak ayarlayarak oluşturulan Kimliğine bürünülen erişim belirteçleri geri döndürmek için kullanılan `bImpersonate` bayrağını *doğru*.  
  
##  <a name="openrpcclienttoken"></a>  CAccessToken::OpenRPCClientToken  
 Bir sunucu başlatmak için bir RPC istemci çağrısından işleme bu yöntemi çağırın `CAccessToken` istemci erişim belirteci ile.  
  
```
bool OpenRPCClientToken(
    RPC_BINDING_HANDLE BindingHandle,
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 *BindingHandle*  
 Bağlama işleci sunucuda istemciye bağlama temsil eder.  
  
 `dwDesiredAccess`  
 İstenen türlerde erişim belirtecini erişim belirten erişim maskesi belirtir. Bu istenen erişim türleri hangi erişim verilen veya reddedilen belirlemek için belirtecin DACL ile karşılaştırılır.  
  
 `bImpersonate`  
 Bu çağrı başarıyla tamamlarsa true ise, geçerli iş parçacığı arama RPC istemcinin. False ise, erişim belirteci açılacak ancak bu çağrıyı tamamlandığında iş parçacığı kimliğe bürünme simgesi sahip olmaz.  
  
 `bOpenAsSelf`  
 Erişim denetimi iş parçacığı arama güvenlik bağlamı karşı yapılması olup olmadığını belirten [GetThreadToken](http://msdn.microsoft.com/library/windows/desktop/ms683182) yöntem veya işlem çağıran iş parçacığı için güvenlik bağlamı karşı.  
  
 Bu parametre false ise, erişim denetimi çağıran iş parçacığı için güvenlik bağlamı kullanılarak gerçekleştirilir. İş parçacığı bir istemcinin kimliğine bürünüyor varsa, bu güvenlik bağlamı, bir istemci işlemi olabilir. Bu parametre true ise, erişim denetimi çağıran iş parçacığı için işlem güvenlik bağlamını kullanarak yapılır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 [CAutoRevertImpersonation sınıfı](../../atl/reference/cautorevertimpersonation-class.md) otomatik olarak ayarlayarak oluşturulan Kimliğine bürünülen erişim belirteçleri geri döndürmek için kullanılan `bImpersonate` bayrağını *doğru*.  
  
##  <a name="openthreadtoken"></a>  CAccessToken::OpenThreadToken  
 Kimliğe bürünme düzeyini ayarlayın ve ardından başlatmak için bu yöntemi çağırın `CAccessToken` verilen iş parçacığı belirtecinden ile.  
  
```
bool OpenThreadToken(
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true,
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwDesiredAccess`  
 İstenen türlerde erişim belirtecini erişim belirten erişim maskesi belirtir. Bu istenen erişim türleri hangi erişim verilen veya reddedilen belirlemek için belirtecin DACL ile karşılaştırılır.  
  
 `bImpersonate`  
 Bu yöntem tamamlandıktan sonra true ise, iş parçacığı istenen kimliğe bürünme düzeyinde kalacaktır. False ise, iş parçacığının kendi özgün kimliğe bürünme düzeyini döner.  
  
 `bOpenAsSelf`  
 Erişim denetimi iş parçacığı arama güvenlik bağlamı karşı yapılması olup olmadığını belirten [GetThreadToken](http://msdn.microsoft.com/library/windows/desktop/ms683182) yöntem veya işlem çağıran iş parçacığı için güvenlik bağlamı karşı.  
  
 Bu parametre false ise, erişim denetimi çağıran iş parçacığı için güvenlik bağlamı kullanılarak gerçekleştirilir. İş parçacığı bir istemcinin kimliğine bürünüyor varsa, bu güvenlik bağlamı, bir istemci işlemi olabilir. Bu parametre true ise, erişim denetimi çağıran iş parçacığı için işlem güvenlik bağlamını kullanarak yapılır.  
  
 `sil`  
 Belirten bir [SECURITY_IMPERSONATION_LEVEL](http://msdn.microsoft.com/library/windows/desktop/aa379572) numaralandırılmış belirteç kimliğe bürünme düzeyini sağlayan türü.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 `OpenThreadToken` benzer [CAccessToken::GetThreadToken](#getthreadtoken), ancak başlatmadan önce kimliğe bürünme düzeyi ayarlar `CAccessToken` iş parçacığının erişim belirteci gelen.  
  
 [CAutoRevertImpersonation sınıfı](../../atl/reference/cautorevertimpersonation-class.md) otomatik olarak ayarlayarak oluşturulan Kimliğine bürünülen erişim belirteçleri geri döndürmek için kullanılan `bImpersonate` bayrağını *doğru*.  
  
##  <a name="privilegecheck"></a>  CAccessToken::PrivilegeCheck  
 Belirtilen bir dizi ayrıcalık etkin içinde olup olmadığını belirlemek için bu yöntemi çağırın **CAccessToken** nesnesi.  
  
```
bool PrivilegeCheck(
    PPRIVILEGE_SET RequiredPrivileges,
     bool* pbResult) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *RequiredPrivileges*  
 İşaretçi bir [PRIVILEGE_SET](http://msdn.microsoft.com/library/windows/desktop/aa379307) yapısı.  
  
 *pbResult*  
 Yöntemi bir değer işaretçisine ayarlar içinde belirtilen ayrıcalık bir bölümünü veya tamamını etkin olup olmadığını belirtmek için `CAccessToken` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Zaman `PrivilegeCheck` döndürür, **öznitelikleri** her üyesi [LUID_AND_ATTRIBUTES konusuna](http://msdn.microsoft.com/library/windows/desktop/aa379263) karşılık gelen ayrıcalık etkinleştirilirse yapısı SE_PRIVILEGE_USED_FOR_ACCESS için ayarlanır. Bu yöntemi çağırır [PrivilegeCheck](http://msdn.microsoft.com/library/windows/desktop/aa379304) Win32 işlevi.  
  
##  <a name="revert"></a>  CAccessToken::Revert  
 Kimliğe bürünme simgesi kullanarak bir iş parçacığı durdurmak için bu yöntemi çağırın.  
  
```
bool Revert(HANDLE hThread = NULL) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `hThread`  
 Kimliğe bürünme dönmek için iş parçacığı için işleyin. Varsa *hThread* null, geçerli iş parçacığının varsayılır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Geri Al'kimliğe bürünme belirteçlerin ile otomatik olarak gerçekleştirilebilir [CAutoRevertImpersonation sınıfı](../../atl/reference/cautorevertimpersonation-class.md).  
  
##  <a name="setdefaultdacl"></a>  CAccessToken::SetDefaultDacl  
 Varsayılan değer ayarlamak için bu yöntemi çağırın, DACL `CAccessToken` nesnesi.  
  
```
bool SetDefaultDacl(const CDacl& rDacl) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `rDacl`  
 Yeni varsayılan [CDacl sınıfı](../../atl/reference/cdacl-class.md) bilgi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 DACL yeni nesneler bu erişim belirteciyle yürürlükte oluşturulduğunda, varsayılan olarak kullanılan DACL varsayılandır.  
  
##  <a name="setowner"></a>  CAccessToken::SetOwner  
 Sahibi ayarlamak için bu yöntemi çağırın `CAccessToken` nesnesi.  
  
```
bool SetOwner(const CSid& rSid) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `rSid`  
 [CSID sınıfı](../../atl/reference/csid-class.md) sahibi ile ilgili bilgileri içeren bir nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu erişim belirteci etkinken oluşturulan yeni nesneler için kullanılan varsayılan sahibi sahibidir.  
  
##  <a name="setprimarygroup"></a>  CAccessToken::SetPrimaryGroup  
 Birincil grup ayarlamak için bu yöntemi çağırın `CAccessToken` nesnesi.  
  
```
bool SetPrimaryGroup(const CSid& rSid) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `rSid`  
 [CSID sınıfı](../../atl/reference/csid-class.md) birincil grup bilgilerini içeren bir nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Birincil grup bu erişim belirteci etkinken oluşturulan yeni nesneler için varsayılan grubudur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATLSecurity örnek](../../visual-cpp-samples.md)   
 [Erişim belirteçleri](http://msdn.microsoft.com/library/windows/desktop/aa374909)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
