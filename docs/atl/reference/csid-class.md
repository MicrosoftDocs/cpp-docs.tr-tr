---
title: "CSID sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSid
- ATLSECURITY/ATL::CSid
- ATLSECURITY/ATL::CSid::CSidArray
- ATLSECURITY/ATL::CSid::CSid
- ATLSECURITY/ATL::CSid::AccountName
- ATLSECURITY/ATL::CSid::Domain
- ATLSECURITY/ATL::CSid::EqualPrefix
- ATLSECURITY/ATL::CSid::GetLength
- ATLSECURITY/ATL::CSid::GetPSID
- ATLSECURITY/ATL::CSid::GetPSID_IDENTIFIER_AUTHORITY
- ATLSECURITY/ATL::CSid::GetSubAuthority
- ATLSECURITY/ATL::CSid::GetSubAuthorityCount
- ATLSECURITY/ATL::CSid::IsValid
- ATLSECURITY/ATL::CSid::LoadAccount
- ATLSECURITY/ATL::CSid::Sid
- ATLSECURITY/ATL::CSid::SidNameUse
dev_langs: C++
helpviewer_keywords: CSid class
ms.assetid: be58b7ca-5958-49c3-a833-ca341aaaf753
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3915206f0b05e33d5e13e41871a597ea7278ee8f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="csid-class"></a>CSID sınıfı
Bu sınıf için sarmalayıcı, bir `SID` (güvenlik tanımlayıcısı) yapısı.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CSid
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSid::CSidArray](#csidarray)|Bir dizi `CSid` nesneleri.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSid::CSid](#csid)|Oluşturucu.|  
|[CSID:: ~ CSID](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSid::AccountName](#accountname)|İle ilişkili hesap adını döndürür `CSid` nesnesi.|  
|[CSid::Domain](#domain)|İle ilişkili etki alanı adını döndürür `CSid` nesnesi.|  
|[CSid::EqualPrefix](#equalprefix)|Testleri `SID` (güvenlik tanımlayıcısı) önekleri eşitlik için.|  
|[CSid::GetLength](#getlength)|Uzunluğunu döndürür `CSid` nesnesi.|  
|[CSid::GetPSID](#getpsid)|Bir işaretçi döndüren bir `SID` yapısı.|  
|[CSid::GetPSID_IDENTIFIER_AUTHORITY](#getpsid_identifier_authority)|Bir işaretçi döndürür **SID_IDENTIFIER_AUTHORITY** yapısı.|  
|[CSid::GetSubAuthority](#getsubauthority)|İçinde belirtilen bir kimliğinin alt yetki verir bir **SID** yapısı.|  
|[CSid::GetSubAuthorityCount](#getsubauthoritycount)|Kimliğinin alt yetki sayımını döndürür.|  
|[CSid::IsValid](#isvalid)|Testleri `CSid` geçerliliğini nesnesi.|  
|[CSid::LoadAccount](#loadaccount)|Güncelleştirmeleri `CSid` verilen hesap adı ve etki alanı veya varolan bir nesne `SID` yapısı.|  
|[CSid::Sid](#sid)|Kimlik dizesi döndürür.|  
|[CSid::SidNameUse](#sidnameuse)|Durumu açıklamasını döndürür `CSid` nesnesi.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[işleç =](#operator_eq)|Atama işleci.|  
|[İşleç const SID *](#operator_const_sid__star)|Atamalar bir `CSid` gösteren bir işaretçi nesnesine bir `SID` yapısı.|  
  
### <a name="global-operators"></a>Genel işleçler  
  
|||  
|-|-|  
|[operator ==](#operator_eq_eq)|İki güvenlik tanımlayıcısı nesnenin eşitlik için test|  
|[operator! =](#operator_neq)|Eşitsizlik açısından iki güvenlik tanımlayıcısı nesneleri testleri|  
|[işleci\<](#operator_lt_)|Göreli iki güvenlik tanımlayıcısı nesneleri karşılaştırır.|  
|[operator >](#operator_gt_)|Göreli iki güvenlik tanımlayıcısı nesneleri karşılaştırır.|  
|[işleci\<=](#operator_lt__eq)|Göreli iki güvenlik tanımlayıcısı nesneleri karşılaştırır.|  
|[operator > =](#operator_gt__eq)|Göreli iki güvenlik tanımlayıcısı nesneleri karşılaştırır.|  
  
## <a name="remarks"></a>Açıklamalar  
 `SID` Kullanıcıları veya grupları benzersiz şekilde tanımlamak için kullanılan bir değişken uzunlukta yapısı yapısıdır.  
  
 Uygulamaları değişiklik `SID` yapısı doğrudan, ancak bunun yerine bu sarmalayıcı sınıfı sağlanan yöntemleri kullanın. Ayrıca bkz. [AtlGetOwnerSid](security-global-functions.md#atlgetownersid), [AtlSetGroupSid](security-global-functions.md#atlsetgroupsid), [AtlGetGroupSid](security-global-functions.md#atlgetgroupsid), ve [AtlSetOwnerSid](security-global-functions.md#atlsetownersid).  
  
 Erişim denetimi modeli Windows giriş için bkz: [erişim denetimi](http://msdn.microsoft.com/library/windows/desktop/aa374860) Windows SDK'sındaki.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlsecurity.h  
  
##  <a name="accountname"></a>CSid::AccountName  
 İle ilişkili hesap adını döndürür `CSid` nesnesi.  
  
```
LPCTSTR AccountName() const throw(...);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `LPCTSTR` hesap adına işaret eden.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, bir ad için belirtilen bulmayı dener `SID` (güvenlik tanımlayıcısı). Ayrıntılar için bkz: [LookupAccountSid](http://msdn.microsoft.com/library/windows/desktop/aa379166).  
  
 Hesap adı için `SID` bulunabilir, `AccountName` boş bir dize döndürür. Bu durum ağ zaman aşımı bu yöntem adı bulma engeller ortaya çıkabilir. Ayrıca, bir oturum açma gibi karşılık gelen hiçbir hesap adı ile güvenlik tanımlayıcıları için oluşur `SID` bir oturumun tanımlar.  
  
##  <a name="csid"></a>CSid::CSid  
 Oluşturucu.  
  
```
CSid() throw();
CSid(const SID& rhs) throw(...);
CSid(const CSid& rhs) throw(...);

CSid(
    const SID_IDENTIFIER_AUTHORITY& IdentifierAuthority,
    BYTE nSubAuthorityCount,
    ...) throw(...);

explicit CSid(
    LPCTSTR pszAccountName,
    LPCTSTR pszSystem = NULL) throw(...);

explicit CSid(
    const SID* pSid,
    LPCTSTR pszSystem = NULL) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `rhs`  
 Var olan `CSid` nesne veya `SID` (güvenlik tanımlayıcısı) yapısı.  
  
 *IdentifierAuthority*  
 Yetkilisi.  
  
 *nSubAuthorityCount*  
 Kimliğinin alt yetki sayısı.  
  
 `pszAccountName`  
 Hesap adı.  
  
 `pszSystem`  
 Sistem adı. Bu dize bir uzak bilgisayar adı olabilir. Bu dize NULL ise, yerel sistem yerine kullanılır.  
  
 `pSid`  
 Bir işaretçi bir `SID` yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturucu başlatır `CSid` nesne, bir iç veri üyesi ayarını *SidTypeInvalid*, ya da mevcut bir ayarları kopyalayarak `CSid`, `SID`, ya da mevcut hesap.  
  
 Başlatma başarısız olursa Oluşturucusu özel durum oluşturacak bir [CAtlException sınıfı](../../atl/reference/catlexception-class.md).  
  
##  <a name="dtor"></a>CSID:: ~ CSID  
 Yok Edicisi.  
  
```
virtual ~CSid() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yok Edicisi nesne tarafından alınan tüm kaynakları serbest bırakır.  
  
##  <a name="csidarray"></a>CSid::CSidArray  
 Bir dizi [CSID](../../atl/reference/csid-class.md) nesneleri.  
  
```
typedef CAtlArray<CSid> CSidArray;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu typedef bir ACL (erişim denetim listesi) güvenlik tanımlayıcıları almak için kullanılan dizi türünü belirtir. Bkz: [CAcl::GetAclEntries](../../atl/reference/cacl-class.md#getaclentries).  
  
##  <a name="domain"></a>CSid::Domain  
 İle ilişkili etki alanı adını döndürür `CSid` nesnesi.  
  
```
LPCTSTR Domain() const throw(...);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `LPCTSTR` etki alanına işaret ediyor.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, bir ad için belirtilen bulmayı dener `SID` (güvenlik tanımlayıcısı). Ayrıntılar için bkz: [LookupAccountSid](http://msdn.microsoft.com/library/windows/desktop/aa379166).  
  
 Hesap adı için `SID` bulunabilir, **etki alanı** etki alanı boş bir dize olarak döndürür. Bu durum ağ zaman aşımı bu yöntem adı bulma engeller ortaya çıkabilir. Ayrıca, bir oturum açma gibi karşılık gelen hiçbir hesap adı ile güvenlik tanımlayıcıları için oluşur `SID` bir oturumun tanımlar.  
  
##  <a name="equalprefix"></a>CSid::EqualPrefix  
 Testleri `SID` (güvenlik tanımlayıcısı) önekleri eşitlik için.  
  
```
bool EqualPrefix(const SID& rhs) const throw();
bool EqualPrefix(const CSid& rhs) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `rhs`  
 `SID` (Güvenlik tanımlayıcısı) yapısı veya `CSid` Karşılaştırılacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** başarılı, **false** hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [EqualPrefixSid](http://msdn.microsoft.com/library/windows/desktop/aa446621) daha fazla ayrıntı için Windows SDK.  
  
##  <a name="getlength"></a>CSid::GetLength  
 Uzunluğunu döndürür `CSid` nesnesi.  
  
```
UINT GetLength() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bayt cinsinden uzunluğu döndürür `CSid` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `CSid` yapısı geçerli değil, dönüş değeri tanımlanmamış. Çağırmadan önce `GetLength`, kullanın [CSid::IsValid](#isvalid) doğrulamak için üye işlevi `CSid` geçerlidir.  
  
> [!NOTE]
>  Hata ayıklama yapıları varsa, işlev ASSERT neden olacak altında `CSid` nesnesi geçerli değil.  
  
##  <a name="getpsid"></a>CSid::GetPSID  
 Bir işaretçi döndüren bir `SID` (güvenlik tanımlayıcısı) yapısı.  
  
```
const SID* GetPSID() const throw(...);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Adresini döndürür `CSid` nesne temel aldığı `SID` yapısı.  
  
##  <a name="getpsid_identifier_authority"></a>CSid::GetPSID_IDENTIFIER_AUTHORITY  
 Bir işaretçi döndürür **SID_IDENTIFIER_AUTHORITY** yapısı.  
  
```
const SID_IDENTIFIER_AUTHORITY* GetPSID_IDENTIFIER_AUTHORITY() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa adresini döndürür **SID_IDENTIFIER_AUTHORITY** yapısı. Dönüş değeri, başarısız olursa, tanımlanmamıştır. Hata oluşabilir `CSid` nesnesi geçerli değil, bu durumda [CSid::IsValid](#isvalid) yöntemi döndürür **false**. İşlev `GetLastError` genişletilmiş hata bilgileri için çağrılabilir.  
  
> [!NOTE]
>  Hata ayıklama yapıları varsa, işlev ASSERT neden olacak altında `CSid` nesnesi geçerli değil.  
  
##  <a name="getsubauthority"></a>CSid::GetSubAuthority  
 İçinde belirtilen bir kimliğinin alt yetki verir bir `SID` (güvenlik tanımlayıcısı) yapısı.  
  
```
DWORD GetSubAuthority(DWORD nSubAuthority) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *nSubAuthority*  
 Kimliğinin alt yetki.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tarafından başvurulan kimliğinin alt yetki verir *nSubAuthority.* Göreli bir tanımlayıcı (RID) kimliğinin alt yetki değerdir.  
  
### <a name="remarks"></a>Açıklamalar  
 *NSubAuthority* parametresi, yöntemin döndürecektir kimliğinin alt yetki dizi öğesi tanımlayan bir dizin değerini belirtir. Yöntemi bu değere doğrulama testi gerçekleştirir. Bir uygulamanın çağırabileceği [CSid::GetSubAuthorityCount](#getsubauthoritycount) kabul edilebilir değer aralığını bulmak için.  
  
> [!NOTE]
>  Hata ayıklama yapıları varsa, işlev ASSERT neden olacak altında `CSid` nesnesi geçerli değil.  
  
##  <a name="getsubauthoritycount"></a>CSid::GetSubAuthorityCount  
 Kimliğinin alt yetki sayımını döndürür.  
  
```
UCHAR GetSubAuthorityCount() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, dönüş değeri kimliğinin alt yetki sayı değil.  
  
 Yöntem başarısız olursa, dönüş değeri tanımlanmamıştır. Yöntem, başarısız `CSid` nesnesi geçersiz. Genişletilmiş hata bilgilerini için arama `GetLastError`.  
  
> [!NOTE]
>  Hata ayıklama yapıları varsa, işlev ASSERT neden olacak altında `CSid` nesnesi geçerli değil.  
  
##  <a name="isvalid"></a>CSid::IsValid  
 Testleri `CSid` geçerliliğini nesnesi.  
  
```
bool IsValid() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** varsa `CSid` nesne geçerli **false** değilse. Bu yöntem için genişletilmiş hata bilgi yok; çağırmayın `GetLastError`.  
  
### <a name="remarks"></a>Açıklamalar  
 `IsValid` Yöntemi doğrular `CSid` düzeltme numarası içinde bilinen bir aralıktaki olduğunu ve subauthorities sayısının en büyük değerinden olduğunu doğrulayarak nesnesi.  
  
##  <a name="loadaccount"></a>CSid::LoadAccount  
 Güncelleştirmeleri `CSid` verilen hesap adı ve etki alanı veya varolan bir SID (güvenlik tanımlayıcısı) yapısını nesnesi.  
  
```
bool LoadAccount(
    LPCTSTR pszAccountName,
    LPCTSTR pszSystem = NULL) throw(...);

bool LoadAccount(
    const SID* pSid,
    LPCTSTR pszSystem = NULL) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `pszAccountName`  
 Hesap adı.  
  
 `pszSystem`  
 Sistem adı. Bu dize bir uzak bilgisayar adı olabilir. Bu dize NULL ise, yerel sistem yerine kullanılır.  
  
 `pSid`  
 Bir işaretçi bir [SID](http://msdn.microsoft.com/library/windows/desktop/aa379594\(v=vs.85\).aspx) yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** başarılı, **false** hatasında. Genişletilmiş hata bilgilerini için arama `GetLastError`.  
  
### <a name="remarks"></a>Açıklamalar  
 `LoadAccount`bir güvenlik tanımlayıcısı için belirtilen ad bulmaya çalışır. Bkz: [LookupAccountSid](http://msdn.microsoft.com/library/windows/desktop/aa379166\(v=vs.85\).aspx) daha fazla ayrıntı için.  
  
##  <a name="operator_eq"></a>CSid::operator =  
 Atama işleci.  
  
```
CSid& operator= (const CSid& rhs) throw(...);  
CSid& operator= (const SID& rhs) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `rhs`  
 `SID` (Güvenlik tanımlayıcısı) veya `CSid` atamak için `CSid` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güncelleştirilmiş bir başvuru döndürür `CSid` nesnesi.  
  
##  <a name="operator_eq_eq"></a>CSid::operator ==  
 İki güvenlik tanımlayıcısı nesnenin eşitlik için test eder.  
  
```
bool operator==(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `lhs`  
 `SID` (Güvenlik tanımlayıcısı) veya `CSid` sol tarafında görünür == işleci.  
  
 `rhs`  
 `SID` (Güvenlik tanımlayıcısı) veya `CSid` sağ tarafında görünür == işleci.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** Aksi durumda güvenlik tanımlayıcısı eşitse, **false**.  
  
##  <a name="operator_neq"></a>CSid::operator! =  
 Eşitsizlik açısından iki güvenlik tanımlayıcısı nesneleri sınar.  
  
```
bool operator!=(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `lhs`  
 `SID` (Güvenlik tanımlayıcısı) veya `CSid` sol tarafında görünür! = işleci.  
  
 `rhs`  
 `SID` (Güvenlik tanımlayıcısı) veya `CSid` sağ tarafında görünür! = işleci.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** güvenlik tanımlayıcıları aksi eşit değilse **false**.  
  
##  <a name="operator_lt"></a>CSid::operator&lt;  
 Göreli iki güvenlik tanımlayıcısı nesneleri karşılaştırır.  
  
```
bool operator<(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `lhs`  
 `SID` (Güvenlik tanımlayıcısı) veya `CSid` sol tarafında görünür! = işleci.  
  
 `rhs`  
 `SID` (Güvenlik tanımlayıcısı) veya `CSid` sağ tarafında görünür! = işleci.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** varsa `lhs` olan değerinden `rhs`, aksi takdirde **false**.  
  
##  <a name="operator_lt__eq"></a>CSid::operator&lt;=  
 Göreli iki güvenlik tanımlayıcısı nesneleri karşılaştırır.  
  
```
bool operator<=(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `lhs`  
 `SID` (Güvenlik tanımlayıcısı) veya `CSid` sol tarafında görünür! = işleci.  
  
 `rhs`  
 `SID` (Güvenlik tanımlayıcısı) veya `CSid` sağ tarafında görünür! = işleci.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** varsa `lhs` küçük veya eşittir `rhs`, aksi takdirde **false**.  
  
##  <a name="operator_gt"></a>CSid::operator&gt;  
 Göreli iki güvenlik tanımlayıcısı nesneleri karşılaştırır.  
  
```
bool operator>(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `lhs`  
 `SID` (Güvenlik tanımlayıcısı) veya `CSid` sol tarafında görünür! = işleci.  
  
 `rhs`  
 `SID` (Güvenlik tanımlayıcısı) veya `CSid` sağ tarafında görünür! = işleci.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** varsa `lhs` değerinden daha büyük `rhs`, aksi takdirde **false**.  
  
##  <a name="operator_gt__eq"></a>CSid::operator&gt;=  
 Göreli iki güvenlik tanımlayıcısı nesneleri karşılaştırır.  
  
```
bool operator>=(
    const CSid& lhs,
    const CSid& rhs) throw());
```  
  
### <a name="parameters"></a>Parametreler  
 `lhs`  
 `SID` (Güvenlik tanımlayıcısı) veya `CSid` sol tarafında görünür! = işleci.  
  
 `rhs`  
 `SID` (Güvenlik tanımlayıcısı) veya `CSid` sağ tarafında görünür! = işleci.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** varsa `lhs` büyük veya eşit `rhs`, aksi takdirde **false**.  
  
##  <a name="operator_const_sid__star"></a>CSid::operator const SID *  
 Atamalar bir `CSid` gösteren bir işaretçi nesnesine bir `SID` (güvenlik tanımlayıcısı) yapısı.  
  
```  
operator const SID *() const throw(...);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Adresini döndürür `SID` yapısı.  
  
##  <a name="sid"></a>CSid::Sid  
 Döndürür `SID` dize olarak (güvenlik tanımlayıcısı) yapısı.  
  
```
LPCTSTR Sid() const throw(...);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `SID` yapısı görüntüleme, depolama ve iletim için uygun bir biçiminde bir dize olarak. Eşdeğer [ConvertSidToStringSid](http://msdn.microsoft.com/library/windows/desktop/aa376399), bu işlevi yalnızca Windows 2000 veya sonraki sürümlerde kullanılabilir olsa da ve önceki işletim sistemleri için benzetilmiş.  
  
##  <a name="sidnameuse"></a>CSid::SidNameUse  
 Durumu açıklamasını döndürür `CSid` nesnesi.  
  
```
SID_NAME_USE SidNameUse() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Durumunu açıklayan bir değeri saklayan veri üyesinin değerini döndürür `CSid` nesnesi.  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SidTypeUser|Bir kullanıcıyı gösteren `SID` (güvenlik tanımlayıcısı).|  
|SidTypeGroup|Bir grubu gösterir `SID`.|  
|SidTypeDomain|Bir etki alanını gösterir `SID`.|  
|SidTypeAlias|Bir diğer ad gösterir `SID`.|  
|SidTypeWellKnownGroup|Gösteren bir `SID` iyi bilinen bir grup için.|  
|SidTypeDeletedAccount|Gösteren bir `SID` silinmiş bir hesabı için.|  
|SidTypeInvalid|Geçersiz bir gösterir `SID`.|  
|SidTypeUnknown|Bilinmeyen gösterir `SID` türü.|  
|SidTypeComputer|Gösteren bir `SID` bir bilgisayar için.|  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı [CSid::LoadAccount](#loadaccount) güncelleştirmek için `CSid` nesne çağırmadan önce `SidNameUse` durumuna döndürmek için. `SidNameUse`nesnenin durumu değiştirmez (için arama tarafından **LookupAccountName** veya **LookupAccountSid**), ancak yalnızca geçerli durumunu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Güvenliği örneği](../../visual-cpp-samples.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)   
 [Güvenlik genel işlevler](../../atl/reference/security-global-functions.md)   
 [İşleçler](../../atl/reference/atl-operators.md)
