---
description: 'Daha fazla bilgi edinin: CAcl sınıfı'
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
ms.openlocfilehash: 60c498336f1bfb5358dd8e5b2eb771456a84ce17
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165075"
---
# <a name="cacl-class"></a>CAcl sınıfı

Bu sınıf, `ACL` (erişim denetimi listesi) yapısına yönelik bir sarmalayıcıdır.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Syntax

```cpp
class CAcl
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|[CAcl:: CAccessMaskArray](#caccessmaskarray)|Bir dizi ACCESS_MASKs.|
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
|[CAcl:: Getaclendenemeler](#getaclentries)|Nesneden erişim denetimi listesi (ACL) girdilerini alır `CAcl` .|
|[CAcl:: GetAclEntry](#getaclentry)|Bir nesne içindeki bir girdiyle ilgili tüm bilgileri alır `CAcl` .|
|[CAcl:: GetLength](#getlength)|ACL 'nin uzunluğunu döndürür.|
|[CAcl:: GetPACL](#getpacl)|Bir PACL döndürür (ACL işaretçisi).|
|[CAcl:: IsEmpty](#isempty)|`CAcl`Nesneleri girdiler için sınar.|
|[CAcl:: IsNull](#isnull)|Nesnenin durumunu döndürür `CAcl` .|
|[CAcl:: RemoveAce](#removeace)|Nesnesinden belirli bir ACE 'yi (erişim denetimi girişi) kaldırır `CAcl` .|
|[CAcl:: RemoveAce 'Ler](#removeaces)|Verilen için uygulanan tüm Ace 'Leri (erişim denetimi girdileri) kaldırır `CAcl` `CSid` .|
|[CAcl:: SetEmpty](#setempty)|`CAcl`Nesneyi boş olarak işaretler.|
|[CAcl:: SetNull](#setnull)|`CAcl`NESNEYI null olarak işaretler.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CAcl:: operator const ACL *](#operator_const_acl__star)|Bir `CAcl` yapıya bir nesne yayınlar `ACL` .|
|[CAcl:: operator =](#operator_eq)|Atama işleci.|

## <a name="remarks"></a>Açıklamalar

`ACL`Yapı, BIR ACL 'nin üst bilgisi (erişim denetimi listesi). ACL, sıfır veya daha fazla [Ace](/windows/win32/SecAuthZ/access-control-entries) 'nin sıralı bir listesini içerir (erişim denetimi girdileri). ACL 'deki tek tek Ace 'Ler 0 ile *n-1* arasında numaralandırılır; burada *n* , ACL 'deki Ace sayısıdır. Bir ACL düzenlenirken, bir uygulama ACL içindeki bir erişim denetimi girişine (ACE) karşılık gelir.

İki ACL türü vardır:

- Seçmeli

- Sistem

İsteğe bağlı bir ACL, nesnenin sahibi tarafından veya nesnesine erişim WRITE_DAC verilmiş bir kişi tarafından denetlenir. Belirli kullanıcıların ve grupların bir nesneye sahip olduğunu belirtir. Örneğin, bir dosyanın sahibi, hangi kullanıcıların ve grupların dosya erişimine sahip olduğunu ve hangilerinin erişebileceğini denetlemek için isteğe bağlı bir ACL kullanabilir.

Bir nesne, bir sistem yöneticisi tarafından denetlenen bir sistem ACL 'si biçiminde kendisiyle ilişkili sistem düzeyi güvenlik bilgilerine de sahip olabilir. Sistem ACL 'si, sistem yöneticisinin bir nesneye erişim kazanmak için herhangi bir girişimi denetlemesine izin verebilir.

Daha fazla ayrıntı için Windows SDK [ACL](/windows/win32/SecAuthZ/access-control-lists) tartışmasına bakın.

Windows 'daki erişim denetim modeline giriş için Windows SDK [Access Control](/windows/win32/SecAuthZ/access-control) bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity. h

## <a name="caclcaccessmaskarray"></a><a name="caccessmaskarray"></a> CAcl:: CAccessMaskArray

ACCESS_MASK nesnelerden oluşan bir dizi.

```cpp
typedef CAtlArray<ACCESS_MASK> CAccessMaskArray;
```

### <a name="remarks"></a>Açıklamalar

Bu typedef, erişim denetimi girişlerinde (ACE) kullanılan erişim haklarını depolamak için kullanılabilecek dizi türünü belirtir.

## <a name="caclcaceflagarray"></a><a name="caceflagarray"></a> CAcl:: Caceflagdizisi

Bir bayt dizisi.

```cpp
typedef CAtlArray<BYTE> CAceFlagArray;
```

### <a name="remarks"></a>Açıklamalar

Bu typedef, erişim denetimi girişi (ACE) türüne özgü denetim bayraklarını tanımlamak için kullanılan dizi türünü belirtir. Olası bayrakların tüm listesi için [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) tanımına bakın.

## <a name="caclcacetypearray"></a><a name="cacetypearray"></a> CAcl:: CAceTypeArray

Bir bayt dizisi.

```cpp
typedef CAtlArray<BYTE> CAceTypeArray;
```

### <a name="remarks"></a>Açıklamalar

Bu typedef, ACCESS_ALLOWED_ACE_TYPE veya ACCESS_DENIED_ACE_TYPE gibi erişim denetimi girişi (ACE) nesnelerinin yapısını tanımlamak için kullanılan dizi türünü belirtir. Olası türlerin tüm listesi için [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) tanımına bakın.

## <a name="caclcacl"></a><a name="cacl"></a> CAcl:: CAcl

Oluşturucu.

```cpp
CAcl() throw();
CAcl(const CAcl& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*sağ taraftan*<br/>
Varolan bir `CAcl` nesnesi.

### <a name="remarks"></a>Açıklamalar

`CAcl`Nesne, isteğe bağlı olarak, varolan bir nesne kullanılarak oluşturulabilir `CAcl` .

## <a name="caclcacl"></a><a name="dtor"></a> CAcl:: ~ CAcl

Yok edicisi.

```cpp
virtual ~CAcl() throw();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı, nesne tarafından alınan tüm kaynakları serbest bırakır.

## <a name="caclgetacecount"></a><a name="getacecount"></a> CAcl:: GetAceCount

Erişim denetimi girişi (ACE) nesne sayısını döndürür.

```cpp
virtual UINT GetAceCount() const throw() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Nesnedeki ACE girişi sayısını döndürür `CAcl` .

## <a name="caclgetaclentries"></a><a name="getaclentries"></a> CAcl:: Getaclendenemeler

Nesneden erişim denetimi listesi (ACL) girdilerini alır `CAcl` .

```cpp
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

Bu yöntem, dizi parametrelerini nesnesinde bulunan her ACE nesnesinin ayrıntılarıyla doldurur `CAcl` . Söz konusu dizinin ayrıntıları gerekli olmadığında NULL kullanın.

Her bir dizinin içeriği birbirine karşılık gelir, diğer bir deyişle, dizinin ilk öğesi `CAccessMaskArray` dizideki ilk öğeye karşılık gelir `CSidArray` ve bu şekilde devam eder.

ACE türleri ve bayrakları hakkında daha fazla bilgi için bkz. [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) .

## <a name="caclgetaclentry"></a><a name="getaclentry"></a> CAcl:: GetAclEntry

Bir erişim denetimi listesindeki (ACL) bir girdiyle ilgili tüm bilgileri alır.

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

## <a name="caclgetlength"></a><a name="getlength"></a> CAcl:: GetLength

Erişim denetimi listesinin (ACL) uzunluğunu döndürür.

```cpp
UINT GetLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Yapıyı tutmak için gerekli olan bayt sayısını döndürür `ACL` .

## <a name="caclgetpacl"></a><a name="getpacl"></a> CAcl:: GetPACL

Erişim denetimi listesi (ACL) için bir işaretçi döndürür.

```cpp
const ACL* GetPACL() const throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

Yapıya bir işaretçi döndürür `ACL` .

## <a name="caclisempty"></a><a name="isempty"></a> CAcl:: IsEmpty

`CAcl`Nesneleri girdiler için sınar.

```cpp
bool IsEmpty() const throw();
```

### <a name="remarks"></a>Açıklamalar

`CAcl`Nesne null değilse ve girdi içermiyorsa, true döndürür. Nesne NULL ya da `CAcl` en az bir giriş IÇERIYORSA yanlış döndürür.

## <a name="caclisnull"></a><a name="isnull"></a> CAcl:: IsNull

Nesnenin durumunu döndürür `CAcl` .

```cpp
bool IsNull() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne NULL ise TRUE `CAcl` , aksi takdırde false döndürür.

## <a name="cacloperator-const-acl-"></a><a name="operator_const_acl__star"></a> CAcl:: operator const ACL *

Bir `CAcl` nesneyi `ACL` (erişim denetimi listesi) yapısına yayınlar.

```cpp
operator const ACL *() const throw(...);
```

### <a name="remarks"></a>Açıklamalar

Yapının adresini döndürür `ACL` .

## <a name="cacloperator-"></a><a name="operator_eq"></a> CAcl:: operator =

Atama işleci.

```cpp
CAcl& operator= (const CAcl& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*sağ taraftan*<br/>
`CAcl`Var olan nesneye atamak için.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş nesneye bir başvuru döndürür `CAcl` .

## <a name="caclremoveace"></a><a name="removeace"></a> CAcl:: RemoveAce

Nesnesinden belirli bir ACE 'yi (erişim denetimi girişi) kaldırır `CAcl` .

```cpp
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Kaldırılacak ACE girişinin dizini.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, [CAtlArray:: removeadresinden](../../atl/reference/catlarray-class.md#removeat)türetilir.

## <a name="caclremoveaces"></a><a name="removeaces"></a> CAcl:: RemoveAce 'Ler

Verilen için uygulanan ' dan gelen cepler (erişim denetimi girdileri) kaldırır `CAcl` `CSid` .

```cpp
bool RemoveAces(const CSid& rSid) throw(...)
```

### <a name="parameters"></a>Parametreler

*Rsıd*<br/>
Bir `CSid` nesneye başvuru.

## <a name="caclsetempty"></a><a name="setempty"></a> CAcl:: SetEmpty

`CAcl`Nesneyi boş olarak işaretler.

```cpp
void SetEmpty() throw();
```

### <a name="remarks"></a>Açıklamalar

`CAcl`Boş veya null olarak ayarlanabilir: iki durum birbirinden farklıdır.

## <a name="caclsetnull"></a><a name="setnull"></a> CAcl:: SetNull

`CAcl`NESNEYI null olarak işaretler.

```cpp
void SetNull() throw();
```

### <a name="remarks"></a>Açıklamalar

`CAcl`Boş veya null olarak ayarlanabilir: iki durum birbirinden farklıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[Güvenlik Genel Işlevleri](../../atl/reference/security-global-functions.md)
