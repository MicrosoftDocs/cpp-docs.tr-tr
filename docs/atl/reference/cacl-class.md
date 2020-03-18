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
ms.openlocfilehash: 5d03154597f800042846e82d0a0cf5e7c46b613f
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79418148"
---
# <a name="cacl-class"></a>CAcl sınıfı

Bu sınıf, `ACL` (erişim denetimi listesi) yapısına yönelik bir sarmalayıcıdır.

> [!IMPORTANT]
>  Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CAcl
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Adı|Açıklama|
|----------|-----------------|
|[CAcl:: CAccessMaskArray](#caccessmaskarray)|Bir dizi ACCESS_MASKs.|
|[CAcl:: Caceflagdizisi](#caceflagarray)|Bir bayt dizisi.|
|[CAcl:: CAceTypeArray](#cacetypearray)|Bir bayt dizisi.|

### <a name="public-constructors"></a>Genel Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAcl:: CAcl](#cacl)|Oluşturucu.|
|[CAcl:: ~ CAcl](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Genel Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAcl:: GetAceCount](#getacecount)|Erişim denetimi girişi (ACE) nesne sayısını döndürür.|
|[CAcl:: Getaclendenemeler](#getaclentries)|`CAcl` nesnesinden erişim denetimi listesi (ACL) girdilerini alır.|
|[CAcl:: GetAclEntry](#getaclentry)|`CAcl` nesnesindeki bir girdiyle ilgili tüm bilgileri alır.|
|[CAcl:: GetLength](#getlength)|ACL 'nin uzunluğunu döndürür.|
|[CAcl:: GetPACL](#getpacl)|Bir PACL döndürür (ACL işaretçisi).|
|[CAcl:: IsEmpty](#isempty)|`CAcl` nesnesini girişler için sınar.|
|[CAcl:: IsNull](#isnull)|`CAcl` nesnesinin durumunu döndürür.|
|[CAcl:: RemoveAce](#removeace)|`CAcl` nesnesinden belirli bir ACE 'yi (erişim denetimi girişi) kaldırır.|
|[CAcl:: RemoveAce 'Ler](#removeaces)|Verilen `CSid`uygulanan `CAcl` tüm Ace 'Leri (erişim denetimi girdileri) kaldırır.|
|[CAcl:: SetEmpty](#setempty)|`CAcl` nesnesini boş olarak işaretler.|
|[CAcl:: SetNull](#setnull)|`CAcl` nesnesini NULL olarak işaretler.|

### <a name="public-operators"></a>Genel İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CAcl:: operator const ACL *](#operator_const_acl__star)|`CAcl` nesnesini `ACL` yapısına yayınlar.|
|[CAcl:: operator =](#operator_eq)|Atama işleci.|

## <a name="remarks"></a>Açıklamalar

`ACL` yapısı bir ACL 'nin üst bilgisi (erişim denetimi listesi). ACL, sıfır veya daha fazla [Ace](/windows/win32/SecAuthZ/access-control-entries) 'nin sıralı bir listesini içerir (erişim denetimi girdileri). ACL 'deki tek tek Ace 'Ler 0 ile *n-1*arasında numaralandırılır; burada *n* , ACL 'deki Ace sayısıdır. Bir ACL düzenlenirken, bir uygulama ACL içindeki bir erişim denetimi girişine (ACE) karşılık gelir.

İki ACL türü vardır:

- Seçmeli

- Sistem

İsteğe bağlı bir ACL, nesnenin sahibi tarafından veya nesnesine erişim WRITE_DAC verilmiş bir kişi tarafından denetlenir. Belirli kullanıcıların ve grupların bir nesneye sahip olduğunu belirtir. Örneğin, bir dosyanın sahibi, hangi kullanıcıların ve grupların dosya erişimine sahip olduğunu ve hangilerinin erişebileceğini denetlemek için isteğe bağlı bir ACL kullanabilir.

Bir nesne, bir sistem yöneticisi tarafından denetlenen bir sistem ACL 'si biçiminde kendisiyle ilişkili sistem düzeyi güvenlik bilgilerine de sahip olabilir. Sistem ACL 'si, sistem yöneticisinin bir nesneye erişim kazanmak için herhangi bir girişimi denetlemesine izin verebilir.

Daha fazla ayrıntı için Windows SDK [ACL](/windows/win32/SecAuthZ/access-control-lists) tartışmasına bakın.

Windows 'daki erişim denetim modeline giriş için Windows SDK [Access Control](/windows/win32/SecAuthZ/access-control) bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity. h

##  <a name="caccessmaskarray"></a>CAcl:: CAccessMaskArray

ACCESS_MASK nesnelerden oluşan bir dizi.

```
typedef CAtlArray<ACCESS_MASK> CAccessMaskArray;
```

### <a name="remarks"></a>Açıklamalar

Bu typedef, erişim denetimi girişlerinde (ACE) kullanılan erişim haklarını depolamak için kullanılabilecek dizi türünü belirtir.

##  <a name="caceflagarray"></a>CAcl:: Caceflagdizisi

Bir bayt dizisi.

```
typedef CAtlArray<BYTE> CAceFlagArray;
```

### <a name="remarks"></a>Açıklamalar

Bu typedef, erişim denetimi girişi (ACE) türüne özgü denetim bayraklarını tanımlamak için kullanılan dizi türünü belirtir. Olası bayrakların tüm listesi için [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) tanımına bakın.

##  <a name="cacetypearray"></a>CAcl:: CAceTypeArray

Bir bayt dizisi.

```
typedef CAtlArray<BYTE> CAceTypeArray;
```

### <a name="remarks"></a>Açıklamalar

Bu typedef, ACCESS_ALLOWED_ACE_TYPE veya ACCESS_DENIED_ACE_TYPE gibi erişim denetimi girişi (ACE) nesnelerinin yapısını tanımlamak için kullanılan dizi türünü belirtir. Olası türlerin tüm listesi için [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) tanımına bakın.

##  <a name="cacl"></a>CAcl:: CAcl

Oluşturucu.

```
CAcl() throw();
CAcl(const CAcl& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*sağ taraftan*<br/>
Varolan bir `CAcl` nesnesi.

### <a name="remarks"></a>Açıklamalar

`CAcl` nesnesi, isteğe bağlı olarak, var olan bir `CAcl` nesnesi kullanılarak oluşturulabilir.

##  <a name="dtor"></a>CAcl:: ~ CAcl

Yok edicisi.

```
virtual ~CAcl() throw();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı, nesne tarafından alınan tüm kaynakları serbest bırakır.

##  <a name="getacecount"></a>CAcl:: GetAceCount

Erişim denetimi girişi (ACE) nesne sayısını döndürür.

```
virtual UINT GetAceCount() const throw() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

`CAcl` nesnesindeki ACE girişi sayısını döndürür.

##  <a name="getaclentries"></a>CAcl:: Getaclendenemeler

`CAcl` nesnesinden erişim denetimi listesi (ACL) girdilerini alır.

```
void GetAclEntries(
    CSid::CSidArray* pSids,
    CAccessMaskArray* pAccessMasks = NULL,
    CAceTypeArray* pAceTypes = NULL,
    CAceFlagArray* pAceFlags = NULL) const throw(...);
```

### <a name="parameters"></a>Parametreler

*PSID 'Ler*<br/>
[CSID](../../atl/reference/csid-class.md) nesneleri dizisine yönelik bir işaretçi.

*Paccessmaskeleri*<br/>
Erişim maskeleri.

*Pacetype*<br/>
Erişim denetimi girişi (ACE) türleri.

*pAceFlags*<br/>
ACE bayrakları.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, dizi parametrelerini `CAcl` nesnesinde bulunan her ACE nesnesinin ayrıntılarıyla doldurur. Söz konusu dizinin ayrıntıları gerekli olmadığında NULL kullanın.

Her bir dizinin içeriği birbirine karşılık gelir, diğer bir deyişle, `CAccessMaskArray` dizisinin ilk öğesi `CSidArray` dizisindeki ilk öğeye karşılık gelir ve bu şekilde devam eder.

ACE türleri ve bayrakları hakkında daha fazla bilgi için bkz. [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) .

##  <a name="getaclentry"></a>CAcl:: GetAclEntry

Bir erişim denetimi listesindeki (ACL) bir girdiyle ilgili tüm bilgileri alır.

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

*nDizin*<br/>
Alınacak ACL girişinin dizini.

*PSID*<br/>
ACL girişinin uygulandığı [CSID](../../atl/reference/csid-class.md) nesnesi.

*pMask*<br/>
Erişim izni verme veya reddetme izinlerini belirten maske.

*pType*<br/>
ACE türü.

*pFlags*<br/>
ACE bayrakları.

*pObjectType*<br/>
Nesne türü. Bu, nesne türü ACE 'de belirtilmemişse veya ACE bir nesne ACE değilse GUID_NULL olarak ayarlanır.

*Pınheritedobjecttype*<br/>
Devralınan nesne türü. Bu, devralınan nesne türü ACE 'de belirtilmemişse veya ACE bir nesne ACE değilse GUID_NULL olarak ayarlanır.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, tek bir ACE hakkındaki tüm bilgileri alır ve [CAcl:: Getaclendenemeler](#getaclentries) tek başına kullanılabilir hale gelir.

ACE türleri ve bayrakları hakkında daha fazla bilgi için bkz. [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) .

##  <a name="getlength"></a>CAcl:: GetLength

Erişim denetimi listesinin (ACL) uzunluğunu döndürür.

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`ACL` yapısını tutmak için gerekli olan bayt sayısını döndürür.

##  <a name="getpacl"></a>CAcl:: GetPACL

Erişim denetimi listesi (ACL) için bir işaretçi döndürür.

```
const ACL* GetPACL() const throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

`ACL` yapısına bir işaretçi döndürür.

##  <a name="isempty"></a>CAcl:: IsEmpty

`CAcl` nesnesini girişler için sınar.

```
bool IsEmpty() const throw();
```

### <a name="remarks"></a>Açıklamalar

`CAcl` nesnesi NULL değilse ve giriş içermiyorsa, TRUE döndürür. `CAcl` nesnesi NULL ya da en az bir giriş içeriyorsa, FALSE döndürür.

##  <a name="isnull"></a>CAcl:: IsNull

`CAcl` nesnesinin durumunu döndürür.

```
bool IsNull() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CAcl` nesnesi NULL ise TRUE, aksi takdirde FALSE döndürür.

##  <a name="operator_const_acl__star"></a>CAcl:: operator const ACL *

`CAcl` nesnesini bir `ACL` (erişim denetimi listesi) yapısına yayınlar.

```
operator const ACL *() const throw(...);
```

### <a name="remarks"></a>Açıklamalar

`ACL` yapısının adresini döndürür.

##  <a name="operator_eq"></a>CAcl:: operator =

Atama işleci.

```
CAcl& operator= (const CAcl& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*sağ taraftan*<br/>
Var olan nesneye atanacak `CAcl`.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CAcl` nesnesine bir başvuru döndürür.

##  <a name="removeace"></a>CAcl:: RemoveAce

`CAcl` nesnesinden belirli bir ACE 'yi (erişim denetimi girişi) kaldırır.

```
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Kaldırılacak ACE girişinin dizini.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, [CAtlArray:: removeadresinden](../../atl/reference/catlarray-class.md#removeat)türetilir.

##  <a name="removeaces"></a>CAcl:: RemoveAce 'Ler

Verilen `CSid`uygulanan `CAcl`, cepler (erişim denetimi girdileri) öğesini kaldırır.

```
bool RemoveAces(const CSid& rSid) throw(...)
```

### <a name="parameters"></a>Parametreler

*Rsıd*<br/>
`CSid` nesnesine bir başvuru.

##  <a name="setempty"></a>CAcl:: SetEmpty

`CAcl` nesnesini boş olarak işaretler.

```
void SetEmpty() throw();
```

### <a name="remarks"></a>Açıklamalar

`CAcl` boş veya NULL olarak ayarlanabilir: iki durum birbirinden farklıdır.

##  <a name="setnull"></a>CAcl:: SetNull

`CAcl` nesnesini NULL olarak işaretler.

```
void SetNull() throw();
```

### <a name="remarks"></a>Açıklamalar

`CAcl` boş veya NULL olarak ayarlanabilir: iki durum birbirinden farklıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[Güvenlik Genel İşlevleri](../../atl/reference/security-global-functions.md)
