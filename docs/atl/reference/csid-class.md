---
description: 'Daha fazla bilgi edinin: CSID sınıfı'
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
ms.openlocfilehash: b0f5553f14d31a43c0cc581ef43b518fa612616d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140809"
---
# <a name="csid-class"></a>CSID sınıfı

Bu sınıf `SID` (güvenlik tanımlayıcısı) yapısına yönelik bir sarmalayıcı.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Syntax

```
class CSid
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|[CSID:: Csıdarray](#csidarray)|`CSid`Nesne dizisi.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSID:: CSID](#csid)|Oluşturucu.|
|[CSID:: ~ CSID](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSID:: AccountName](#accountname)|Nesneyle ilişkili hesabın adını döndürür `CSid` .|
|[CSID::D omain](#domain)|Nesneyle ilişkili etki alanının adını döndürür `CSid` .|
|[CSID:: EqualPrefix](#equalprefix)|`SID`Eşitlik için testler (güvenlik tanımlayıcısı) ön ekleri.|
|[CSID:: GetLength](#getlength)|Nesnenin uzunluğunu döndürür `CSid` .|
|[CSID:: Getpsıd](#getpsid)|Yapıya bir işaretçi döndürür `SID` .|
|[CSID:: GetPSID_IDENTIFIER_AUTHORITY](#getpsid_identifier_authority)|Yapıya bir işaretçi döndürür `SID_IDENTIFIER_AUTHORITY` .|
|[CSID:: Getalt yetki miktarı](#getsubauthority)|Bir yapıda belirtilen bir alt yetki değerini döndürür `SID` .|
|[CSID:: Getalt Uthoritycount](#getsubauthoritycount)|Alt yetki sayısını döndürür.|
|[CSID:: IsValid](#isvalid)|`CSid`Nesneyi geçerliliğini test eder.|
|[CSID:: LoadAccount](#loadaccount)|`CSid`Hesap adı ve etki alanı ya da var olan bir yapıyla belirtilen nesneyi güncelleştirir `SID` .|
|[CSID:: Sid](#sid)|KIMLIK dizesini döndürür.|
|[CSID:: SidNameUse](#sidnameuse)|Nesnenin durumunun açıklamasını döndürür `CSid` .|

### <a name="operators"></a>İşleçler

|Ad|Açıklama|
|-|-|
|[işleç =](#operator_eq)|Atama işleci.|
|[işleç const SID *](#operator_const_sid__star)|Bir `CSid` nesneyi bir yapıya işaretçiye yayınlar `SID` .|

### <a name="global-operators"></a>Genel Işleçler

|Ad|Açıklama|
|-|-|
|[işleç = =](#operator_eq_eq)|Eşitlik için iki güvenlik tanımlayıcısı nesnesini sınar|
|[işleç! =](#operator_neq)|Eşitsizlik için iki güvenlik tanımlayıcısı nesnesini sınar|
|[işlecinde \<](#operator_lt)|İki güvenlik tanımlayıcısı nesnesinin göreli değerini karşılaştırır.|
|[işleç >](#operator_gt)|İki güvenlik tanımlayıcısı nesnesinin göreli değerini karşılaştırır.|
|[işlecinde \<=](#operator_lt__eq)|İki güvenlik tanımlayıcısı nesnesinin göreli değerini karşılaştırır.|
|[işleç >=](#operator_gt__eq)|İki güvenlik tanımlayıcısı nesnesinin göreli değerini karşılaştırır.|

## <a name="remarks"></a>Açıklamalar

`SID`Yapı, kullanıcıları veya grupları benzersiz şekilde tanımlamak için kullanılan değişken uzunluklu bir yapıdır.

Uygulamalar yapıyı doğrudan değiştirmemelidir `SID` , bunun yerine bu sarmalayıcı sınıfında sunulan yöntemleri kullanır. Ayrıca bkz. [Atlgetownersıd](security-global-functions.md#atlgetownersid), [atlsetgroupsıd](security-global-functions.md#atlsetgroupsid), [Atlgetgroupsıd](security-global-functions.md#atlgetgroupsid)ve [atlsetownersıd](security-global-functions.md#atlsetownersid).

Windows 'daki erişim denetim modeline giriş için Windows SDK [Access Control](/windows/win32/SecAuthZ/access-control) bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity. h

## <a name="csidaccountname"></a><a name="accountname"></a> CSID:: AccountName

Nesneyle ilişkili hesabın adını döndürür `CSid` .

```
LPCTSTR AccountName() const throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

Hesabın adına işaret eden LPCTSTR değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, belirtilen `SID` (güvenlik tanımlayıcısı) için bir ad bulmaya çalışır. Tüm ayrıntılar için bkz. [LookupAccountSid](/windows/win32/api/winbase/nf-winbase-lookupaccountsidw).

İçin bir hesap adı `SID` bulunamazsa `AccountName` boş bir dize döndürür. Bir ağ zaman aşımı bu yöntemin adı bulmasını engelliyorsa bu durum oluşabilir. Aynı zamanda, `SID` oturum açma oturumunu tanımlayan bir gibi, karşılık gelen hesap adı olmayan güvenlik tanımlayıcıları için de gerçekleşir.

## <a name="csidcsid"></a><a name="csid"></a> CSID:: CSID

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
Varolan bir `CSid` nesne veya `SID` (güvenlik tanımlayıcısı) yapısı.

*Identifierauthority*<br/>
Yetkili.

*NALT yetki sayısı*<br/>
Alt yetki sayısı.

*pszAccountName*<br/>
Hesap adı.

*pszSystem*<br/>
Sistem adı. Bu dize, uzak bir bilgisayarın adı olabilir. Bu dize NULL ise, bunun yerine yerel sistem kullanılır.

*PSID*<br/>
Bir yapıya yönelik işaretçi `SID` .

### <a name="remarks"></a>Açıklamalar

Oluşturucu `CSid` nesneyi başlatır, bir iç veri üyesini *Sıdtypegeçersiz* olarak ayarlar veya ayarları mevcut `CSid` , ya da `SID` var olan bir hesaptan kopyalayarak.

Başlatma başarısız olursa, Oluşturucu bir [CAtlException Sınıfı](../../atl/reference/catlexception-class.md)oluşturur.

## <a name="csidcsid"></a><a name="dtor"></a> CSID:: ~ CSID

Yok edicisi.

```
virtual ~CSid() throw();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı, nesne tarafından alınan tüm kaynakları serbest bırakır.

## <a name="csidcsidarray"></a><a name="csidarray"></a> CSID:: Csıdarray

Bir [CSID](../../atl/reference/csid-class.md) nesneleri dizisi.

```
typedef CAtlArray<CSid> CSidArray;
```

### <a name="remarks"></a>Açıklamalar

Bu typedef, bir ACL 'den (erişim denetimi listesi) güvenlik tanımlayıcılarını almak için kullanılabilecek dizi türünü belirtir. Bkz. [CAcl:: Getaclendenemeler](../../atl/reference/cacl-class.md#getaclentries).

## <a name="csiddomain"></a><a name="domain"></a> CSID::D omain

Nesneyle ilişkili etki alanının adını döndürür `CSid` .

```
LPCTSTR Domain() const throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

`LPCTSTR`Etki alanına işaret eden bir değer döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, belirtilen `SID` (güvenlik tanımlayıcısı) için bir ad bulmaya çalışır. Tüm ayrıntılar için bkz. [LookupAccountSid](/windows/win32/api/winbase/nf-winbase-lookupaccountsidw).

İçin bir hesap adı `SID` bulunamazsa, `Domain` etki alanını boş bir dize olarak döndürür. Bir ağ zaman aşımı bu yöntemin adı bulmasını engelliyorsa bu durum oluşabilir. Aynı zamanda, `SID` oturum açma oturumunu tanımlayan bir gibi, karşılık gelen hesap adı olmayan güvenlik tanımlayıcıları için de gerçekleşir.

## <a name="csidequalprefix"></a><a name="equalprefix"></a> CSID:: EqualPrefix

`SID`Eşitlik için testler (güvenlik tanımlayıcısı) ön ekleri.

```
bool EqualPrefix(const SID& rhs) const throw();
bool EqualPrefix(const CSid& rhs) const throw();
```

### <a name="parameters"></a>Parametreler

*sağ taraftan*<br/>
`SID`Karşılaştırılacak (güvenlik tanımlayıcısı) yapısı veya `CSid` nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [EqualPrefixSid](/windows/win32/api/securitybaseapi/nf-securitybaseapi-equalprefixsid) Windows SDK.

## <a name="csidgetlength"></a><a name="getlength"></a> CSID:: GetLength

Nesnenin uzunluğunu döndürür `CSid` .

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Nesnenin bayt cinsinden uzunluğunu döndürür `CSid` .

### <a name="remarks"></a>Açıklamalar

`CSid`Yapı geçerli değilse, dönüş değeri tanımsızdır. Çağrılmadan önce `GetLength` , geçerli olduğunu doğrulamak Için [CSID:: IsValid](#isvalid) üye işlevini kullanın `CSid` .

> [!NOTE]
> Hata ayıklama Derlemeleriyle, nesne geçerli değilse işlev bir onaylama oluşmasına neden olur `CSid` .

## <a name="csidgetpsid"></a><a name="getpsid"></a> CSID:: Getpsıd

Bir `SID` (güvenlik tanımlayıcısı) yapısına yönelik bir işaretçi döndürür.

```
const SID* GetPSID() const throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

`CSid`Nesnenin temel yapısının adresini döndürür `SID` .

## <a name="csidgetpsid_identifier_authority"></a><a name="getpsid_identifier_authority"></a> CSID:: GetPSID_IDENTIFIER_AUTHORITY

Yapıya bir işaretçi döndürür `SID_IDENTIFIER_AUTHORITY` .

```
const SID_IDENTIFIER_AUTHORITY* GetPSID_IDENTIFIER_AUTHORITY() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa yapının adresini döndürür `SID_IDENTIFIER_AUTHORITY` . Başarısız olursa, dönüş değeri tanımsızdır. `CSid`Nesne geçerli değilse hata oluşabilir. Bu durumda, [CSID:: IsValid](#isvalid) yöntemi false değerini döndürür. İşlev, `GetLastError` genişletilmiş hata bilgileri için çağrılabilir.

> [!NOTE]
> Hata ayıklama Derlemeleriyle, nesne geçerli değilse işlev bir onaylama oluşmasına neden olur `CSid` .

## <a name="csidgetsubauthority"></a><a name="getsubauthority"></a> CSID:: Getalt yetki miktarı

(Güvenlik tanımlayıcısı) yapısında belirtilen bir alt yetki değerini döndürür `SID` .

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
> Hata ayıklama Derlemeleriyle, nesne geçerli değilse işlev bir onaylama oluşmasına neden olur `CSid` .

## <a name="csidgetsubauthoritycount"></a><a name="getsubauthoritycount"></a> CSID:: Getalt Uthoritycount

Alt yetki sayısını döndürür.

```
UCHAR GetSubAuthorityCount() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, dönüş değeri alt yetki sayısıdır.

Yöntem başarısız olursa, dönüş değeri tanımsızdır. Nesne geçersiz ise yöntem başarısız olur `CSid` . Genişletilmiş hata bilgilerini almak için çağrısı yapın `GetLastError` .

> [!NOTE]
> Hata ayıklama Derlemeleriyle, nesne geçerli değilse işlev bir onaylama oluşmasına neden olur `CSid` .

## <a name="csidisvalid"></a><a name="isvalid"></a> CSID:: IsValid

`CSid`Nesneyi geçerliliğini test eder.

```
bool IsValid() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CSid`Nesne GEÇERLIYSE true, DEĞILSE false döndürür. Bu yöntem için genişletilmiş hata bilgisi yok; ' i çağırmayın `GetLastError` .

### <a name="remarks"></a>Açıklamalar

`IsValid`Yöntemi, `CSid` Düzeltme numarasının bilinen bir Aralık içinde olduğunu ve alt uthoriler sayısının en büyük değerden küçük olduğunu doğrulayarak nesneyi doğrular.

## <a name="csidloadaccount"></a><a name="loadaccount"></a> CSID:: LoadAccount

`CSid`Hesap adı ve etki alanı veya var olan SID (güvenlik tanımlayıcısı) yapısı verilen nesneyi güncelleştirir.

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
[SID](/windows/win32/api/winnt/ns-winnt-sid) yapısına yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür. Genişletilmiş hata bilgilerini almak için çağrısı yapın `GetLastError` .

### <a name="remarks"></a>Açıklamalar

`LoadAccount` Belirtilen ad için bir güvenlik tanımlayıcısı bulmaya çalışır. Daha fazla ayrıntı için [LookupAccountSid](/windows/win32/api/winbase/nf-winbase-lookupaccountsidw) bölümüne bakın.

## <a name="csidoperator-"></a><a name="operator_eq"></a> CSID:: operator =

Atama işleci.

```
CSid& operator= (const CSid& rhs) throw(...);
CSid& operator= (const SID& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*sağ taraftan*<br/>
`SID`(Güvenlik tanımlayıcısı) veya `CSid` `CSid` nesnesine atama.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş nesneye bir başvuru döndürür `CSid` .

## <a name="csidoperator-"></a><a name="operator_eq_eq"></a> CSID:: operator = =

, Eşitlik için iki güvenlik tanımlayıcısı nesnesini sınar.

```
bool operator==(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*Point*<br/>
`SID`(Güvenlik tanımlayıcısı) ya da `CSid` = = işlecinin sol tarafında görünür.

*sağ taraftan*<br/>
`SID`(Güvenlik tanımlayıcısı) veya `CSid` = = işlecinin sağ tarafında görünür.

### <a name="return-value"></a>Dönüş Değeri

Güvenlik tanımlayıcıları eşitse TRUE, aksi takdirde FALSE.

## <a name="csidoperator-"></a><a name="operator_neq"></a> CSID:: operator! =

Eşitsizlik için iki güvenlik tanımlayıcısı nesnesini sınar.

```
bool operator!=(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*Point*<br/>
`SID`(Güvenlik tanımlayıcısı) veya `CSid` ! = işlecinin sol tarafında görünen.

*sağ taraftan*<br/>
`SID`(Güvenlik tanımlayıcısı) veya `CSid` ! = işlecinin sağ tarafında görünür.

### <a name="return-value"></a>Dönüş Değeri

Güvenlik tanımlayıcıları eşitse TRUE, aksi takdirde FALSE.

## <a name="csidoperator-lt"></a><a name="operator_lt"></a> CSID:: operator &lt;

İki güvenlik tanımlayıcısı nesnesinin göreli değerini karşılaştırır.

```
bool operator<(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*Point*<br/>
`SID`(Güvenlik tanımlayıcısı) veya `CSid` ! = işlecinin sol tarafında görünen.

*sağ taraftan*<br/>
`SID`(Güvenlik tanımlayıcısı) veya `CSid` ! = işlecinin sağ tarafında görünür.

### <a name="return-value"></a>Dönüş Değeri

*LHS* , *RHS*'den küçükse true, aksi takdirde false.

## <a name="csidoperator-lt"></a><a name="operator_lt__eq"></a> CSID:: operator &lt;=

İki güvenlik tanımlayıcısı nesnesinin göreli değerini karşılaştırır.

```
bool operator<=(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*Point*<br/>
`SID`(Güvenlik tanımlayıcısı) veya `CSid` ! = işlecinin sol tarafında görünen.

*sağ taraftan*<br/>
`SID`(Güvenlik tanımlayıcısı) veya `CSid` ! = işlecinin sağ tarafında görünür.

### <a name="return-value"></a>Dönüş Değeri

*LHS* , *RHS*'den küçükse veya eşitse true, aksi takdirde false.

## <a name="csidoperator-gt"></a><a name="operator_gt"></a> CSID:: operator &gt;

İki güvenlik tanımlayıcısı nesnesinin göreli değerini karşılaştırır.

```
bool operator>(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*Point*<br/>
`SID`(Güvenlik tanımlayıcısı) veya `CSid` ! = işlecinin sol tarafında görünen.

*sağ taraftan*<br/>
`SID`(Güvenlik tanımlayıcısı) veya `CSid` ! = işlecinin sağ tarafında görünür.

### <a name="return-value"></a>Dönüş Değeri

*LHS* , *RHS*'den büyükse true, aksi takdirde false.

## <a name="csidoperator-gt"></a><a name="operator_gt__eq"></a> CSID:: operator &gt;=

İki güvenlik tanımlayıcısı nesnesinin göreli değerini karşılaştırır.

```
bool operator>=(
    const CSid& lhs,
    const CSid& rhs) throw());
```

### <a name="parameters"></a>Parametreler

*Point*<br/>
`SID`(Güvenlik tanımlayıcısı) veya `CSid` ! = işlecinin sol tarafında görünen.

*sağ taraftan*<br/>
`SID`(Güvenlik tanımlayıcısı) veya `CSid` ! = işlecinin sağ tarafında görünür.

### <a name="return-value"></a>Dönüş Değeri

*LHS* , *RHS*'den büyükse veya eşitse true, aksi takdirde false.

## <a name="csidoperator-const-sid-"></a><a name="operator_const_sid__star"></a> CSID:: operator const SID \*

Bir `CSid` nesneyi `SID` (güvenlik tanımlayıcısı) yapısına bir işaretçiye yayınlar.

```
operator const SID *() const throw(...);
```

### <a name="remarks"></a>Açıklamalar

Yapının adresini döndürür `SID` .

## <a name="csidsid"></a><a name="sid"></a> CSID:: Sid

`SID`(Güvenlik tanımlayıcısı) yapısını bir dize olarak döndürür.

```
LPCTSTR Sid() const throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

`SID`Yapıyı, görüntü, depolama veya iletim için uygun bir biçimde bir dize olarak döndürür. [ConvertSidToStringSid](/windows/win32/api/sddl/nf-sddl-convertsidtostringsidw)ile eşdeğerdir.

## <a name="csidsidnameuse"></a><a name="sidnameuse"></a> CSID:: SidNameUse

Nesnenin durumunun açıklamasını döndürür `CSid` .

```
SID_NAME_USE SidNameUse() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Nesnenin durumunu açıklayan bir değer depolayan veri üyesinin değerini döndürür `CSid` .

|Değer|Açıklama|
|-----------|-----------------|
|Sıdtypeuser|Bir kullanıcıyı `SID` (güvenlik tanımlayıcısı) gösterir.|
|Sıdtypegroup|Bir grubu gösterir `SID` .|
|Sıdtypedomain|Bir etki alanını belirtir `SID` .|
|Sıdtypealias|Diğer adı gösterir `SID` .|
|Sıdtypewellknowngroup|`SID`İyi bilinen bir grup için bir belirtir.|
|Sıdtypedeletedaccount|Silinen bir `SID` hesap için bir belirtir.|
|Sıdtypegeçersiz|Geçersiz olduğunu gösterir `SID` .|
|Sıdtypeunknown|Bilinmeyen bir `SID` türü gösterir.|
|Sıdtypecomputer|Bir `SID` bilgisayar için belirtir.|

### <a name="remarks"></a>Açıklamalar

Durumunu döndürmek için çağrılmadan önce nesneyi güncelleştirmek üzere [CSID:: LoadAccount](#loadaccount) ' i çağırın `CSid` `SidNameUse` . `SidNameUse` nesnenin durumunu değiştirmez ( `LookupAccountName` veya ' a çağırarak `LookupAccountSid` ), ancak yalnızca geçerli durumu döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Güvenlik örneği](../../overview/visual-cpp-samples.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[Güvenlik Genel Işlevleri](../../atl/reference/security-global-functions.md)<br/>
[İşleçler](../../atl/reference/atl-operators.md)
