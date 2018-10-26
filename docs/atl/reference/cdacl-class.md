---
title: CDacl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CDacl
- ATLSECURITY/ATL::CDacl
- ATLSECURITY/ATL::CDacl::CDacl
- ATLSECURITY/ATL::CDacl::AddAllowedAce
- ATLSECURITY/ATL::CDacl::AddDeniedAce
- ATLSECURITY/ATL::CDacl::GetAceCount
- ATLSECURITY/ATL::CDacl::RemoveAce
- ATLSECURITY/ATL::CDacl::RemoveAllAces
dev_langs:
- C++
helpviewer_keywords:
- CDacl class
ms.assetid: 2dc76616-6362-4967-b6cf-e2d39ca37ddd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f3d0b817fc080ff81e11e1789387f50cb3e871e5
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50076015"
---
# <a name="cdacl-class"></a>CDacl sınıfı

(İsteğe bağlı erişim denetimi listesi) DACL yapısı için bir sarmalayıcı sınıftır.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CDacl : public CAcl
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDacl::CDacl](#cdacl)|Oluşturucu.|
|[CDacl::~CDacl](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDacl::AddAllowedAce](#addallowedace)|İzin verilen ACE (erişim denetimi girişi) ekler `CDacl` nesne.|
|[CDacl::AddDeniedAce](#adddeniedace)|Reddedilen bir AS ekler `CDacl` nesne.|
|[CDacl::GetAceCount](#getacecount)|ACE (erişim denetimi girdileri) sayısını döndürür `CDacl` nesne.|
|[CDacl::RemoveAce](#removeace)|Belirli bir ACE (erişim denetimi girişi) kaldırır `CDacl` nesne.|
|[CDacl::RemoveAllAces](#removeallaces)|Tüm bulunan ACE kaldırır `CDacl` nesne.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CDacl::operator =](#operator_eq)|Atama işleci.|

## <a name="remarks"></a>Açıklamalar

Bir nesnenin güvenlik tanımlayıcısının DACL içerebilir. Bir DACL kullanıcılar ve nesne erişebilecek grupları tanımlar sıfır veya daha fazla ACE (erişim denetimi girdileri) içerir. Boş bir DACL ise (diğer bir deyişle, sıfır ACE içerdiği), örtük olarak erişim reddedildiği için hiçbir erişim açıkça verilir. Ancak, bir nesnenin güvenlik tanımlayıcısının DACL yok, korumasız bir nesnedir ve herkesin tam erişimi vardır.

Bir nesnenin DACL almak için nesnenin sahibi olmanız veya nesne READ_CONTROL erişiminiz olması gerekir. Bir nesnenin DACL değiştirmek için nesne WRITE_DAC erişimi olmalıdır.

Oluşturma, ekleme, kaldırma ve ACE öğesinden silmek sağlanan sınıf yöntemleriyle `CDacl` nesne. Ayrıca bkz: [AtlGetDacl](security-global-functions.md#atlgetdacl) ve [AtlSetDacl](security-global-functions.md#atlsetdacl).

Windows, erişim denetimi modeli için bir giriş için bkz [erişim denetimi](/windows/desktop/SecAuthZ/access-control) Windows SDK.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CAcl](../../atl/reference/cacl-class.md)

`CDacl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlsecurity.h

##  <a name="addallowedace"></a>  CDacl::AddAllowedAce

İzin verilen ACE (erişim denetimi girişi) ekler `CDacl` nesne.

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

*rSid*<br/>
A [CSID](../../atl/reference/csid-class.md) nesne.

*AccessMask*<br/>
İzin verilmesi için erişim haklarını maskesini belirtir için belirtilen `CSid` nesne.

*AceFlags*<br/>
ACE devralma denetleyen bit bayrakları kümesini.

*pObjectType*<br/>
Nesne türü.

*pInheritedObjectType*<br/>
Devralınan bir nesne türü.

### <a name="return-value"></a>Dönüş Değeri

ACE eklenirse TRUE döndürür `CDacl` yanlış hatasında nesne.

### <a name="remarks"></a>Açıklamalar

A `CDacl` nesnesi, nesne erişebilecek grupları ve kullanıcıları tanımlama sıfır veya daha fazla ACE (erişim denetimi girdileri) içerir. Bu yöntem erişimine izin veren bir ACE ekler `CDacl` nesne.

Bkz: [ACE_HEADER](/windows/desktop/api/winnt/ns-winnt-_ace_header) içinde ayarlanan çeşitli bayrakları açıklamasını `AceFlags` parametresi.

##  <a name="adddeniedace"></a>  CDacl::AddDeniedAce

Reddedilen bir ACE (erişim denetimi girişi) ekler `CDacl` nesne.

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

*rSid*<br/>
A `CSid` nesne.

*AccessMask*<br/>
Erişim hakları reddedildi olarak maskesini belirtir için belirtilen `CSid` nesne.

*AceFlags*<br/>
ACE devralma denetleyen bit bayrakları kümesini. Varsayılan olarak 0 yöntemin ilk biçiminde.

*pObjectType*<br/>
Nesne türü.

*pInheritedObjectType*<br/>
Devralınan bir nesne türü.

### <a name="return-value"></a>Dönüş Değeri

ACE eklenirse TRUE döndürür `CDacl` yanlış hatasında nesne.

### <a name="remarks"></a>Açıklamalar

A `CDacl` nesnesi, nesne erişebilecek grupları ve kullanıcıları tanımlama sıfır veya daha fazla ACE (erişim denetimi girdileri) içerir. Bu yöntem erişim iznini reddeder ACE ekler `CDacl` nesne.

Bkz: [ACE_HEADER](/windows/desktop/api/winnt/ns-winnt-_ace_header) içinde ayarlanan çeşitli bayrakları açıklamasını `AceFlags` parametresi.

##  <a name="cdacl"></a>  CDacl::CDacl

Oluşturucu.

```
CDacl (const ACL& rhs) throw(...);
CDacl () throw();
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Mevcut bir `ACL` yapısı (erişim denetim listesi).

### <a name="remarks"></a>Açıklamalar

`CDacl` Nesne isteğe bağlı olarak oluşturulabilir var olan bir `ACL` yapısı. (İsteğe bağlı erişim denetimi listesi) DACL yalnızca bir dikkate almak önemlidir ve SACL değil (sistem erişim denetim listesi), bu parametre olarak geçirilen. Hata ayıklama yapılarında SACL geçirme ASSERT neden olur. Yayın derlemeleri SACL geçirme ACE (erişim denetimi girdileri) ACL'de yoksayılmasına neden olur ve herhangi bir hata meydana gelir.

##  <a name="dtor"></a>  CDacl::~CDacl

Yıkıcı.

```
~CDacl () throw();
```

### <a name="remarks"></a>Açıklamalar

Yok edici kullanarak tüm ACE (erişim denetimi girdileri) dahil olmak üzere nesne tarafından alınan tüm kaynakları serbest bırakan [CDacl::RemoveAllAces](#removeallaces).

##  <a name="getacecount"></a>  CDacl::GetAceCount

ACE (erişim denetimi girdileri) sayısını döndürür `CDacl` nesne.

```
UINT GetAceCount() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

ACE'ler yer alan sayısını döndürür `CDacl` nesne.

##  <a name="operator_eq"></a>  CDacl::operator =

Atama işleci.

```
CDacl& operator= (const ACL& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Var olan nesneye atamak için ACL (erişim denetim listesi).

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş bir başvuru döndürür `CDacl` nesne.

### <a name="remarks"></a>Açıklamalar

(İsteğe bağlı erişim denetimi listesi) DACL yalnızca bu işleve başarılı emin olmanız gerekir. (Sistem erişim denetim listesi) SACL geçirme bu işlev bir ONAYLAMADIR hata ayıklama yapılarında neden olur ancak sürüm yapılarında hata neden olur.

##  <a name="removeace"></a>  CDacl::RemoveAce

Belirli bir ACE (erişim denetimi girişi) kaldırır `CDacl` nesne.

```
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Kaldırmak için ACE giriş dizini.

### <a name="remarks"></a>Açıklamalar

Bu yöntem türetilmiş [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat).

##  <a name="removeallaces"></a>  CDacl::RemoveAllAces

Tüm bulunan ACE (erişim denetimi girdileri) kaldırır `CDacl` nesne.

```
void RemoveAllAces() throw();
```

### <a name="remarks"></a>Açıklamalar

Kaldırır her `ACE` (erişim denetimi girişi) yapısı (varsa) içinde `CDacl` nesne.

## <a name="see-also"></a>Ayrıca Bkz.

[Güvenliği örneği](../../visual-cpp-samples.md)<br/>
[CAcl Sınıfı](../../atl/reference/cacl-class.md)<br/>
[ACL'ler](/windows/desktop/SecAuthZ/access-control-lists)<br/>
[ACE](/windows/desktop/SecAuthZ/access-control-entries)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)<br/>
[Güvenlik Genel İşlevleri](../../atl/reference/security-global-functions.md)
