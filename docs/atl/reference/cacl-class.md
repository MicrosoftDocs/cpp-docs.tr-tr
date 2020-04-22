---
title: CAcl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAcl
- ATLSECURITY/ATL::CAcl
- ATLSECURITY/ATL::CAcl::CAccessMaskArray
- ATLSECURITY/ATL::CAcl::CAceFlagArray
- ATLSECURITY/ATL::CAcl::CAceTypeArray
- ATLSECURITY/ATL::CAcl::CAcl
- ATLSECURITY/ATL::CAcl::GetAceCount
- ATLSECURITY/ATL::CAcl::GetAclEntries
- ATLSECURITY/ATL::CAcl::GetAclEntry
- ATLSECURITY/ATL::CAcl::GetLength
- ATLSECURITY/ATL::CAcl::GetPACL
- ATLSECURITY/ATL::CAcl::IsEmpty
- ATLSECURITY/ATL::CAcl::IsNull
- ATLSECURITY/ATL::CAcl::RemoveAce
- ATLSECURITY/ATL::CAcl::RemoveAces
- ATLSECURITY/ATL::CAcl::SetEmpty
- ATLSECURITY/ATL::CAcl::SetNull
helpviewer_keywords:
- CAcl class
ms.assetid: 20bcb9af-dc1c-4737-b923-3864776680d6
ms.openlocfilehash: 458f7cd50462a145d005f3f81d87cc06fc7e01b1
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748779"
---
# <a name="cacl-class"></a>CAcl Sınıfı

Bu sınıf, (erişim `ACL` denetim listesi) yapısı için bir sarıcıdır.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CAcl
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

|Adı|Açıklama|
|----------|-----------------|
|[CAcl::CAccessMaskArray](#caccessmaskarray)|Bir dizi ACCESS_MASKs.|
|[CAcl::CAceFlagArray](#caceflagarray)|Bir dizi BYT.|
|[CAcl::CAceTypeArray](#cacetypearray)|Bir dizi BYT.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAcl::CAcl](#cacl)|Oluşturucu.|
|[CAcl::~CAcl](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAcl::GetAceCount](#getacecount)|Erişim denetimi girişi (ACE) nesnelerinin sayısını verir.|
|[CAcl::GetAclEntries](#getaclentries)|Erişim denetim listesi (ACL) girişlerini `CAcl` nesneden alır.|
|[CAcl::GetAclEntry](#getaclentry)|Bir `CAcl` nesnedeki girişle ilgili tüm bilgileri alır.|
|[CAcl::GetLength](#getlength)|ACL uzunluğunu verir.|
|[CAcl::GetPACL](#getpacl)|PACL (işaretçi bir ACL için) döndürür.|
|[CAcl::Boş](#isempty)|Girişler `CAcl` için nesneyi sınar.|
|[CAcl::IsNull](#isnull)|`CAcl` Nesnenin durumunu döndürür.|
|[CAcl::RemoveAce](#removeace)|`CAcl` Nesneden belirli bir ACE (erişim denetimi girişi) kaldırır.|
|[CAcl::Aces kaldırma](#removeaces)|Verilen `CAcl` `CSid`ler için geçerli olan tüm ACE'leri (erişim denetimi girişleri) kaldırır.|
|[CAcl::SetEmpty](#setempty)|Nesneyi `CAcl` boş olarak işaretler.|
|[CAcl::SetNull](#setnull)|Nesneyi `CAcl` NULL olarak işaretler.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CAcl::operatör const ACL *](#operator_const_acl__star)|Bir `CAcl` nesneyi bir `ACL` yapıya atar.|
|[CAcl::operatör =](#operator_eq)|Atama işleci.|

## <a name="remarks"></a>Açıklamalar

Yapı, `ACL` bir ACL (erişim denetim listesi) üstbilgisidir. ACL, sıfır veya daha fazla [ACE'nin](/windows/win32/SecAuthZ/access-control-entries) (erişim denetimi girişleri) sıralı bir listesini içerir. Bir ACL'deki tek tek ACE'ler 0'dan *n-1'e*numaralandırılır, *burada n,* ACL'deki ACE sayısıdır. Bir ACL düzenlerken, bir uygulama dizin tarafından ACL içinde bir erişim denetimi girişi (ACE) anlamına gelir.

İki ACL türü vardır:

- Isteğe bağlı

- Sistem

İhtiyari ACL, bir nesnenin sahibi veya nesneye erişim izni WRITE_DAC verilen herkes tarafından denetlenir. Belirli kullanıcıların ve grupların bir nesneye erişebileceği erişimi belirtir. Örneğin, bir dosyanın sahibi, hangi kullanıcıların ve grupların dosyaya erişebileceğini ve erişemeyeceğini denetlemek için isteğe bağlı bir ACL kullanabilir.

Bir nesne, sistem yöneticisi tarafından denetlenen bir sistem ACL şeklinde, onunla ilişkili sistem düzeyinde güvenlik bilgilerine de sahip olabilir. Sistem ACL, sistem yöneticisinin bir nesneye erişim sağlama girişimlerini denetlemesine izin verebilir.

Daha fazla bilgi için Windows SDK'daki [ACL](/windows/win32/SecAuthZ/access-control-lists) tartışmasına bakın.

Windows'daki erişim denetimi modeline giriş için Windows SDK'daki [Access Denetimi'ne](/windows/win32/SecAuthZ/access-control) bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity.h

## <a name="caclcaccessmaskarray"></a><a name="caccessmaskarray"></a>CAcl::CAccessMaskArray

Bir dizi ACCESS_MASK nesnesi.

```
typedef CAtlArray<ACCESS_MASK> CAccessMaskArray;
```

### <a name="remarks"></a>Açıklamalar

Bu typedef, erişim denetimi girişlerinde (ACE) kullanılan erişim haklarını depolamak için kullanılabilecek dizi türünü belirtir.

## <a name="caclcaceflagarray"></a><a name="caceflagarray"></a>CAcl::CAceFlagArray

Bir dizi BYT.

```
typedef CAtlArray<BYTE> CAceFlagArray;
```

### <a name="remarks"></a>Açıklamalar

Bu typedef, erişim denetimi girişini (ACE) türüne özgü denetim bayraklarını tanımlamak için kullanılan dizi türünü belirtir. Olası bayrakların tam listesi için [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) tanımına bakın.

## <a name="caclcacetypearray"></a><a name="cacetypearray"></a>CAcl::CAceTypeArray

Bir dizi BYT.

```
typedef CAtlArray<BYTE> CAceTypeArray;
```

### <a name="remarks"></a>Açıklamalar

Bu typedef, ACCESS_ALLOWED_ACE_TYPE veya ACCESS_DENIED_ACE_TYPE gibi erişim denetimi girişi (ACE) nesnelerinin doğasını tanımlamak için kullanılan dizi türünü belirtir. Olası türlerin tam listesi için [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) tanımına bakın.

## <a name="caclcacl"></a><a name="cacl"></a>CAcl::CAcl

Oluşturucu.

```
CAcl() throw();
CAcl(const CAcl& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*Rhs*<br/>
Varolan bir `CAcl` nesnesi.

### <a name="remarks"></a>Açıklamalar

Nesne `CAcl` isteğe bağlı olarak varolan `CAcl` bir nesne kullanılarak oluşturulabilir.

## <a name="caclcacl"></a><a name="dtor"></a>CAcl::~CAcl

Yıkıcı.

```
virtual ~CAcl() throw();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı nesne tarafından edinilen tüm kaynakları serbest sağlar.

## <a name="caclgetacecount"></a><a name="getacecount"></a>CAcl::GetAceCount

Erişim denetimi girişi (ACE) nesnelerinin sayısını verir.

```
virtual UINT GetAceCount() const throw() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Nesnedeki ACE girişlerinin `CAcl` sayısını döndürür.

## <a name="caclgetaclentries"></a><a name="getaclentries"></a>CAcl::GetAclEntries

Erişim denetim listesi (ACL) girişlerini `CAcl` nesneden alır.

```cpp
void GetAclEntries(
    CSid::CSidArray* pSids,
    CAccessMaskArray* pAccessMasks = NULL,
    CAceTypeArray* pAceTypes = NULL,
    CAceFlagArray* pAceFlags = NULL) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pSids*<br/>
[CSid](../../atl/reference/csid-class.md) nesneleri dizisi için bir işaretçi.

*pAccessMasks*<br/>
Erişim maskeleri.

*pAceTypes*<br/>
Erişim denetimi girişi (ACE) türleri.

*pAceFlags*<br/>
ACE bayrakları.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, dizi parametrelerini `CAcl` nesnede bulunan her ACE nesnesinin ayrıntılarıyla doldurur. Söz konusu dizinin ayrıntıları gerekli olmadığında NULL'u kullanın.

Her dizinin içeriği birbirine karşılık gelir, yani `CAccessMaskArray` dizinin ilk öğesi `CSidArray` dizideki ilk öğeye karşılık gelir ve böyle devam eder.

ACE türleri ve bayrakları hakkında daha fazla bilgi için [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) bakın.

## <a name="caclgetaclentry"></a><a name="getaclentry"></a>CAcl::GetAclEntry

Bir erişim denetim listesindeki (ACL) girişle ilgili tüm bilgileri alır.

```cpp
void GetAclEntry(
    UINT nIndex,
    CSid* pSid,
    ACCESS_MASK* pMask = NULL,
    BYTE* pType = NULL,
    BYTE* pFlags = NULL,
    GUID* pObjectType = NULL,
    GUID* pInheritedObjectType = NULL) const throw(...);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Almak için ACL girişine dizin.

*pSid*<br/>
ACL girişinin uygulandığı [CSid](../../atl/reference/csid-class.md) nesnesi.

*pMask*<br/>
Erişim izni verme veya reddetme izinlerini belirten maske.

*pTipi*<br/>
ACE türü.

*pFlags*<br/>
ACE bayrakları.

*pObjectType*<br/>
Nesne türü. Bu, nesne türü ACE'de belirtilmemişse veya ACE bir OBJECT ACE değilse GUID_NULL olarak ayarlanır.

*pInheritedObjectType*<br/>
Devralınan nesne türü. Bu, devralınan nesne türü ACE'de belirtilmemişse veya ACE bir OBJECT ACE değilse GUID_NULL olarak ayarlanır.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, tek bir ACE hakkında tüm bilgileri alır, CAcl daha fazla bilgi [sağlayan::GetAclEntries](#getaclentries) tek başına kullanılabilir hale getirir.

ACE türleri ve bayrakları hakkında daha fazla bilgi için [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) bakın.

## <a name="caclgetlength"></a><a name="getlength"></a>CAcl::GetLength

Erişim denetim listesinin (ACL) uzunluğunu döndürür.

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`ACL` Yapıyı tutmak için gerekli baytlarda gerekli uzunluğu verir.

## <a name="caclgetpacl"></a><a name="getpacl"></a>CAcl::GetPACL

Bir işaretçiyi bir erişim denetim listesine (ACL) döndürür.

```
const ACL* GetPACL() const throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

Yapıya bir `ACL` işaretçi döndürür.

## <a name="caclisempty"></a><a name="isempty"></a>CAcl::Boş

Girişler `CAcl` için nesneyi sınar.

```
bool IsEmpty() const throw();
```

### <a name="remarks"></a>Açıklamalar

`CAcl` Nesne NULL değilse ve giriş yoksa TRUE döndürür. Nesne NULL `CAcl` ise veya en az bir giriş içeriyorsa FALSE döndürür.

## <a name="caclisnull"></a><a name="isnull"></a>CAcl::IsNull

`CAcl` Nesnenin durumunu döndürür.

```
bool IsNull() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CAcl` Nesne NULL ise TRUE, aksi takdirde FALSE döndürür.

## <a name="cacloperator-const-acl-"></a><a name="operator_const_acl__star"></a>CAcl::operatör const ACL *

Nesneyi `CAcl` (erişim `ACL` denetim listesi) yapısına atar.

```
operator const ACL *() const throw(...);
```

### <a name="remarks"></a>Açıklamalar

`ACL` Yapının adresini döndürür.

## <a name="cacloperator-"></a><a name="operator_eq"></a>CAcl::operatör =

Atama işleci.

```
CAcl& operator= (const CAcl& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*Rhs*<br/>
Varolan `CAcl` nesneye atamak için.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CAcl` nesneye bir başvuru verir.

## <a name="caclremoveace"></a><a name="removeace"></a>CAcl::RemoveAce

`CAcl` Nesneden belirli bir ACE (erişim denetimi girişi) kaldırır.

```cpp
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Kaldırmak için ACE girişine dizin.

### <a name="remarks"></a>Açıklamalar

Bu yöntem [CAtlArray türetilmiştir::RemoveAt](../../atl/reference/catlarray-class.md#removeat).

## <a name="caclremoveaces"></a><a name="removeaces"></a>CAcl::Aces kaldırma

Verilen `CAcl` `CSid`ler için geçerli olan tüm ACE'leri (erişim denetimi girişleri) kaldırır.

```
bool RemoveAces(const CSid& rSid) throw(...)
```

### <a name="parameters"></a>Parametreler

*rSid*<br/>
Bir `CSid` nesneye başvuru.

## <a name="caclsetempty"></a><a name="setempty"></a>CAcl::SetEmpty

Nesneyi `CAcl` boş olarak işaretler.

```cpp
void SetEmpty() throw();
```

### <a name="remarks"></a>Açıklamalar

Boş `CAcl` veya NULL olarak ayarlanabilir: iki durum farklıdır.

## <a name="caclsetnull"></a><a name="setnull"></a>CAcl::SetNull

Nesneyi `CAcl` NULL olarak işaretler.

```cpp
void SetNull() throw();
```

### <a name="remarks"></a>Açıklamalar

Boş `CAcl` veya NULL olarak ayarlanabilir: iki durum farklıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)<br/>
[Güvenlik Genel İşlevleri](../../atl/reference/security-global-functions.md)
