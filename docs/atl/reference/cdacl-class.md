---
title: CDacl Sınıfı
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
ms.openlocfilehash: 1540c90e3538d763708e161ba6c1a5e459bb2bdf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327147"
---
# <a name="cdacl-class"></a>CDacl Sınıfı

Bu sınıf, DACL (isteğe bağlı erişim denetim listesi) yapısı için bir sarmalayıcıdır.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CDacl : public CAcl
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CDacl::CDacl](#cdacl)|Oluşturucu.|
|[CDacl::~CDacl](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDacl::AddAllowedAce](#addallowedace)|`CDacl` Nesneye izin verilen ACE (erişim denetimi girişi) ekler.|
|[CDacl::AddDeniedAce](#adddeniedace)|`CDacl` Nesneye reddedilen bir ACE ekler.|
|[CDacl::GetAceCount](#getacecount)|`CDacl` Nesnedeki ACE (erişim denetimi girişleri) sayısını verir.|
|[CDacl::RemoveAce](#removeace)|`CDacl` Nesneden belirli bir ACE (erişim denetimi girişi) kaldırır.|
|[CDacl::RemoveAllAces](#removeallaces)|`CDacl` Nesnede bulunan tüm ACE'leri kaldırır.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CDacl::operatör =](#operator_eq)|Atama işleci.|

## <a name="remarks"></a>Açıklamalar

Bir nesnenin güvenlik tanımlayıcısı bir DACL içerebilir. DACL, nesneye erişebilen kullanıcıları ve grupları tanımlayan sıfır veya daha fazla ACE (erişim denetimi girişleri) içerir. Bir DACL boşsa (diğer bir şekilde sıfır AC'ler içeriyorsa), erişim açıkça verilmez, bu nedenle erişim örtülü olarak reddedilir. Ancak, bir nesnenin güvenlik tanımlayıcısı DACL'si yoksa, nesne korumasızdır ve herkes tam erişime sahiptir.

Bir nesnenin DACL'sini almak için nesnenin sahibi olmalısınız veya nesneye READ_CONTROL erişiminiz olmalıdır. Bir nesnenin DACL'sini değiştirmek için nesneye WRITE_DAC erişiminiz olması gerekir.

Ace'leri oluşturmak, eklemek, kaldırmak ve silmek için `CDacl` sağlanan sınıf yöntemlerini kullanın. Ayrıca bakınız [AtlGetDacl](security-global-functions.md#atlgetdacl) ve [AtlSetDacl](security-global-functions.md#atlsetdacl).

Windows'daki erişim denetimi modeline giriş için Windows SDK'daki [Access Denetimi'ne](/windows/win32/SecAuthZ/access-control) bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cacl](../../atl/reference/cacl-class.md)

`CDacl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity.h

## <a name="cdacladdallowedace"></a><a name="addallowedace"></a>CDacl::AddAllowedAce

`CDacl` Nesneye izin verilen ACE (erişim denetimi girişi) ekler.

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
CSid [nesnesi.](../../atl/reference/csid-class.md)

*Accessmask*<br/>
Belirtilen `CSid` nesne için izin verilecek erişim haklarının maskesini belirtir.

*AceFlags*<br/>
ACE kalıtımını kontrol eden bit bayrakları kümesi.

*pObjectType*<br/>
Nesne türü.

*pInheritedObjectType*<br/>
Devralınan nesne türü.

### <a name="return-value"></a>Dönüş Değeri

ACE `CDacl` nesneye eklenirse TRUE döndürür, hata üzerine FALSE.

### <a name="remarks"></a>Açıklamalar

Bir `CDacl` nesne, nesneye erişebilecek kullanıcıları ve grupları tanımlayan sıfır veya daha fazla ACE (erişim denetimi girişleri) içerir. Bu yöntem, `CDacl` nesneye erişim sağlayan bir ACE ekler.

Parametrede ayarlanabilen çeşitli bayrakların açıklaması için ACE_HEADER bakın. [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) `AceFlags`

## <a name="cdacladddeniedace"></a><a name="adddeniedace"></a>CDacl::AddDeniedAce

`CDacl` Nesneye reddedilen ace (erişim denetimi girişi) ekler.

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
Bir `CSid` nesnesi.

*Accessmask*<br/>
Belirtilen `CSid` nesne için reddedilecek erişim haklarının maskesini belirtir.

*AceFlags*<br/>
ACE kalıtımını kontrol eden bit bayrakları kümesi. Yöntemin ilk biçiminde varsayılan olarak 0'a kadar.

*pObjectType*<br/>
Nesne türü.

*pInheritedObjectType*<br/>
Devralınan nesne türü.

### <a name="return-value"></a>Dönüş Değeri

ACE `CDacl` nesneye eklenirse TRUE döndürür, hata üzerine FALSE.

### <a name="remarks"></a>Açıklamalar

Bir `CDacl` nesne, nesneye erişebilecek kullanıcıları ve grupları tanımlayan sıfır veya daha fazla ACE (erişim denetimi girişleri) içerir. Bu yöntem, `CDacl` nesneye erişimi reddeden bir ACE ekler.

Parametrede ayarlanabilen çeşitli bayrakların açıklaması için ACE_HEADER bakın. [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) `AceFlags`

## <a name="cdaclcdacl"></a><a name="cdacl"></a>CDacl::CDacl

Oluşturucu.

```
CDacl (const ACL& rhs) throw(...);
CDacl () throw();
```

### <a name="parameters"></a>Parametreler

*Rhs*<br/>
Varolan `ACL` (erişim denetim listesi) yapısı.

### <a name="remarks"></a>Açıklamalar

Nesne `CDacl` isteğe bağlı olarak varolan `ACL` bir yapı kullanılarak oluşturulabilir. Bu parametre olarak yalnızca bir DACL (isteğe bağlı erişim denetim listesi) değil, bir SACL (sistem erişim denetim listesi) geçirilmesi gerektiğini unutmayın. Hata ayıklama oluşturur, bir SACL geçen bir ASSERT neden olur. Sürüm yapılarında, Bir SACL'nin geçirilmesi ACL'deki ACE'lerin (erişim denetimi girişleri) yoksayılmasına neden olur ve hiçbir hata oluşmaz.

## <a name="cdaclcdacl"></a><a name="dtor"></a>CDacl::~CDacl

Yıkıcı.

```
~CDacl () throw();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı CDacl kullanarak tüm ACE'ler (erişim-kontrol girişleri) dahil olmak üzere nesne tarafından edinilen tüm kaynakları [serbest::RemoveAllAces](#removeallaces).

## <a name="cdaclgetacecount"></a><a name="getacecount"></a>CDacl::GetAceCount

`CDacl` Nesnedeki ACE (erişim denetimi girişleri) sayısını verir.

```
UINT GetAceCount() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CDacl` Nesnede bulunan ACE sayısını döndürür.

## <a name="cdacloperator-"></a><a name="operator_eq"></a>CDacl::operatör =

Atama işleci.

```
CDacl& operator= (const ACL& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*Rhs*<br/>
Varolan nesneye atamak için ACL (erişim denetim listesi).

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CDacl` nesneye bir başvuru verir.

### <a name="remarks"></a>Açıklamalar

Bu işleve yalnızca bir DACL (isteğe bağlı erişim denetim listesi) geçtiğinden emin olmalısınız. SACL 'nin (sistem erişim denetim listesi) bu işleve geçirilmesi hata ayıklama yapılarda bir Assert'a neden olur, ancak sürüm yapılarında hata yayılmaz.

## <a name="cdaclremoveace"></a><a name="removeace"></a>CDacl::RemoveAce

`CDacl` Nesneden belirli bir ACE (erişim denetimi girişi) kaldırır.

```
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Kaldırmak için ACE girişine dizin.

### <a name="remarks"></a>Açıklamalar

Bu yöntem [CAtlArray türetilmiştir::RemoveAt](../../atl/reference/catlarray-class.md#removeat).

## <a name="cdaclremoveallaces"></a><a name="removeallaces"></a>CDacl::RemoveAllAces

`CDacl` Nesnede bulunan tüm ACE'leri (erişim denetimi girişleri) kaldırır.

```
void RemoveAllAces() throw();
```

### <a name="remarks"></a>Açıklamalar

Nesnedeki `CDacl` `ACE` her (erişim denetimi girişi) yapısını (varsa) kaldırır.

## <a name="see-also"></a>Ayrıca bkz.

[Güvenlik Örneği](../../overview/visual-cpp-samples.md)<br/>
[CAcl Sınıfı](../../atl/reference/cacl-class.md)<br/>
[Acl](/windows/win32/SecAuthZ/access-control-lists)<br/>
[Ace](/windows/win32/SecAuthZ/access-control-entries)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)<br/>
[Güvenlik Genel İşlevleri](../../atl/reference/security-global-functions.md)
