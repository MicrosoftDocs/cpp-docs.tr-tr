---
description: 'Daha fazla bilgi edinin: CDacl sınıfı'
title: CDacl sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDacl
- ATLSECURITY/ATL::CDacl
- ATLSECURITY/ATL::CDacl::CDacl
- ATLSECURITY/ATL::CDacl::AddAllowedAce
- ATLSECURITY/ATL::CDacl::AddDeniedAce
- ATLSECURITY/ATL::CDacl::GetAceCount
- ATLSECURITY/ATL::CDacl::RemoveAce
- ATLSECURITY/ATL::CDacl::RemoveAllAces
helpviewer_keywords:
- CDacl class
ms.assetid: 2dc76616-6362-4967-b6cf-e2d39ca37ddd
ms.openlocfilehash: 0f071cbf426fe9cf89752defa19ff7f212e142d1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142005"
---
# <a name="cdacl-class"></a>CDacl sınıfı

Bu sınıf, bir DACL (isteğe bağlı erişim denetimi listesi) yapısına yönelik bir sarmalayıcıdır.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Syntax

```
class CDacl : public CAcl
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDacl:: CDacl](#cdacl)|Oluşturucu.|
|[CDacl:: ~ CDacl](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDacl:: Addallowedadce](#addallowedace)|Nesnesine izin verilen ACE (erişim denetimi girişi) ekler `CDacl` .|
|[CDacl:: Adddenıedadce](#adddeniedace)|Nesnesine bir reddedildi ACE ekler `CDacl` .|
|[CDacl:: GetAceCount](#getacecount)|Nesnedeki ACE sayısını (erişim denetimi girdileri) döndürür `CDacl` .|
|[CDacl:: RemoveAce](#removeace)|Nesnesinden belirli bir ACE 'yi (erişim denetimi girişi) kaldırır `CDacl` .|
|[CDacl:: RemoveAllAces](#removeallaces)|Nesnesinde bulunan tüm Ace 'Leri kaldırır `CDacl` .|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CDacl:: operator =](#operator_eq)|Atama işleci.|

## <a name="remarks"></a>Açıklamalar

Bir nesnenin güvenlik tanımlayıcısı, bir DACL içerebilir. Bir DACL, nesneye erişebilen kullanıcıları ve grupları belirleyen sıfır veya daha fazla ACE (erişim denetimi girişleri) içerir. Bir DACL boşsa (yani sıfır Ace 'Leri içeriyorsa), erişim örtük olarak reddedilir. Ancak, bir nesnenin güvenlik tanımlayıcısının bir DACL 'si yoksa, nesne korumasız olur ve herkesin erişimi tamamlanmıştır.

Bir nesnenin DACL 'sini almak için nesnenin sahibi olmanız veya nesneye READ_CONTROL erişiminizin olması gerekir. Bir nesnenin DACL 'sini değiştirmek için nesneye WRITE_DAC erişiminizin olması gerekir.

Nesnesinden Ace 'Ler oluşturmak, eklemek, kaldırmak ve silmek için belirtilen sınıf yöntemlerini kullanın `CDacl` . Ayrıca bkz. [AtlGetDacl](security-global-functions.md#atlgetdacl) ve [AtlSetDacl](security-global-functions.md#atlsetdacl).

Windows 'daki erişim denetim modeline giriş için Windows SDK [Access Control](/windows/win32/SecAuthZ/access-control) bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CAcl](../../atl/reference/cacl-class.md)

`CDacl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity. h

## <a name="cdacladdallowedace"></a><a name="addallowedace"></a> CDacl:: Addallowedadce

Nesnesine izin verilen ACE (erişim denetimi girişi) ekler `CDacl` .

```
bool AddAllowedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags = 0) throw(...);

bool AddAllowedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```

### <a name="parameters"></a>Parametreler

*Rsıd*<br/>
Bir [CSID](../../atl/reference/csid-class.md) nesnesi.

*AccessMask*<br/>
Belirtilen nesne için izin verilen erişim haklarının maskesini belirtir `CSid` .

*Asetat bayrakları*<br/>
ACE devralmayı denetleyen bit bayrakları kümesi.

*pObjectType*<br/>
Nesne türü.

*Pınheritedobjecttype*<br/>
Devralınan nesne türü.

### <a name="return-value"></a>Dönüş Değeri

ACE nesneye eklenirse TRUE `CDacl` , hata durumunda FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

`CDacl`Nesne, nesnesine erişebilen kullanıcıları ve grupları belirleyen sıfır veya daha fazla ACE (erişim denetimi girişleri) içerir. Bu yöntem, nesnesine erişime izin veren bir ACE ekler `CDacl` .

Parametresinde ayarlayabilen çeşitli bayrakların açıklaması için bkz. [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) `AceFlags` .

## <a name="cdacladddeniedace"></a><a name="adddeniedace"></a> CDacl:: Adddenıedadce

Nesneye reddedilen ACE (erişim denetimi girişi) ekler `CDacl` .

```
bool AddDeniedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags = 0) throw(...);

bool AddDeniedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```

### <a name="parameters"></a>Parametreler

*Rsıd*<br/>
Bir `CSid` nesnesi.

*AccessMask*<br/>
Belirtilen nesne için izin verilmeyen erişim haklarının maskesini belirtir `CSid` .

*Asetat bayrakları*<br/>
ACE devralmayı denetleyen bit bayrakları kümesi. Metodun ilk biçiminde varsayılan değer 0 ' dır.

*pObjectType*<br/>
Nesne türü.

*Pınheritedobjecttype*<br/>
Devralınan nesne türü.

### <a name="return-value"></a>Dönüş Değeri

ACE nesneye eklenirse TRUE `CDacl` , hata durumunda FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

`CDacl`Nesne, nesnesine erişebilen kullanıcıları ve grupları belirleyen sıfır veya daha fazla ACE (erişim denetimi girişleri) içerir. Bu yöntem, nesnesine erişimi reddeden bir ACE ekler `CDacl` .

Parametresinde ayarlayabilen çeşitli bayrakların açıklaması için bkz. [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) `AceFlags` .

## <a name="cdaclcdacl"></a><a name="cdacl"></a> CDacl:: CDacl

Oluşturucu.

```
CDacl (const ACL& rhs) throw(...);
CDacl () throw();
```

### <a name="parameters"></a>Parametreler

*sağ taraftan*<br/>
Var olan bir `ACL` (erişim denetimi listesi) yapısı.

### <a name="remarks"></a>Açıklamalar

`CDacl`Nesne, isteğe bağlı olarak, var olan bir `ACL` Yapı kullanılarak oluşturulabilir. Yalnızca bir DACL (sistem erişimi-denetim listesi) değil, bu parametre olarak bir DACL (bir isteğe bağlı erişim denetimi listesi) geçtiğini unutmayın. Hata ayıklama yapılarında, SACL geçirilmesi bir onaylama yapılmasına neden olur. Yayın yapıları ' nda, SACL 'nin geçirilmesi ACL 'deki ACE (erişim denetimi girdileri) yoksayılmasına neden olur ve hata oluşmaz.

## <a name="cdaclcdacl"></a><a name="dtor"></a> CDacl:: ~ CDacl

Yok edicisi.

```
~CDacl () throw();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı, [CDacl:: RemoveAllAces](#removeallaces)kullanarak tüm Ace 'ler (erişim-denetim girişleri) dahil olmak üzere, nesne tarafından alınan tüm kaynakları serbest bırakır.

## <a name="cdaclgetacecount"></a><a name="getacecount"></a> CDacl:: GetAceCount

Nesnedeki ACE sayısını (erişim denetimi girdileri) döndürür `CDacl` .

```
UINT GetAceCount() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Nesnede bulunan ACE sayısını döndürür `CDacl` .

## <a name="cdacloperator-"></a><a name="operator_eq"></a> CDacl:: operator =

Atama işleci.

```
CDacl& operator= (const ACL& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*sağ taraftan*<br/>
Mevcut nesneye atanacak ACL (erişim denetimi listesi).

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş nesneye bir başvuru döndürür `CDacl` .

### <a name="remarks"></a>Açıklamalar

Bu işleve yalnızca bir DACL (isteğe bağlı erişim denetimi listesi) iletdiğinizden emin olmanız gerekir. Bu işleve bir SACL (sistem erişim denetimi listesi) geçirmek hata ayıklama yapılarında bir onaylama yapılmasına neden olur, ancak yayın yapılarında hata vermez.

## <a name="cdaclremoveace"></a><a name="removeace"></a> CDacl:: RemoveAce

Nesnesinden belirli bir ACE 'yi (erişim denetimi girişi) kaldırır `CDacl` .

```cpp
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Kaldırılacak ACE girişinin dizini.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, [CAtlArray:: removeadresinden](../../atl/reference/catlarray-class.md#removeat)türetilir.

## <a name="cdaclremoveallaces"></a><a name="removeallaces"></a> CDacl:: RemoveAllAces

Nesnesinde bulunan tüm Ace 'Leri (erişim denetimi girdileri) kaldırır `CDacl` .

```cpp
void RemoveAllAces() throw();
```

### <a name="remarks"></a>Açıklamalar

Nesnesinde ( `ACE` varsa) her (erişim denetimi girişi) yapısını kaldırır `CDacl` .

## <a name="see-also"></a>Ayrıca bkz.

[Güvenlik örneği](../../overview/visual-cpp-samples.md)<br/>
[CAcl sınıfı](../../atl/reference/cacl-class.md)<br/>
[Cacls](/windows/win32/SecAuthZ/access-control-lists)<br/>
[Ace 'ler](/windows/win32/SecAuthZ/access-control-entries)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[Güvenlik Genel Işlevleri](../../atl/reference/security-global-functions.md)
