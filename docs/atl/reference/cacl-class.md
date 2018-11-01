---
title: CAcl sınıfı
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
ms.openlocfilehash: a9653225f3057d6c5ba9fd49cf64487e766ca8d1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50491552"
---
# <a name="cacl-class"></a>CAcl sınıfı

Bu sınıf için bir sarmalayıcı olan bir `ACL` yapısı (erişim denetim listesi).

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CAcl
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|[CAcl::CAccessMaskArray](#caccessmaskarray)|ACCESS_MASKs dizisi.|
|[CAcl::CAceFlagArray](#caceflagarray)|Bir bayt dizisi.|
|[CAcl::CAceTypeArray](#cacetypearray)|Bir bayt dizisi.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAcl::CAcl](#cacl)|Oluşturucu.|
|[CAcl:: ~ CAcl](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAcl::GetAceCount](#getacecount)|Erişim denetimi girişi (ACE) nesneleri döndürür.|
|[CAcl::GetAclEntries](#getaclentries)|Erişim denetimi listesi (ACL) girişlerinden alır `CAcl` nesne.|
|[CAcl::GetAclEntry](#getaclentry)|Tüm bir girişe hakkındaki bilgileri alır bir `CAcl` nesne.|
|[CAcl::GetLength](#getlength)|ACL uzunluğunu döndürür.|
|[CAcl::GetPACL](#getpacl)|Bir PACL (bir ACL işaretçisi) döndürür.|
|[CAcl::IsEmpty](#isempty)|Testleri `CAcl` girişler için nesne.|
|[CAcl::IsNull](#isnull)|Durumunu döndüren `CAcl` nesne.|
|[CAcl::RemoveAce](#removeace)|Belirli bir ACE (erişim denetimi girişi) kaldırır `CAcl` nesne.|
|[CAcl::RemoveAces](#removeaces)|Tüm ACE (erişim denetimi girdileri) kaldırır `CAcl` geçerli verilen `CSid`.|
|[CAcl::SetEmpty](#setempty)|İşaretleri `CAcl` nesnesi boş.|
|[CAcl::SetNull](#setnull)|İşaretleri `CAcl` nesne NULL olarak.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[Const ACL CAcl::operator *](#operator_const_acl__star)|Yayınları bir `CAcl` nesnesini bir `ACL` yapısı.|
|[CAcl::operator =](#operator_eq)|Atama işleci.|

## <a name="remarks"></a>Açıklamalar

`ACL` Yapısıdır üst bilgisine bir ACL (erişim denetim listesi). Bir ACL sıfır veya daha fazla olan sıralı bir listesini içeren [ACE](/windows/desktop/SecAuthZ/access-control-entries) (erişim denetimi girdileri). Bir ACL içinde tek tek ACE'ler 0'dan numaralandırılır *n-1*burada *n* ACE acl'sindeki sayısıdır. Bir ACL düzenlerken, bir uygulama içinde ACL erişim denetimi girişi (ACE) tarafından dizinini ifade eder.

İki ACL türü vardır:

- İsteğe bağlı

- Sistem

İsteğe bağlı bir ACL, bir nesnenin sahibi tarafından denetlenir veya herhangi bir nesne WRITE_DAC erişim izni. Bu, bir nesneye erişimi belirli kullanıcıları ve grupları olabilir belirtir. Örneğin, bir dosyanın sahibi, hangi kullanıcıların ve grupların olabilir ve dosyaya erişimi olamaz denetlemek için isteğe bağlı bir ACL kullanabilirsiniz.

Bir nesne, bir sistemin bir sistem yöneticisi tarafından denetlenen ACL biçiminde ilişkili sistem düzeyindeki güvenlik bilgileri de sağlayabilirsiniz. Bir sistem ACL, bir nesneye erişim girişimlerini denetlemek için sistem yöneticisine izin verebilirsiniz.

Daha fazla ayrıntı için [ACL](/windows/desktop/SecAuthZ/access-control-lists) Windows SDK'sı tartışma.

Windows, erişim denetimi modeli için bir giriş için bkz [erişim denetimi](/windows/desktop/SecAuthZ/access-control) Windows SDK.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlsecurity.h

##  <a name="caccessmaskarray"></a>  CAcl::CAccessMaskArray

ACCESS_MASK nesneleri dizisi.

```
typedef CAtlArray<ACCESS_MASK> CAccessMaskArray;
```

### <a name="remarks"></a>Açıklamalar

Bu tür tanımı, erişim hakları kullanılan erişim denetimi girdileri (ACE) depolamak için kullanılan bir dizi türü belirtir.

##  <a name="caceflagarray"></a>  CAcl::CAceFlagArray

Bir bayt dizisi.

```
typedef CAtlArray<BYTE> CAceFlagArray;
```

### <a name="remarks"></a>Açıklamalar

Bu tür tanımı, erişim denetimi girişi (ACE) türüne özgü denetim bayrakları tanımlamak için kullanılan bir dizi türü belirtir. Bkz: [ACE_HEADER](/windows/desktop/api/winnt/ns-winnt-_ace_header) tanımı tam listesi için olası bayraklar.

##  <a name="cacetypearray"></a>  CAcl::CAceTypeArray

Bir bayt dizisi.

```
typedef CAtlArray<BYTE> CAceTypeArray;
```

### <a name="remarks"></a>Açıklamalar

Bu tür tanımı, erişim denetimi girişi (ACE) nesneleri ACCESS_ALLOWED_ACE_TYPE veya ACCESS_DENIED_ACE_TYPE gibi yapısını tanımlamak için kullanılan bir dizi türü belirtir. Bkz: [ACE_HEADER](/windows/desktop/api/winnt/ns-winnt-_ace_header) olası türlerinin tam listesi için tanımı.

##  <a name="cacl"></a>  CAcl::CAcl

Oluşturucu.

```
CAcl() throw();
CAcl(const CAcl& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Varolan bir `CAcl` nesnesi.

### <a name="remarks"></a>Açıklamalar

`CAcl` Nesne isteğe bağlı olarak oluşturulabilir var olan bir `CAcl` nesne.

##  <a name="dtor"></a>  CAcl:: ~ CAcl

Yıkıcı.

```
virtual ~CAcl() throw();
```

### <a name="remarks"></a>Açıklamalar

Yok edici, nesne tarafından alınan tüm kaynakları serbest bırakır.

##  <a name="getacecount"></a>  CAcl::GetAceCount

Erişim denetimi girişi (ACE) nesneleri döndürür.

```
virtual UINT GetAceCount() const throw() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

ACE girişleri döndürür `CAcl` nesne.

##  <a name="getaclentries"></a>  CAcl::GetAclEntries

Erişim denetimi listesi (ACL) girişlerinden alır `CAcl` nesne.

```
void GetAclEntries(
    CSid::CSidArray* pSids,
    CAccessMaskArray* pAccessMasks = NULL,
    CAceTypeArray* pAceTypes = NULL,
    CAceFlagArray* pAceFlags = NULL) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pSids*<br/>
Bir dizi işaretçi [CSID](../../atl/reference/csid-class.md) nesneleri.

*pAccessMasks*<br/>
Erişim maskesi.

*pAceTypes*<br/>
Erişim denetimi girişi (ACE) türleri.

*pAceFlags*<br/>
ACE bayraklar.

### <a name="remarks"></a>Açıklamalar

Bu yöntem bulunan her ACE nesne ayrıntılarını dizi parametrelerle doldurur `CAcl` nesne. Ayrıntılar için belirli bir dizi gerekli olmadığında NULL kullanın.

Her dizi içeriğini birbiriyle diğer bir deyişle, ilk öğesine karşılık gelen `CAccessMaskArray` dizi içindeki ilk öğeye karşılık gelen `CSidArray` dizi ve benzeri.

Bkz: [ACE_HEADER](/windows/desktop/api/winnt/ns-winnt-_ace_header) ACE türleri ve bayrakları hakkında daha fazla ayrıntı için.

##  <a name="getaclentry"></a>  CAcl::GetAclEntry

Tüm bir erişim denetimi listesi (ACL) bir giriş bilgilerini alır.

```
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

*nIndex*<br/>
Alınacak ACL girişi için dizin.

*Psıd*<br/>
[CSID](../../atl/reference/csid-class.md) ACL girişi uygulandığı nesne.

*pMask*<br/>
Maske izinleri vermek veya erişimini engellemek için belirleme.

*pType*<br/>
ACE türü.

*pFlags*<br/>
ACE bayraklar.

*pObjectType*<br/>
Nesne türü. Bu GUID_NULL için nesne türü ACE belirtilmezse veya ACE nesne ACE değilse ayarlanır.

*pInheritedObjectType*<br/>
Devralınan bir nesne türü. Bu GUID_NULL için devralınan nesne türü ACE belirtilmezse veya ACE nesne ACE değilse ayarlanır.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, tüm bilgileri hakkında daha fazla bilgi sağlayan bir tek ACE alır [CAcl::GetAclEntries](#getaclentries) tek başına kullanılabilir hale getirir.

Bkz: [ACE_HEADER](/windows/desktop/api/winnt/ns-winnt-_ace_header) ACE türleri ve bayrakları hakkında daha fazla ayrıntı için.

##  <a name="getlength"></a>  CAcl::GetLength

Erişim denetimi listesi (ACL) uzunluğunu döndürür.

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

İstenen uzunluğa tutmak gereken bayt cinsinden döndürür `ACL` yapısı.

##  <a name="getpacl"></a>  CAcl::GetPACL

Erişim denetimi listesi (ACL) için bir işaretçi döndürür.

```
const ACL* GetPACL() const throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi döndürür `ACL` yapısı.

##  <a name="isempty"></a>  CAcl::IsEmpty

Testleri `CAcl` girişler için nesne.

```
bool IsEmpty() const throw();
```

### <a name="remarks"></a>Açıklamalar

Gerekirse TRUE döndürür `CAcl` nesnesi NULL değil ve yok girişler içeriyor. FALSE döndürür `CAcl` nesne ya da null ya da en az bir giriş içeriyor.

##  <a name="isnull"></a>  CAcl::IsNull

Durumunu döndüren `CAcl` nesne.

```
bool IsNull() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Gerekirse TRUE döndürür `CAcl` nesnesi, NULL, yanlış Aksi takdirde.

##  <a name="operator_const_acl__star"></a>  Const ACL CAcl::operator *

Yayınları bir `CAcl` nesnesini bir `ACL` yapısı (erişim denetim listesi).

```
operator const ACL *() const throw(...);
```

### <a name="remarks"></a>Açıklamalar

Adresini döndürür `ACL` yapısı.

##  <a name="operator_eq"></a>  CAcl::operator =

Atama işleci.

```
CAcl& operator= (const CAcl& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
`CAcl` Var olan nesneye atamak için.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş bir başvuru döndürür `CAcl` nesne.

##  <a name="removeace"></a>  CAcl::RemoveAce

Belirli bir ACE (erişim denetimi girişi) kaldırır `CAcl` nesne.

```
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Kaldırmak için ACE giriş dizini.

### <a name="remarks"></a>Açıklamalar

Bu yöntem türetilmiş [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat).

##  <a name="removeaces"></a>  CAcl::RemoveAces

Yanıtla ACE (erişim denetimi girdileri) kaldırır `CAcl` geçerli verilen `CSid`.

```
bool RemoveAces(const CSid& rSid) throw(...)
```

### <a name="parameters"></a>Parametreler

*rSid*<br/>
Bir başvuru bir `CSid` nesne.

##  <a name="setempty"></a>  CAcl::SetEmpty

İşaretleri `CAcl` nesnesi boş.

```
void SetEmpty() throw();
```

### <a name="remarks"></a>Açıklamalar

`CAcl` Boş veya NULL olarak ayarlanabilir: iki durum farklıdır.

##  <a name="setnull"></a>  CAcl::SetNull

İşaretleri `CAcl` nesne NULL olarak.

```
void SetNull() throw();
```

### <a name="remarks"></a>Açıklamalar

`CAcl` Boş veya NULL olarak ayarlanabilir: iki durum farklıdır.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)<br/>
[Güvenlik Genel İşlevleri](../../atl/reference/security-global-functions.md)
