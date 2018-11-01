---
title: CSid sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: 57edb46047021d0ede04164584e79748028e05b3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50465370"
---
# <a name="csid-class"></a>CSid sınıfı

Bu sınıf için bir sarmalayıcı olan bir `SID` (güvenlik kimliği) yapısı.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CSid
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|[CSid::CSidArray](#csidarray)|Bir dizi `CSid` nesneleri.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSid::CSid](#csid)|Oluşturucu.|
|[CSid::~CSid](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSid::AccountName](#accountname)|İle ilişkili hesap adını döndürür `CSid` nesne.|
|[CSid::Domain](#domain)|İlişkili etki alanı adını döndürür `CSid` nesne.|
|[CSid::EqualPrefix](#equalprefix)|Testleri `SID` eşitlik (güvenlik tanımlayıcısı) ön ekler.|
|[CSid::GetLength](#getlength)|Uzunluğunu döndürür `CSid` nesne.|
|[CSid::GetPSID](#getpsid)|Bir işaretçi döndüren bir `SID` yapısı.|
|[CSid::GetPSID_IDENTIFIER_AUTHORITY](#getpsid_identifier_authority)|Bir işaretçi döndürür `SID_IDENTIFIER_AUTHORITY` yapısı.|
|[CSid::GetSubAuthority](#getsubauthority)|İçinde belirtilen bir kimliğinin alt yetki döndürür bir `SID` yapısı.|
|[CSid::GetSubAuthorityCount](#getsubauthoritycount)|Kimliğinin alt yetki sayımını döndürür.|
|[CSid::IsValid](#isvalid)|Testleri `CSid` geçerliliğini nesne.|
|[CSid::LoadAccount](#loadaccount)|Güncelleştirmeleri `CSid` hesap adı ve etki alanı veya var olan bir nesne `SID` yapısı.|
|[CSid::Sid](#sid)|Kimlik dizesi döndürür.|
|[CSid::SidNameUse](#sidnameuse)|Durumu açıklamasını döndürür `CSid` nesne.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işleç =](#operator_eq)|Atama işleci.|
|[işleci const SID *](#operator_const_sid__star)|Yayınları bir `CSid` nesneye bir işaretçi bir `SID` yapısı.|

### <a name="global-operators"></a>Genel işleçler

|||
|-|-|
|[işleç ==](#operator_eq_eq)|İki güvenlik tanımlayıcısı nesne eşitliği sınar.|
|[işleç! =](#operator_neq)|Testler iki güvenlik tanımlayıcısı nesneleri için eşitsizlik|
|[İşleci \<](#operator_lt_)|İki güvenlik tanımlayıcısı nesneleri göreli değerini karşılaştırır.|
|[operator >](#operator_gt_)|İki güvenlik tanımlayıcısı nesneleri göreli değerini karşılaştırır.|
|[İşleci \<=](#operator_lt__eq)|İki güvenlik tanımlayıcısı nesneleri göreli değerini karşılaştırır.|
|[operator > =](#operator_gt__eq)|İki güvenlik tanımlayıcısı nesneleri göreli değerini karşılaştırır.|

## <a name="remarks"></a>Açıklamalar

`SID` Kullanıcıları veya grupları benzersiz şekilde tanımlamak için kullanılan bir değişken uzunluklu yapısı yapısıdır.

Uygulamaları değişiklik `SID` yapısı doğrudan, ancak bunun yerine bu sarmalayıcı sınıfı sağlanan yöntemleri kullanın. Ayrıca bkz: [AtlGetOwnerSid](security-global-functions.md#atlgetownersid), [AtlSetGroupSid](security-global-functions.md#atlsetgroupsid), [AtlGetGroupSid](security-global-functions.md#atlgetgroupsid), ve [AtlSetOwnerSid](security-global-functions.md#atlsetownersid).

Windows, erişim denetimi modeli için bir giriş için bkz [erişim denetimi](/windows/desktop/SecAuthZ/access-control) Windows SDK.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlsecurity.h

##  <a name="accountname"></a>  CSid::AccountName

İle ilişkili hesap adını döndürür `CSid` nesne.

```
LPCTSTR AccountName() const throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

Hesap adına işaret eden LPCTSTR döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem için belirtilen bir ad bulmayı dener `SID` (güvenlik tanımlayıcısı). Tüm Ayrıntılar için bkz. [LookupAccountSid](/windows/desktop/api/winbase/nf-winbase-lookupaccountsida).

Hesap adı yok, `SID` bulunabilir, `AccountName` boş bir dize döndürür. Bu durum ağ zaman aşımı bu yöntem adı bulmasını engeller ortaya çıkabilir. Oturum açma gibi karşılık gelen hiçbir hesap adıyla güvenlik tanımlayıcıları için de gerçekleşir `SID` oturum tanımlar.

##  <a name="csid"></a>  CSid::CSid

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

*Sol*<br/>
Mevcut bir `CSid` nesne veya `SID` (güvenlik kimliği) yapısı.

*IdentifierAuthority*<br/>
Yetkilisi.

*nSubAuthorityCount*<br/>
Kimliğinin alt yetki sayısı.

*pszAccountName*<br/>
Hesap adı.

*pszSystem*<br/>
Sistem adı. Bu dize bir uzak bilgisayar adı olabilir. Yerel Sistem, bu dize NULL ise, bunun yerine kullanılır.

*Psıd*<br/>
Bir işaretçi bir `SID` yapısı.

### <a name="remarks"></a>Açıklamalar

Oluşturucu başlatır `CSid` nesnesi, bir iç veri üyesi ayarını *SidTypeInvalid*, veya varolan bir ayarları kopyalayarak `CSid`, `SID`, ya da mevcut hesap.

Başlatma başarısız olursa Oluşturucu yaratır bir [CAtlException sınıfı](../../atl/reference/catlexception-class.md).

##  <a name="dtor"></a>  CSid::~CSid

Yıkıcı.

```
virtual ~CSid() throw();
```

### <a name="remarks"></a>Açıklamalar

Yok edici, nesne tarafından alınan tüm kaynakları serbest bırakır.

##  <a name="csidarray"></a>  CSid::CSidArray

Bir dizi [CSID](../../atl/reference/csid-class.md) nesneleri.

```
typedef CAtlArray<CSid> CSidArray;
```

### <a name="remarks"></a>Açıklamalar

Bu tür tanımı, güvenlik tanımlayıcıları bir ACL (erişim denetim listesi) almak için kullanılan bir dizi türü belirtir. Bkz: [CAcl::GetAclEntries](../../atl/reference/cacl-class.md#getaclentries).

##  <a name="domain"></a>  CSid::Domain

İlişkili etki alanı adını döndürür `CSid` nesne.

```
LPCTSTR Domain() const throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

Döndürür `LPCTSTR` etki alanına işaret eden.

### <a name="remarks"></a>Açıklamalar

Bu yöntem için belirtilen bir ad bulmayı dener `SID` (güvenlik tanımlayıcısı). Tüm Ayrıntılar için bkz. [LookupAccountSid](/windows/desktop/api/winbase/nf-winbase-lookupaccountsida).

Hesap adı yok, `SID` bulunabilir, `Domain` etki alanı boş bir dize olarak döndürür. Bu durum ağ zaman aşımı bu yöntem adı bulmasını engeller ortaya çıkabilir. Oturum açma gibi karşılık gelen hiçbir hesap adıyla güvenlik tanımlayıcıları için de gerçekleşir `SID` oturum tanımlar.

##  <a name="equalprefix"></a>  CSid::EqualPrefix

Testleri `SID` eşitlik (güvenlik tanımlayıcısı) ön ekler.

```
bool EqualPrefix(const SID& rhs) const throw();
bool EqualPrefix(const CSid& rhs) const throw();
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
`SID` (Güvenlik kimliği) yapısı veya `CSid` Karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

Bkz: [EqualPrefixSid](https://msdn.microsoft.com/library/windows/desktop/aa446621) daha fazla ayrıntı için Windows SDK.

##  <a name="getlength"></a>  CSid::GetLength

Uzunluğunu döndürür `CSid` nesne.

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bayt cinsinden uzunluğunu döndürür `CSid` nesne.

### <a name="remarks"></a>Açıklamalar

Varsa `CSid` yapısı geçerli değil, dönüş değeri tanımsızdır. Çağırmadan önce `GetLength`, kullanın [CSid::IsValid](#isvalid) doğrulamak için üye işlevi `CSid` geçerlidir.

> [!NOTE]
>  Hata ayıklama yapıları işlevi, bir onay neden altında `CSid` nesnesi geçerli değil.

##  <a name="getpsid"></a>  CSid::GetPSID

Bir işaretçi döndüren bir `SID` (güvenlik kimliği) yapısı.

```
const SID* GetPSID() const throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

Adresini döndürür `CSid` nesnesinin temel aldığı `SID` yapısı.

##  <a name="getpsid_identifier_authority"></a>  CSid::GetPSID_IDENTIFIER_AUTHORITY

Bir işaretçi döndürür `SID_IDENTIFIER_AUTHORITY` yapısı.

```
const SID_IDENTIFIER_AUTHORITY* GetPSID_IDENTIFIER_AUTHORITY() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa adresini döndürür `SID_IDENTIFIER_AUTHORITY` yapısı. Başarısız olursa, dönüş değeri tanımsızdır. Hata oluşabilir `CSid` nesnesi geçerli değil, bu durumda [CSid::IsValid](#isvalid) yöntem FALSE döndürür. İşlev `GetLastError` genişletilmiş hata bilgileri için çağrılabilir.

> [!NOTE]
>  Hata ayıklama yapıları işlevi, bir onay neden altında `CSid` nesnesi geçerli değil.

##  <a name="getsubauthority"></a>  CSid::GetSubAuthority

İçinde belirtilen bir kimliğinin alt yetki döndürür bir `SID` (güvenlik kimliği) yapısı.

```
DWORD GetSubAuthority(DWORD nSubAuthority) const throw();
```

### <a name="parameters"></a>Parametreler

*nSubAuthority*<br/>
Kimliğinin alt yetki.

### <a name="return-value"></a>Dönüş Değeri

Tarafından başvurulan kimliğinin alt yetki verir *nSubAuthority.* Göreli bir tanımlayıcı (RID) kimliğinin alt yetki değerdir.

### <a name="remarks"></a>Açıklamalar

*NSubAuthority* parametresi yöntemi döndürür kimliğinin alt yetki dizi öğesi tanımlayan bir dizin değerini belirtir. Yöntemi, bu değeri doğrulama testi gerçekleştirir. Bir uygulama çağırabilirsiniz [CSid::GetSubAuthorityCount](#getsubauthoritycount) kabul edilebilir değerler aralığı bulunacak.

> [!NOTE]
>  Hata ayıklama yapıları işlevi, bir onay neden altında `CSid` nesnesi geçerli değil.

##  <a name="getsubauthoritycount"></a>  CSid::GetSubAuthorityCount

Kimliğinin alt yetki sayımını döndürür.

```
UCHAR GetSubAuthorityCount() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, dönüş değeri kimliğinin alt yetki sayısıdır.

Yöntem başarısız olursa, dönüş değeri tanımsızdır. Yöntem, başarısız `CSid` nesnesi geçersiz. Genişletilmiş hata bilgilerini almak için arama `GetLastError`.

> [!NOTE]
>  Hata ayıklama yapıları işlevi, bir onay neden altında `CSid` nesnesi geçerli değil.

##  <a name="isvalid"></a>  CSid::IsValid

Testleri `CSid` geçerliliğini nesne.

```
bool IsValid() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Gerekirse TRUE döndürür `CSid` nesne geçerli, yanlış Aksi takdirde. Bu yöntem için genişletilmiş hata bilgi yok; çağırmayın `GetLastError`.

### <a name="remarks"></a>Açıklamalar

`IsValid` Yöntemi doğrular `CSid` düzeltme numarası bilinen bir aralıkta olduğundan ve subauthorities sayısı maksimum değerden küçük olduğunu doğrulayarak nesne.

##  <a name="loadaccount"></a>  CSid::LoadAccount

Güncelleştirmeleri `CSid` hesap adı ve etki alanı veya varolan bir SID (güvenlik kimliği) yapısı verilen nesne.

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
Sistem adı. Bu dize bir uzak bilgisayar adı olabilir. Yerel Sistem, bu dize NULL ise, bunun yerine kullanılır.

*Psıd*<br/>
Bir işaretçi bir [SID](/windows/desktop/api/winnt/ns-winnt-_sid) yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE. Genişletilmiş hata bilgilerini almak için arama `GetLastError`.

### <a name="remarks"></a>Açıklamalar

`LoadAccount` Belirtilen ad için bir güvenlik tanımlayıcısı bulmaya çalışır. Bkz: [LookupAccountSid](/windows/desktop/api/winbase/nf-winbase-lookupaccountsida) daha fazla ayrıntı için.

##  <a name="operator_eq"></a>  CSid::operator =

Atama işleci.

```
CSid& operator= (const CSid& rhs) throw(...);
CSid& operator= (const SID& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
`SID` (Güvenlik tanımlayıcısı) veya `CSid` atamak için `CSid` nesne.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş bir başvuru döndürür `CSid` nesne.

##  <a name="operator_eq_eq"></a>  CSid::operator ==

İki güvenlik tanımlayıcısı nesne eşitliği sınar.

```
bool operator==(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*lhs*<br/>
`SID` (Güvenlik tanımlayıcısı) veya `CSid` sol tarafında görünür == işleci.

*Sol*<br/>
`SID` (Güvenlik tanımlayıcısı) veya `CSid` sağ tarafında görünür == işleci.

### <a name="return-value"></a>Dönüş Değeri

Güvenlik tanımlayıcıları eşittir, aksi takdirde FALSE ise TRUE.

##  <a name="operator_neq"></a>  CSid::operator! =

İki güvenlik tanımlayıcısı nesneleri eşitsizliği sınar.

```
bool operator!=(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*lhs*<br/>
`SID` (Güvenlik tanımlayıcısı) veya `CSid` sol tarafında görünür! = işleci.

*Sol*<br/>
`SID` (Güvenlik tanımlayıcısı) veya `CSid` sağ tarafında görünür! = işleci.

### <a name="return-value"></a>Dönüş Değeri

Güvenlik tanımlayıcıları değildir, eşittir, aksi takdirde FALSE TRUE.

##  <a name="operator_lt"></a>  CSid::operator &lt;

İki güvenlik tanımlayıcısı nesneleri göreli değerini karşılaştırır.

```
bool operator<(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*lhs*<br/>
`SID` (Güvenlik tanımlayıcısı) veya `CSid` sol tarafında görünür! = işleci.

*Sol*<br/>
`SID` (Güvenlik tanımlayıcısı) veya `CSid` sağ tarafında görünür! = işleci.

### <a name="return-value"></a>Dönüş Değeri

TRUE ise *lhs* olduğu küçüktür *sol*, aksi durumda FALSE.

##  <a name="operator_lt__eq"></a>  CSid::operator &lt;=

İki güvenlik tanımlayıcısı nesneleri göreli değerini karşılaştırır.

```
bool operator<=(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*lhs*<br/>
`SID` (Güvenlik tanımlayıcısı) veya `CSid` sol tarafında görünür! = işleci.

*Sol*<br/>
`SID` (Güvenlik tanımlayıcısı) veya `CSid` sağ tarafında görünür! = işleci.

### <a name="return-value"></a>Dönüş Değeri

TRUE ise *lhs* küçüktür veya eşittir *sol*, aksi durumda FALSE.

##  <a name="operator_gt"></a>  CSid::operator &gt;

İki güvenlik tanımlayıcısı nesneleri göreli değerini karşılaştırır.

```
bool operator>(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*lhs*<br/>
`SID` (Güvenlik tanımlayıcısı) veya `CSid` sol tarafında görünür! = işleci.

*Sol*<br/>
`SID` (Güvenlik tanımlayıcısı) veya `CSid` sağ tarafında görünür! = işleci.

### <a name="return-value"></a>Dönüş Değeri

TRUE ise *lhs* büyüktür *sol*, aksi durumda FALSE.

##  <a name="operator_gt__eq"></a>  CSid::operator &gt;=

İki güvenlik tanımlayıcısı nesneleri göreli değerini karşılaştırır.

```
bool operator>=(
    const CSid& lhs,
    const CSid& rhs) throw());
```

### <a name="parameters"></a>Parametreler

*lhs*<br/>
`SID` (Güvenlik tanımlayıcısı) veya `CSid` sol tarafında görünür! = işleci.

*Sol*<br/>
`SID` (Güvenlik tanımlayıcısı) veya `CSid` sağ tarafında görünür! = işleci.

### <a name="return-value"></a>Dönüş Değeri

TRUE ise *lhs* büyüktür veya eşittir *sol*, aksi durumda FALSE.

##  <a name="operator_const_sid__star"></a>  CSid::operator const SID \*

Yayınları bir `CSid` nesneye bir işaretçi bir `SID` (güvenlik kimliği) yapısı.

```
operator const SID *() const throw(...);
```

### <a name="remarks"></a>Açıklamalar

Adresini döndürür `SID` yapısı.

##  <a name="sid"></a>  CSid::Sid

Döndürür `SID` (güvenlik kimliği) yapısı bir dize.

```
LPCTSTR Sid() const throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

Döndürür `SID` yapısı olarak görünen, depolama ve aktarım için uygun bir biçimde bir dizeye. Eşdeğer [ConvertSidToStringSid](/windows/desktop/api/sddl/nf-sddl-convertsidtostringsida).

##  <a name="sidnameuse"></a>  CSid::SidNameUse

Durumu açıklamasını döndürür `CSid` nesne.

```
SID_NAME_USE SidNameUse() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Durumunu açıklayan bir değer depolar veri üyesinin değerini döndürür `CSid` nesne.

|Değer|Açıklama|
|-----------|-----------------|
|SidTypeUser|Bir kullanıcıyı gösteren `SID` (güvenlik tanımlayıcısı).|
|SidTypeGroup|Bir grubu gösterir `SID`.|
|SidTypeDomain|Bir etki alanını gösteren `SID`.|
|SidTypeAlias|Bir diğer ad gösterir `SID`.|
|SidTypeWellKnownGroup|Belirten bir `SID` iyi bilinen bir grup için.|
|SidTypeDeletedAccount|Belirten bir `SID` silinen hesabı.|
|SidTypeInvalid|Geçersiz bir gösteren `SID`.|
|SidTypeUnknown|Bilinmeyen gösterir `SID` türü.|
|SidTypeComputer|Belirten bir `SID` bir bilgisayar için.|

### <a name="remarks"></a>Açıklamalar

Çağrı [CSid::LoadAccount](#loadaccount) güncelleştirilecek `CSid` çağırmadan önce nesne `SidNameUse` durumuna döndürmek için. `SidNameUse` Nesne durumunu değiştirmez (için çağırarak `LookupAccountName` veya `LookupAccountSid`), ancak yalnızca geçerli durumunu döndürür.

## <a name="see-also"></a>Ayrıca Bkz.

[Güvenliği örneği](../../visual-cpp-samples.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)<br/>
[Güvenlik Genel İşlevleri](../../atl/reference/security-global-functions.md)<br/>
[İşleçler](../../atl/reference/atl-operators.md)
