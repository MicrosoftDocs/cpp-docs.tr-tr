---
title: CSid Sınıfı
ms.date: 03/27/2019
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
helpviewer_keywords:
- CSid class
ms.assetid: be58b7ca-5958-49c3-a833-ca341aaaf753
ms.openlocfilehash: 414cf428cebe8105d90b3add93cc7f1e76927c2a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330924"
---
# <a name="csid-class"></a>CSid Sınıfı

Bu sınıf, bir `SID` (güvenlik tanımlayıcısı) yapısı için bir sarmalayıcıdır.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CSid
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

|Adı|Açıklama|
|----------|-----------------|
|[CSid::CsidArray](#csidarray)|Bir dizi `CSid` nesne.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CSid::csid](#csid)|Oluşturucu.|
|[CSid::~CSid](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CSid::Hesap Adı](#accountname)|`CSid` Nesneyle ilişkili hesabın adını verir.|
|[CSid::Domain](#domain)|Nesneyle ilişkili etki alanının `CSid` adını döndürür.|
|[CSid::EqualPrefix](#equalprefix)|Eşitlik `SID` için testler (güvenlik tanımlayıcısı) önekleri.|
|[CSid::GetLength](#getlength)|`CSid` Nesnenin uzunluğunu döndürür.|
|[CSid::GetPSID](#getpsid)|Bir işaretçiyi `SID` bir yapıya döndürür.|
|[CSid::GetPSID_IDENTIFIER_AUTHORITY](#getpsid_identifier_authority)|Yapıya bir `SID_IDENTIFIER_AUTHORITY` işaretçi döndürür.|
|[CSid::GetSubAuthority](#getsubauthority)|Bir `SID` yapıda belirli bir alt yetkisini döndürür.|
|[CSid::GetSubAuthorityCount](#getsubauthoritycount)|Alt yetki sayısını döndürür.|
|[CSid::Geçersiz](#isvalid)|Geçerlilik `CSid` için nesneyi sınar.|
|[CSid::LoadAccount](#loadaccount)|Hesap `CSid` adı ve etki alanı veya varolan `SID` bir yapı verilen nesneyi güncelleştirir.|
|[CSid::Sid](#sid)|Kimlik dizesini döndürür.|
|[CSid::SidnameUse](#sidnameuse)|`CSid` Nesnenin durumunun açıklamasını döndürür.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işleç =](#operator_eq)|Atama işleci.|
|[operatör const SID *](#operator_const_sid__star)|Bir `CSid` nesneyi bir `SID` yapıya işaretçiatar.|

### <a name="global-operators"></a>Küresel Operatörler

|||
|-|-|
|[işleç ==](#operator_eq_eq)|Eşitlik için iki güvenlik tanımlayıcı nesnesi sınar|
|[işleç !=](#operator_neq)|Eşitsizlik için iki güvenlik tanımlayıcı nesnesi sınar|
|[Işleç\<](#operator_lt)|İki güvenlik tanımlayıcı nesnesinin göreli değerini karşılaştırır.|
|[operatör >](#operator_gt)|İki güvenlik tanımlayıcı nesnesinin göreli değerini karşılaştırır.|
|[Işleç\<=](#operator_lt__eq)|İki güvenlik tanımlayıcı nesnesinin göreli değerini karşılaştırır.|
|[operatör >=](#operator_gt__eq)|İki güvenlik tanımlayıcı nesnesinin göreli değerini karşılaştırır.|

## <a name="remarks"></a>Açıklamalar

Yapı, `SID` kullanıcıları veya grupları benzersiz olarak tanımlamak için kullanılan değişken uzunlukta bir yapıdır.

Uygulamalar yapıyı `SID` doğrudan değiştirmemeli, bunun yerine bu sarıcı sınıfında sağlanan yöntemleri kullanmalıdır. Ayrıca bakınız [AtlGetOwnerSid](security-global-functions.md#atlgetownersid), [AtlSetGroupSid](security-global-functions.md#atlsetgroupsid), [AtlGetGroupSid](security-global-functions.md#atlgetgroupsid), ve [AtlSetOwnerSid](security-global-functions.md#atlsetownersid).

Windows'daki erişim denetimi modeline giriş için Windows SDK'daki [Access Denetimi'ne](/windows/win32/SecAuthZ/access-control) bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity.h

## <a name="csidaccountname"></a><a name="accountname"></a>CSid::Hesap Adı

`CSid` Nesneyle ilişkili hesabın adını verir.

```
LPCTSTR AccountName() const throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

LpCTSTR'yi hesabın adını gösteren döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, belirtilen `SID` (güvenlik tanımlayıcısı) için bir ad bulmaya çalışır. Tüm ayrıntılar için [Bkz. LookupAccountSid](/windows/win32/api/winbase/nf-winbase-lookupaccountsidw).

Hesap adı `SID` bulunamazsa, `AccountName` boş bir dize döndürür. Bir ağ zaman aşımı bu yöntemin adı bulmasını engellerse bu oluşabilir. Oturum açma oturumu gibi `SID` karşılık gelen hesap adı olmayan güvenlik tanımlayıcıları için de oluşur.

## <a name="csidcsid"></a><a name="csid"></a>CSid::csid

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

*Rhs*<br/>
Varolan `CSid` bir `SID` nesne veya (güvenlik tanımlayıcısı) yapısı.

*IdentifierAuthority*<br/>
Otorite.

*nSubAuthorityCount*<br/>
Alt yetki sayısı.

*pszAccountName*<br/>
Hesap adı.

*pszSystem*<br/>
Sistem adı. Bu dize uzak bir bilgisayarın adı olabilir. Bu dize NULL ise, bunun yerine yerel sistem kullanılır.

*pSid*<br/>
Bir yapıiçin `SID` bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Kurucu, *sidtypeInvalid*için bir iç veri üyesi ayarlayarak veya varolan bir , `CSid` `SID`veya varolan hesaptan ayarları kopyalayarak `CSid` nesneyi başlatılmasını sağlar.

Başlatma başarısız olursa, oluşturucu bir [CAtlException Sınıfı](../../atl/reference/catlexception-class.md)atar.

## <a name="csidcsid"></a><a name="dtor"></a>CSid::~CSid

Yıkıcı.

```
virtual ~CSid() throw();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı nesne tarafından edinilen tüm kaynakları serbest sağlar.

## <a name="csidcsidarray"></a><a name="csidarray"></a>CSid::CsidArray

CSid [CSid](../../atl/reference/csid-class.md) nesnelerin bir dizi.

```
typedef CAtlArray<CSid> CSidArray;
```

### <a name="remarks"></a>Açıklamalar

Bu typedef, güvenlik tanımlayıcılarını bir ACL'den (erişim denetim listesi) almak için kullanılabilecek dizi türünü belirtir. [Bkz. CAcl::GetAclEntries](../../atl/reference/cacl-class.md#getaclentries).

## <a name="csiddomain"></a><a name="domain"></a>CSid::Domain

Nesneyle ilişkili etki alanının `CSid` adını döndürür.

```
LPCTSTR Domain() const throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

İşaretlemayı `LPCTSTR` etki alanına döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, belirtilen `SID` (güvenlik tanımlayıcısı) için bir ad bulmaya çalışır. Tüm ayrıntılar için [Bkz. LookupAccountSid](/windows/win32/api/winbase/nf-winbase-lookupaccountsidw).

Hesap adı `SID` bulunamazsa, `Domain` etki alanını boş bir dize olarak döndürür. Bir ağ zaman aşımı bu yöntemin adı bulmasını engellerse bu oluşabilir. Oturum açma oturumu gibi `SID` karşılık gelen hesap adı olmayan güvenlik tanımlayıcıları için de oluşur.

## <a name="csidequalprefix"></a><a name="equalprefix"></a>CSid::EqualPrefix

Eşitlik `SID` için testler (güvenlik tanımlayıcısı) önekleri.

```
bool EqualPrefix(const SID& rhs) const throw();
bool EqualPrefix(const CSid& rhs) const throw();
```

### <a name="parameters"></a>Parametreler

*Rhs*<br/>
Karşılaştırılacak `SID` (güvenlik tanımlayıcısı) yapısı `CSid` veya nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK'daki [EqualPrefixSid'e](/windows/win32/api/securitybaseapi/nf-securitybaseapi-equalprefixsid) bakın.

## <a name="csidgetlength"></a><a name="getlength"></a>CSid::GetLength

`CSid` Nesnenin uzunluğunu döndürür.

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CSid` Nesnenin baytlarındaki uzunluğu döndürür.

### <a name="remarks"></a>Açıklamalar

`CSid` Yapı geçerli değilse, iade değeri tanımsız. Aramadan `GetLength`önce, geçerli olduğunu `CSid` doğrulamak için [CSid::IsValid](#isvalid) üye işlevini kullanın.

> [!NOTE]
> Hata ayıklama altında `CSid` işlev nesne geçerli değilse bir ASSERT neden olur oluşturur.

## <a name="csidgetpsid"></a><a name="getpsid"></a>CSid::GetPSID

İşaretçiyi (güvenlik tanımlayıcısı) yapısına `SID` döndürür.

```
const SID* GetPSID() const throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

`CSid` Nesnenin alt yapısının `SID` adresini döndürür.

## <a name="csidgetpsid_identifier_authority"></a><a name="getpsid_identifier_authority"></a>CSid::GetPSID_IDENTIFIER_AUTHORITY

Yapıya bir `SID_IDENTIFIER_AUTHORITY` işaretçi döndürür.

```
const SID_IDENTIFIER_AUTHORITY* GetPSID_IDENTIFIER_AUTHORITY() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, `SID_IDENTIFIER_AUTHORITY` yapının adresini döndürür. Başarısız olursa, iade değeri tanımsız. `CSid` Nesne geçerli değilse hata oluşabilir, bu durumda [CSid::IsValid](#isvalid) yöntemi FALSE döndürür. İşlev `GetLastError` genişletilmiş hata bilgileri için çağrılabilir.

> [!NOTE]
> Hata ayıklama altında `CSid` işlev nesne geçerli değilse bir ASSERT neden olur oluşturur.

## <a name="csidgetsubauthority"></a><a name="getsubauthority"></a>CSid::GetSubAuthority

(Güvenlik tanımlayıcısı) `SID` yapısında belirtilen bir alt yetkisini döndürür.

```
DWORD GetSubAuthority(DWORD nSubAuthority) const throw();
```

### <a name="parameters"></a>Parametreler

*nSubAuthority*<br/>
Alt otorite.

### <a name="return-value"></a>Dönüş Değeri

*nSubAuthority* tarafından başvurulan alt yetkisini verir. Alt yetkİ değeri göreli bir tanımlayıcıdır (RID).

### <a name="remarks"></a>Açıklamalar

*nSubAuthority* parametresi, yöntemin döndüreceği alt yetki dizisi öğesini tanımlayan bir dizin değeri belirtir. Yöntem, bu değer üzerinde hiçbir doğrulama sınaması gerçekleştirmez. Bir uygulama [CSid arayabilirsiniz::GetSubAuthorityCount](#getsubauthoritycount) kabul edilebilir değerlerin aralığını keşfetmek için.

> [!NOTE]
> Hata ayıklama altında `CSid` işlev nesne geçerli değilse bir ASSERT neden olur oluşturur.

## <a name="csidgetsubauthoritycount"></a><a name="getsubauthoritycount"></a>CSid::GetSubAuthorityCount

Alt yetki sayısını döndürür.

```
UCHAR GetSubAuthorityCount() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, iade değeri alt yetkisini saymaktır.

Yöntem başarısız olursa, iade değeri tanımsız. Nesne geçersizse `CSid` yöntem başarısız olur. Genişletilmiş hata bilgilerini almak `GetLastError`için .

> [!NOTE]
> Hata ayıklama altında `CSid` işlev nesne geçerli değilse bir ASSERT neden olur oluşturur.

## <a name="csidisvalid"></a><a name="isvalid"></a>CSid::Geçersiz

Geçerlilik `CSid` için nesneyi sınar.

```
bool IsValid() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CSid` Nesne geçerliyse TRUE'yu döndürür, değilse FALSE. Bu yöntem için genişletilmiş hata bilgisi yoktur; aramayın. `GetLastError`

### <a name="remarks"></a>Açıklamalar

Yöntem, `IsValid` düzeltme `CSid` numarasının bilinen bir aralıkiçinde olduğunu ve alt otorite sayısının en fazla olduğunu doğrulayarak nesneyi doğrular.

## <a name="csidloadaccount"></a><a name="loadaccount"></a>CSid::LoadAccount

Hesap `CSid` adı ve etki alanı verilen nesneyi veya varolan bir SID (güvenlik tanımlayıcısı) yapısını güncelleştirir.

```
bool LoadAccount(
    LPCTSTR pszAccountName,
    LPCTSTR pszSystem = NULL) throw(...);

bool LoadAccount(
    const SID* pSid,
    LPCTSTR pszSystem = NULL) throw(...);
```

### <a name="parameters"></a>Parametreler

*pszAccountName*<br/>
Hesap adı.

*pszSystem*<br/>
Sistem adı. Bu dize uzak bir bilgisayarın adı olabilir. Bu dize NULL ise, bunun yerine yerel sistem kullanılır.

*pSid*<br/>
[SID](/windows/win32/api/winnt/ns-winnt-sid) yapısına işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false. Genişletilmiş hata bilgilerini almak `GetLastError`için .

### <a name="remarks"></a>Açıklamalar

`LoadAccount`belirtilen ad için bir güvenlik tanımlayıcısı bulmaya çalışır. Daha fazla bilgi için [LookupAccountSid'e](/windows/win32/api/winbase/nf-winbase-lookupaccountsidw) bakın.

## <a name="csidoperator-"></a><a name="operator_eq"></a>CSid::operatör =

Atama işleci.

```
CSid& operator= (const CSid& rhs) throw(...);
CSid& operator= (const SID& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*Rhs*<br/>
(güvenlik `SID` tanımlayıcısı) veya `CSid` nesneye atamak `CSid` için.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CSid` nesneye bir başvuru verir.

## <a name="csidoperator-"></a><a name="operator_eq_eq"></a>CSid::işleç ==

Eşitlik için iki güvenlik tanımlayıcı nesnesi sınar.

```
bool operator==(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*Lhs*<br/>
`SID` == işlecinin sol tarafında `CSid` görünen (güvenlik tanımlayıcısı) veya.

*Rhs*<br/>
`SID` == işlecinin sağ tarafında `CSid` görünen (güvenlik tanımlayıcısı) veya.

### <a name="return-value"></a>Dönüş Değeri

Doğru güvenlik tanımlayıcıları eşit, aksi takdirde FALSE.

## <a name="csidoperator-"></a><a name="operator_neq"></a>CSid::operatör !=

Eşitsizlik için iki güvenlik tanımlayıcı nesnesi sınar.

```
bool operator!=(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*Lhs*<br/>
!= işlecinin sol tarafında görünen `SID` (güvenlik tanımlayıcısı) veya. `CSid`

*Rhs*<br/>
!= işlecinin sağ tarafında görünen `SID` (güvenlik tanımlayıcısı) veya. `CSid`

### <a name="return-value"></a>Dönüş Değeri

Doğru güvenlik tanımlayıcıları eşit değilse, aksi takdirde FALSE.

## <a name="csidoperator-lt"></a><a name="operator_lt"></a>CSid::operatör&lt;

İki güvenlik tanımlayıcı nesnesinin göreli değerini karşılaştırır.

```
bool operator<(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*Lhs*<br/>
!= işlecinin sol tarafında görünen `SID` (güvenlik tanımlayıcısı) veya. `CSid`

*Rhs*<br/>
!= işlecinin sağ tarafında görünen `SID` (güvenlik tanımlayıcısı) veya. `CSid`

### <a name="return-value"></a>Dönüş Değeri

DOĞRU *lhs* *rhs*daha az ise , aksi takdirde FALSE.

## <a name="csidoperator-lt"></a><a name="operator_lt__eq"></a>CSid::operatör&lt;=

İki güvenlik tanımlayıcı nesnesinin göreli değerini karşılaştırır.

```
bool operator<=(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*Lhs*<br/>
!= işlecinin sol tarafında görünen `SID` (güvenlik tanımlayıcısı) veya. `CSid`

*Rhs*<br/>
!= işlecinin sağ tarafında görünen `SID` (güvenlik tanımlayıcısı) veya. `CSid`

### <a name="return-value"></a>Dönüş Değeri

DOĞRU *lhs* daha az veya *rhs*eşit ise , aksi takdirde FALSE.

## <a name="csidoperator-gt"></a><a name="operator_gt"></a>CSid::operatör&gt;

İki güvenlik tanımlayıcı nesnesinin göreli değerini karşılaştırır.

```
bool operator>(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*Lhs*<br/>
!= işlecinin sol tarafında görünen `SID` (güvenlik tanımlayıcısı) veya. `CSid`

*Rhs*<br/>
!= işlecinin sağ tarafında görünen `SID` (güvenlik tanımlayıcısı) veya. `CSid`

### <a name="return-value"></a>Dönüş Değeri

DOĞRU *lhs* *rhs*daha büyükise , aksi takdirde FALSE.

## <a name="csidoperator-gt"></a><a name="operator_gt__eq"></a>CSid::operatör&gt;=

İki güvenlik tanımlayıcı nesnesinin göreli değerini karşılaştırır.

```
bool operator>=(
    const CSid& lhs,
    const CSid& rhs) throw());
```

### <a name="parameters"></a>Parametreler

*Lhs*<br/>
!= işlecinin sol tarafında görünen `SID` (güvenlik tanımlayıcısı) veya. `CSid`

*Rhs*<br/>
!= işlecinin sağ tarafında görünen `SID` (güvenlik tanımlayıcısı) veya. `CSid`

### <a name="return-value"></a>Dönüş Değeri

DOĞRU *lhs* daha büyük veya *rhs*eşitise , aksi takdirde FALSE.

## <a name="csidoperator-const-sid-"></a><a name="operator_const_sid__star"></a>CSid::operatör const SID\*

Bir `CSid` nesneyi işaretçiye `SID` (güvenlik tanımlayıcısı) bir yapıya atar.

```
operator const SID *() const throw(...);
```

### <a name="remarks"></a>Açıklamalar

`SID` Yapının adresini döndürür.

## <a name="csidsid"></a><a name="sid"></a>CSid::Sid

`SID` (Güvenlik tanımlayıcısı) yapısını dize olarak döndürür.

```
LPCTSTR Sid() const throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

Yapıyı `SID` görüntü, depolama veya iletim için uygun biçimde dize olarak döndürür. [ConvertSidToStringSid'e](/windows/win32/api/sddl/nf-sddl-convertsidtostringsidw)eşdeğerdir.

## <a name="csidsidnameuse"></a><a name="sidnameuse"></a>CSid::SidnameUse

`CSid` Nesnenin durumunun açıklamasını döndürür.

```
SID_NAME_USE SidNameUse() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CSid` Nesnenin durumunu açıklayan bir değer depolayan veri üyesinin değerini döndürür.

|Değer|Açıklama|
|-----------|-----------------|
|SidTypeUser|Kullanıcıyı `SID` (güvenlik tanımlayıcısı) gösterir.|
|SidTypeGroup|Bir grubu `SID`gösterir.|
|SidTypeDomain|Etki alanını `SID`gösterir.|
|SidTypeAlias|Takma ad `SID`gösterir.|
|SidTypeWellKnownGroup|Tanınmış `SID` bir grup için a gösterir.|
|SidTypeDeletedAccount|Silinen `SID` bir hesap için a gösterir.|
|SidTypeGeçersiz|Geçersiz `SID`bir durumu gösterir.|
|SidTypeUnknown|Bilinmeyen `SID` bir türü gösterir.|
|SidTypeComputer|Bir `SID` bilgisayar için a gösterir.|

### <a name="remarks"></a>Açıklamalar

[CSid'i arayın::Yükleme](#loadaccount) `CSid` Hesabı'nı `SidNameUse` arayamadan önce nesneyi güncelleştirmek için durumunu döndürün. `SidNameUse`nesnenin durumunu değiştirmez (çağırarak `LookupAccountName` veya `LookupAccountSid`), yalnızca geçerli durumu döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Güvenlik Örneği](../../overview/visual-cpp-samples.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)<br/>
[Güvenlik Genel İşlevleri](../../atl/reference/security-global-functions.md)<br/>
[İşleçler](../../atl/reference/atl-operators.md)
