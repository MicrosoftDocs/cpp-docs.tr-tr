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
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497896"
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

|Ad|Açıklama|
|----------|-----------------|
|[CAcl:: CAccessMaskArray](#caccessmaskarray)|Bir ACCESS_MASKs dizisi.|
|[CAcl:: Caceflagdizisi](#caceflagarray)|Bir bayt dizisi.|
|[CAcl:: CAceTypeArray](#cacetypearray)|Bir bayt dizisi.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAcl:: CAcl](#cacl)|Oluşturucu.|
|[CAcl:: ~ CAcl](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAcl:: GetAceCount](#getacecount)|Erişim denetimi girişi (ACE) nesne sayısını döndürür.|
|[CAcl:: Getaclendenemeler](#getaclentries)|`CAcl` Nesneden erişim denetimi listesi (ACL) girdilerini alır.|
|[CAcl:: GetAclEntry](#getaclentry)|Bir `CAcl` nesne içindeki bir girdiyle ilgili tüm bilgileri alır.|
|[CAcl:: GetLength](#getlength)|ACL 'nin uzunluğunu döndürür.|
|[CAcl:: GetPACL](#getpacl)|Bir PACL döndürür (ACL işaretçisi).|
|[CAcl:: IsEmpty](#isempty)|`CAcl` Nesneleri girdiler için sınar.|
|[CAcl:: IsNull](#isnull)|`CAcl` Nesnenin durumunu döndürür.|
|[CAcl:: RemoveAce](#removeace)|`CAcl` Nesnesinden belirli bir ACE 'yi (erişim denetimi girişi) kaldırır.|
|[CAcl:: RemoveAce 'Ler](#removeaces)|`CAcl` Verilen`CSid`için uygulanan tüm Ace 'leri (erişim denetimi girdileri) kaldırır.|
|[CAcl:: SetEmpty](#setempty)|`CAcl` Nesneyi boş olarak işaretler.|
|[CAcl:: SetNull](#setnull)|`CAcl` Nesneyi null olarak işaretler.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CAcl:: operator const ACL *](#operator_const_acl__star)|Bir `ACL` yapıya `CAcl` bir nesne yayınlar.|
|[CAcl:: operator =](#operator_eq)|Atama işleci.|

## <a name="remarks"></a>Açıklamalar

`ACL` Yapı, bir ACL 'nin üst bilgisi (erişim denetimi listesi). ACL, sıfır veya daha fazla [Ace](/windows/win32/SecAuthZ/access-control-entries) 'nin sıralı bir listesini içerir (erişim denetimi girdileri). ACL 'deki tek tek Ace 'Ler 0 ile *n-1*arasında numaralandırılır; burada *n* , ACL 'deki Ace sayısıdır. Bir ACL düzenlenirken, bir uygulama ACL içindeki bir erişim denetimi girişine (ACE) karşılık gelir.

İki ACL türü vardır:

- Seçmeli

- Sistem

İsteğe bağlı bir ACL, nesne sahibi tarafından veya nesnesine WRITE_DAC erişim izni verilen herkes tarafından denetlenir. Belirli kullanıcıların ve grupların bir nesneye sahip olduğunu belirtir. Örneğin, bir dosyanın sahibi, hangi kullanıcıların ve grupların dosya erişimine sahip olduğunu ve hangilerinin erişebileceğini denetlemek için isteğe bağlı bir ACL kullanabilir.

Bir nesne, bir sistem yöneticisi tarafından denetlenen bir sistem ACL 'si biçiminde kendisiyle ilişkili sistem düzeyi güvenlik bilgilerine de sahip olabilir. Sistem ACL 'si, sistem yöneticisinin bir nesneye erişim kazanmak için herhangi bir girişimi denetlemesine izin verebilir.

Daha fazla ayrıntı için Windows SDK [ACL](/windows/win32/SecAuthZ/access-control-lists) tartışmasına bakın.

Windows 'daki erişim denetim modeline giriş için Windows SDK [Access Control](/windows/win32/SecAuthZ/access-control) bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity. h

##  <a name="caccessmaskarray"></a>CAcl:: CAccessMaskArray

ACCESS_MASK nesnelerinden oluşan bir dizi.

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

Nesne `CAcl` , isteğe bağlı olarak, varolan `CAcl` bir nesne kullanılarak oluşturulabilir.

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

`CAcl` Nesnedeki Ace girişi sayısını döndürür.

##  <a name="getaclentries"></a>CAcl:: Getaclendenemeler

`CAcl` Nesneden erişim denetimi listesi (ACL) girdilerini alır.

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

Bu yöntem, dizi parametrelerini `CAcl` nesnesinde bulunan her Ace nesnesinin ayrıntılarıyla doldurur. Söz konusu dizinin ayrıntıları gerekli olmadığında NULL kullanın.

Her bir dizinin içeriği birbirine karşılık gelir, diğer bir deyişle, `CAccessMaskArray` dizinin ilk öğesi `CSidArray` dizideki ilk öğeye karşılık gelir ve bu şekilde devam eder.

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
Nesne türü. Bu, nesne türü ACE 'de belirtilmemişse veya ACE bir nesne ACE değilse, GUID_NULL olarak ayarlanır.

*Pınheritedobjecttype*<br/>
Devralınan nesne türü. Bu, devralınan nesne türü ACE 'de belirtilmemişse veya ACE bir nesne ACE değilse, GUID_NULL olarak ayarlanır.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, tek bir ACE hakkındaki tüm bilgileri alır ve [CAcl:: Getaclendenemeler](#getaclentries) tek başına kullanılabilir hale gelir.

ACE türleri ve bayrakları hakkında daha fazla bilgi için bkz. [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) .

##  <a name="getlength"></a>CAcl:: GetLength

Erişim denetimi listesinin (ACL) uzunluğunu döndürür.

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`ACL` Yapıyı tutmak için gerekli olan bayt sayısını döndürür.

##  <a name="getpacl"></a>CAcl:: GetPACL

Erişim denetimi listesi (ACL) için bir işaretçi döndürür.

```
const ACL* GetPACL() const throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

`ACL` Yapıya bir işaretçi döndürür.

##  <a name="isempty"></a>CAcl:: IsEmpty

`CAcl` Nesneleri girdiler için sınar.

```
bool IsEmpty() const throw();
```

### <a name="remarks"></a>Açıklamalar

`CAcl` Nesne null değilse ve girdi içermiyorsa, true döndürür. `CAcl` Nesne null ya da en az bir giriş içeriyorsa yanlış döndürür.

##  <a name="isnull"></a>CAcl:: IsNull

`CAcl` Nesnenin durumunu döndürür.

```
bool IsNull() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CAcl` Nesne null ise true, aksi takdirde false döndürür.

##  <a name="operator_const_acl__star"></a>CAcl:: operator const ACL *

Bir `CAcl` nesneyi`ACL` (erişim denetimi listesi) yapısına yayınlar.

```
operator const ACL *() const throw(...);
```

### <a name="remarks"></a>Açıklamalar

`ACL` Yapının adresini döndürür.

##  <a name="operator_eq"></a>CAcl:: operator =

Atama işleci.

```
CAcl& operator= (const CAcl& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*sağ taraftan*<br/>
Var olan nesneye atamak için.`CAcl`

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CAcl` nesneye bir başvuru döndürür.

##  <a name="removeace"></a>CAcl:: RemoveAce

`CAcl` Nesnesinden belirli bir ACE 'yi (erişim denetimi girişi) kaldırır.

```
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Kaldırılacak ACE girişinin dizini.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, [CAtlArray:: removeadresinden](../../atl/reference/catlarray-class.md#removeat)türetilir.

##  <a name="removeaces"></a>CAcl:: RemoveAce 'Ler

`CAcl` Verilen`CSid`için uygulanan ' dan gelen cepler (erişim denetimi girdileri) kaldırır.

```
bool RemoveAces(const CSid& rSid) throw(...)
```

### <a name="parameters"></a>Parametreler

*Rsıd*<br/>
Bir `CSid` nesneye başvuru.

##  <a name="setempty"></a>CAcl:: SetEmpty

`CAcl` Nesneyi boş olarak işaretler.

```
void SetEmpty() throw();
```

### <a name="remarks"></a>Açıklamalar

`CAcl` Boş veya null olarak ayarlanabilir: iki durum birbirinden farklıdır.

##  <a name="setnull"></a>CAcl:: SetNull

`CAcl` Nesneyi null olarak işaretler.

```
void SetNull() throw();
```

### <a name="remarks"></a>Açıklamalar

`CAcl` Boş veya null olarak ayarlanabilir: iki durum birbirinden farklıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[Güvenlik Genel İşlevleri](../../atl/reference/security-global-functions.md)
