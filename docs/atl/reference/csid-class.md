---
title: CSID sınıfı
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
ms.openlocfilehash: fb496e3bd58d0fe134c37b240eb2698302c6aa64
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68915696"
---
# <a name="csid-class"></a>CSID sınıfı

Bu sınıf `SID` (güvenlik tanımlayıcısı) yapısına yönelik bir sarmalayıcı.

> [!IMPORTANT]
>  Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CSid
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|[CSID:: Csıdarray](#csidarray)|`CSid` Nesne dizisi.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSID:: CSID](#csid)|Oluşturucu.|
|[CSid::~CSid](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSID:: AccountName](#accountname)|`CSid` Nesneyle ilişkili hesabın adını döndürür.|
|[CSID::D omain](#domain)|`CSid` Nesneyle ilişkili etki alanının adını döndürür.|
|[CSID:: EqualPrefix](#equalprefix)|Eşitlik `SID` için testler (güvenlik tanımlayıcısı) ön ekleri.|
|[CSid::GetLength](#getlength)|`CSid` Nesnenin uzunluğunu döndürür.|
|[CSid::GetPSID](#getpsid)|`SID` Yapıya bir işaretçi döndürür.|
|[CSID:: GetPSID_IDENTIFIER_AUTHORITY](#getpsid_identifier_authority)|`SID_IDENTIFIER_AUTHORITY` Yapıya bir işaretçi döndürür.|
|[CSid::GetSubAuthority](#getsubauthority)|Bir `SID` yapıda belirtilen bir alt yetki değerini döndürür.|
|[CSid::GetSubAuthorityCount](#getsubauthoritycount)|Alt yetki sayısını döndürür.|
|[CSID:: IsValid](#isvalid)|`CSid` Nesneyi geçerliliğini test eder.|
|[CSID:: LoadAccount](#loadaccount)|Hesap adı ve etki alanı ya da var olan `SID` bir yapıyla belirtilen nesneyigüncelleştirir.`CSid`|
|[CSID:: Sid](#sid)|KIMLIK dizesini döndürür.|
|[CSID:: SidNameUse](#sidnameuse)|`CSid` Nesnenin durumunun açıklamasını döndürür.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işleç =](#operator_eq)|Atama işleci.|
|[işleç const SID *](#operator_const_sid__star)|Bir nesneyi bir `SID` yapıya işaretçiye yayınlar. `CSid`|

### <a name="global-operators"></a>Genel Işleçler

|||
|-|-|
|[işleç = =](#operator_eq_eq)|Eşitlik için iki güvenlik tanımlayıcısı nesnesini sınar|
|[işleç! =](#operator_neq)|Eşitsizlik için iki güvenlik tanımlayıcısı nesnesini sınar|
|[işlecinde\<](#operator_lt)|İki güvenlik tanımlayıcısı nesnesinin göreli değerini karşılaştırır.|
|[işleç >](#operator_gt)|İki güvenlik tanımlayıcısı nesnesinin göreli değerini karşılaştırır.|
|[işlecinde\<=](#operator_lt__eq)|İki güvenlik tanımlayıcısı nesnesinin göreli değerini karşılaştırır.|
|[işleç > =](#operator_gt__eq)|İki güvenlik tanımlayıcısı nesnesinin göreli değerini karşılaştırır.|

## <a name="remarks"></a>Açıklamalar

`SID` Yapı, kullanıcıları veya grupları benzersiz şekilde tanımlamak için kullanılan değişken uzunluklu bir yapıdır.

Uygulamalar `SID` yapıyı doğrudan değiştirmemelidir, bunun yerine bu sarmalayıcı sınıfında sunulan yöntemleri kullanır. Ayrıca bkz. [Atlgetownersıd](security-global-functions.md#atlgetownersid), [atlsetgroupsıd](security-global-functions.md#atlsetgroupsid), [Atlgetgroupsıd](security-global-functions.md#atlgetgroupsid)ve [atlsetownersıd](security-global-functions.md#atlsetownersid).

Windows 'daki erişim denetim modeline giriş için Windows SDK [Access Control](/windows/desktop/SecAuthZ/access-control) bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity. h

##  <a name="accountname"></a>CSID:: AccountName

`CSid` Nesneyle ilişkili hesabın adını döndürür.

```
LPCTSTR AccountName() const throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

Hesabın adına işaret eden LPCTSTR değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, belirtilen `SID` (güvenlik tanımlayıcısı) için bir ad bulmaya çalışır. Tüm ayrıntılar için bkz. [LookupAccountSid](/windows/desktop/api/winbase/nf-winbase-lookupaccountsida).

İçin `SID` bir hesap adı `AccountName` bulunamazsa boş bir dize döndürür. Bir ağ zaman aşımı bu yöntemin adı bulmasını engelliyorsa bu durum oluşabilir. Aynı zamanda, oturum açma oturumunu tanımlayan bir `SID` gibi, karşılık gelen hesap adı olmayan güvenlik tanımlayıcıları için de gerçekleşir.

##  <a name="csid"></a>CSID:: CSID

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

*sağ taraftan*<br/>
Varolan `CSid` bir nesne veya `SID` (güvenlik tanımlayıcısı) yapısı.

*Identifierauthority*<br/>
Yetkili.

*NALT yetki sayısı*<br/>
Alt yetki sayısı.

*pszAccountName*<br/>
Hesap adı.

*pszSystem*<br/>
Sistem adı. Bu dize, uzak bir bilgisayarın adı olabilir. Bu dize NULL ise, bunun yerine yerel sistem kullanılır.

*PSID*<br/>
Bir `SID` yapıya yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Oluşturucu `CSid` nesneyi başlatır, bir iç veri üyesini *sıdtypegeçersiz*olarak ayarlar veya ayarları mevcut `CSid`, `SID`ya da var olan bir hesaptan kopyalayarak.

Başlatma başarısız olursa, Oluşturucu bir [CAtlException Sınıfı](../../atl/reference/catlexception-class.md)oluşturur.

##  <a name="dtor"></a>  CSid::~CSid

Yok edicisi.

```
virtual ~CSid() throw();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı, nesne tarafından alınan tüm kaynakları serbest bırakır.

##  <a name="csidarray"></a>CSID:: Csıdarray

Bir [CSID](../../atl/reference/csid-class.md) nesneleri dizisi.

```
typedef CAtlArray<CSid> CSidArray;
```

### <a name="remarks"></a>Açıklamalar

Bu typedef, bir ACL 'den (erişim denetimi listesi) güvenlik tanımlayıcılarını almak için kullanılabilecek dizi türünü belirtir. Bkz. [CAcl:: Getaclendenemeler](../../atl/reference/cacl-class.md#getaclentries).

##  <a name="domain"></a>CSID::D omain

`CSid` Nesneyle ilişkili etki alanının adını döndürür.

```
LPCTSTR Domain() const throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

Etki alanına `LPCTSTR` işaret eden bir değer döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, belirtilen `SID` (güvenlik tanımlayıcısı) için bir ad bulmaya çalışır. Tüm ayrıntılar için bkz. [LookupAccountSid](/windows/desktop/api/winbase/nf-winbase-lookupaccountsida).

İçin `SID` bir hesap adı bulunamazsa, `Domain` etki alanını boş bir dize olarak döndürür. Bir ağ zaman aşımı bu yöntemin adı bulmasını engelliyorsa bu durum oluşabilir. Aynı zamanda, oturum açma oturumunu tanımlayan bir `SID` gibi, karşılık gelen hesap adı olmayan güvenlik tanımlayıcıları için de gerçekleşir.

##  <a name="equalprefix"></a>CSID:: EqualPrefix

Eşitlik `SID` için testler (güvenlik tanımlayıcısı) ön ekleri.

```
bool EqualPrefix(const SID& rhs) const throw();
bool EqualPrefix(const CSid& rhs) const throw();
```

### <a name="parameters"></a>Parametreler

*sağ taraftan*<br/>
Karşılaştırılacak (güvenlik tanımlayıcısı) yapısı veya `CSid` nesne. `SID`

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [EqualPrefixSid](/windows/desktop/api/securitybaseapi/nf-securitybaseapi-equalprefixsid) Windows SDK.

##  <a name="getlength"></a>CSID:: GetLength

`CSid` Nesnenin uzunluğunu döndürür.

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CSid` Nesnenin bayt cinsinden uzunluğunu döndürür.

### <a name="remarks"></a>Açıklamalar

`CSid` Yapı geçerli değilse, dönüş değeri tanımsızdır. Çağrılmadan `GetLength`önce, geçerli olduğunu doğrulamak `CSid` için [CSID:: IsValid](#isvalid) üye işlevini kullanın.

> [!NOTE]
>  Hata ayıklama Derlemeleriyle, `CSid` nesne geçerli değilse işlev bir onaylama oluşmasına neden olur.

##  <a name="getpsid"></a>CSID:: Getpsıd

Bir `SID` (güvenlik tanımlayıcısı) yapısına yönelik bir işaretçi döndürür.

```
const SID* GetPSID() const throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

`CSid` Nesnenin temel`SID` yapısının adresini döndürür.

##  <a name="getpsid_identifier_authority"></a>CSID:: GetPSID_IDENTIFIER_AUTHORITY

`SID_IDENTIFIER_AUTHORITY` Yapıya bir işaretçi döndürür.

```
const SID_IDENTIFIER_AUTHORITY* GetPSID_IDENTIFIER_AUTHORITY() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa `SID_IDENTIFIER_AUTHORITY` yapının adresini döndürür. Başarısız olursa, dönüş değeri tanımsızdır. `CSid` Nesne geçerli değilse hata oluşabilir. Bu durumda, [CSID:: IsValid](#isvalid) yöntemi false değerini döndürür. İşlev `GetLastError` , genişletilmiş hata bilgileri için çağrılabilir.

> [!NOTE]
>  Hata ayıklama Derlemeleriyle, `CSid` nesne geçerli değilse işlev bir onaylama oluşmasına neden olur.

##  <a name="getsubauthority"></a>CSID:: Getalt yetki miktarı

`SID` (Güvenlik tanımlayıcısı) yapısında belirtilen bir alt yetki değerini döndürür.

```
DWORD GetSubAuthority(DWORD nSubAuthority) const throw();
```

### <a name="parameters"></a>Parametreler

*NALT yetki miktarı*<br/>
Alt yetki miktarı.

### <a name="return-value"></a>Dönüş Değeri

*NALT yetki* sahibi tarafından başvurulan alt yetki değerini döndürür. Alt yetki değeri, bir göreli tanımlayıcı (RID) değeridir.

### <a name="remarks"></a>Açıklamalar

*NALT* kimlik belirleme parametresi, yöntemin döndürdüğü alt yetki dizisi öğesini tanımlayan bir dizin değeri belirtir. Yöntemi bu değerde doğrulama testi gerçekleştirmesiz. Bir uygulama, kabul edilebilir değerlerin aralığını saptamak için [CSID:: Getalt Uthoritycount](#getsubauthoritycount) ' i çağırabilir.

> [!NOTE]
>  Hata ayıklama Derlemeleriyle, `CSid` nesne geçerli değilse işlev bir onaylama oluşmasına neden olur.

##  <a name="getsubauthoritycount"></a>  CSid::GetSubAuthorityCount

Alt yetki sayısını döndürür.

```
UCHAR GetSubAuthorityCount() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, dönüş değeri alt yetki sayısıdır.

Yöntem başarısız olursa, dönüş değeri tanımsızdır. `CSid` Nesne geçersiz ise yöntem başarısız olur. Genişletilmiş hata bilgilerini almak için çağrısı `GetLastError`yapın.

> [!NOTE]
>  Hata ayıklama Derlemeleriyle, `CSid` nesne geçerli değilse işlev bir onaylama oluşmasına neden olur.

##  <a name="isvalid"></a>CSID:: IsValid

`CSid` Nesneyi geçerliliğini test eder.

```
bool IsValid() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CSid` Nesne geçerliyse true, değilse false döndürür. Bu yöntem için genişletilmiş hata bilgisi yok; ' i çağırmayın `GetLastError`.

### <a name="remarks"></a>Açıklamalar

Yöntemi, düzeltme numarasının `CSid` bilinen bir Aralık içinde olduğunu ve alt uthoriler sayısının en büyük değerden küçük olduğunu doğrulayarak nesneyi doğrular. `IsValid`

##  <a name="loadaccount"></a>CSID:: LoadAccount

Hesap adı ve etki alanı veya var olan SID (güvenlik tanımlayıcısı) yapısı verilen nesneyigüncelleştirir.`CSid`

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
Sistem adı. Bu dize, uzak bir bilgisayarın adı olabilir. Bu dize NULL ise, bunun yerine yerel sistem kullanılır.

*PSID*<br/>
[SID](/windows/desktop/api/winnt/ns-winnt-sid) yapısına yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür. Genişletilmiş hata bilgilerini almak için çağrısı `GetLastError`yapın.

### <a name="remarks"></a>Açıklamalar

`LoadAccount`Belirtilen ad için bir güvenlik tanımlayıcısı bulmaya çalışır. Daha fazla ayrıntı için [LookupAccountSid](/windows/desktop/api/winbase/nf-winbase-lookupaccountsida) bölümüne bakın.

##  <a name="operator_eq"></a>CSID:: operator =

Atama işleci.

```
CSid& operator= (const CSid& rhs) throw(...);
CSid& operator= (const SID& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*sağ taraftan*<br/>
(Güvenlik tanımlayıcısı) veya `CSid` `CSid` nesnesine atama. `SID`

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CSid` nesneye bir başvuru döndürür.

##  <a name="operator_eq_eq"></a>CSID:: operator = =

, Eşitlik için iki güvenlik tanımlayıcısı nesnesini sınar.

```
bool operator==(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*Point*<br/>
(Güvenlik tanımlayıcısı) ya `CSid` da = = işlecinin sol tarafında görünür. `SID`

*sağ taraftan*<br/>
(Güvenlik tanımlayıcısı) veya `CSid` = = işlecinin sağ tarafında görünür. `SID`

### <a name="return-value"></a>Dönüş Değeri

Güvenlik tanımlayıcıları eşitse TRUE, aksi takdirde FALSE.

##  <a name="operator_neq"></a>CSID:: operator! =

Eşitsizlik için iki güvenlik tanımlayıcısı nesnesini sınar.

```
bool operator!=(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*Point*<br/>
(Güvenlik tanımlayıcısı) veya `CSid` ! = işlecinin sol tarafında görünen. `SID`

*sağ taraftan*<br/>
(Güvenlik tanımlayıcısı) veya `CSid` ! = işlecinin sağ tarafında görünür. `SID`

### <a name="return-value"></a>Dönüş Değeri

Güvenlik tanımlayıcıları eşitse TRUE, aksi takdirde FALSE.

##  <a name="operator_lt"></a>CSID:: operator&lt;

İki güvenlik tanımlayıcısı nesnesinin göreli değerini karşılaştırır.

```
bool operator<(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*Point*<br/>
(Güvenlik tanımlayıcısı) veya `CSid` ! = işlecinin sol tarafında görünen. `SID`

*sağ taraftan*<br/>
(Güvenlik tanımlayıcısı) veya `CSid` ! = işlecinin sağ tarafında görünür. `SID`

### <a name="return-value"></a>Dönüş Değeri

*LHS* , *RHS*'den küçükse true, aksi takdirde false.

##  <a name="operator_lt__eq"></a>CSID:: operator&lt;=

İki güvenlik tanımlayıcısı nesnesinin göreli değerini karşılaştırır.

```
bool operator<=(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*Point*<br/>
(Güvenlik tanımlayıcısı) veya `CSid` ! = işlecinin sol tarafında görünen. `SID`

*sağ taraftan*<br/>
(Güvenlik tanımlayıcısı) veya `CSid` ! = işlecinin sağ tarafında görünür. `SID`

### <a name="return-value"></a>Dönüş Değeri

*LHS* , *RHS*'den küçükse veya eşitse true, aksi takdirde false.

##  <a name="operator_gt"></a>CSID:: operator&gt;

İki güvenlik tanımlayıcısı nesnesinin göreli değerini karşılaştırır.

```
bool operator>(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*Point*<br/>
(Güvenlik tanımlayıcısı) veya `CSid` ! = işlecinin sol tarafında görünen. `SID`

*sağ taraftan*<br/>
(Güvenlik tanımlayıcısı) veya `CSid` ! = işlecinin sağ tarafında görünür. `SID`

### <a name="return-value"></a>Dönüş Değeri

*LHS* , *RHS*'den büyükse true, aksi takdirde false.

##  <a name="operator_gt__eq"></a>CSID:: operator&gt;=

İki güvenlik tanımlayıcısı nesnesinin göreli değerini karşılaştırır.

```
bool operator>=(
    const CSid& lhs,
    const CSid& rhs) throw());
```

### <a name="parameters"></a>Parametreler

*Point*<br/>
(Güvenlik tanımlayıcısı) veya `CSid` ! = işlecinin sol tarafında görünen. `SID`

*sağ taraftan*<br/>
(Güvenlik tanımlayıcısı) veya `CSid` ! = işlecinin sağ tarafında görünür. `SID`

### <a name="return-value"></a>Dönüş Değeri

*LHS* , *RHS*'den büyükse veya eşitse true, aksi takdirde false.

##  <a name="operator_const_sid__star"></a>CSID:: operator const SID\*

`CSid` Bir nesneyi `SID` (güvenlik tanımlayıcısı) yapısına bir işaretçiye yayınlar.

```
operator const SID *() const throw(...);
```

### <a name="remarks"></a>Açıklamalar

`SID` Yapının adresini döndürür.

##  <a name="sid"></a>CSID:: Sid

`SID` (Güvenlik tanımlayıcısı) yapısını bir dize olarak döndürür.

```
LPCTSTR Sid() const throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

`SID` Yapıyı, görüntü, depolama veya iletim için uygun bir biçimde bir dize olarak döndürür. [ConvertSidToStringSid](/windows/desktop/api/sddl/nf-sddl-convertsidtostringsida)ile eşdeğerdir.

##  <a name="sidnameuse"></a>CSID:: SidNameUse

`CSid` Nesnenin durumunun açıklamasını döndürür.

```
SID_NAME_USE SidNameUse() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CSid` Nesnenin durumunu açıklayan bir değer depolayan veri üyesinin değerini döndürür.

|Değer|Açıklama|
|-----------|-----------------|
|SidTypeUser|Bir kullanıcıyı `SID` (güvenlik tanımlayıcısı) gösterir.|
|SidTypeGroup|Bir grubu `SID`gösterir.|
|SidTypeDomain|Bir etki alanını `SID`belirtir.|
|Sıdtypealias|Diğer adı `SID`gösterir.|
|SidTypeWellKnownGroup|İyi bilinen `SID` bir grup için bir belirtir.|
|Sıdtypedeletedaccount|Silinen bir `SID` hesap için bir belirtir.|
|Sıdtypegeçersiz|Geçersiz `SID`olduğunu gösterir.|
|SidTypeUnknown|Bilinmeyen `SID` bir türü gösterir.|
|SidTypeComputer|Bir bilgisayar `SID` için belirtir.|

### <a name="remarks"></a>Açıklamalar

Durumunu döndürmek için çağrılmadan `SidNameUse` önce `CSid` nesneyi güncelleştirmek üzere [CSID:: LoadAccount](#loadaccount) ' i çağırın. `SidNameUse`nesnenin durumunu değiştirmez ( `LookupAccountName` veya `LookupAccountSid`' a çağırarak), ancak yalnızca geçerli durumu döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Güvenlik örneği](../../overview/visual-cpp-samples.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[Güvenlik Genel İşlevleri](../../atl/reference/security-global-functions.md)<br/>
[İşleçler](../../atl/reference/atl-operators.md)
