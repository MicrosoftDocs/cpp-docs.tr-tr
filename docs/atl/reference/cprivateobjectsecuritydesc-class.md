---
title: CPrivateObjectSecurityDesc Class
ms.date: 11/04/2016
f1_keywords:
- CPrivateObjectSecurityDesc
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::CPrivateObjectSecurityDesc
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::ConvertToAutoInherit
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::Create
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::Get
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::Set
helpviewer_keywords:
- CPrivateObjectSecurityDesc class
ms.assetid: 2c4bbb13-bf99-4833-912a-197f6815bb5d
ms.openlocfilehash: cc726892515ea38a559bdf182affa96f84be3449
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66503297"
---
# <a name="cprivateobjectsecuritydesc-class"></a>CPrivateObjectSecurityDesc Class

Bu sınıf, bir özel nesneye güvenli tanımlayıcısı nesnesi temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CPrivateObjectSecurityDesc : public CSecurityDesc
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CPrivateObjectSecurityDesc::CPrivateObjectSecurityDesc](#cprivateobjectsecuritydesc)|Oluşturucu.|
|[CPrivateObjectSecurityDesc::~CPrivateObjectSecurityDesc](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CPrivateObjectSecurityDesc::ConvertToAutoInherit](#converttoautoinherit)|Güvenlik tanımlayıcısı ve onun erişim denetim listelerini (ACL'ler) otomatik yayma devralınabilir erişim denetimi girişlerinin (ACE'ler) destekleyen bir biçime dönüştürmek için bu yöntemi çağırın.|
|[CPrivateObjectSecurityDesc::Create](#create)|Ayırın ve çağrı kaynak yöneticisi tarafından oluşturulan özel nesne kendine bağlı güvenlik tanımlayıcısı'nı başlatmak için bu yöntemi çağırın.|
|[CPrivateObjectSecurityDesc::Get](#get)|Özel bir nesnenin güvenlik tanımlayıcısından bilgileri almak için bu yöntemi çağırın.|
|[CPrivateObjectSecurityDesc::Set](#set)|Özel bir nesnenin güvenlik tanımlayıcısını değiştirmek için bu yöntemi çağırın.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işleç =](#operator_eq)|Atama işleci.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, türetilen [CSecurityDesc](../../atl/reference/csecuritydesc-class.md), oluşturmak ve özel bir nesnenin güvenlik tanımlayıcısını yönetme için yöntemleri sağlar.

Windows, erişim denetimi modeli için bir giriş için bkz [erişim denetimi](/windows/desktop/SecAuthZ/access-control) Windows SDK.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CSecurityDesc](../../atl/reference/csecuritydesc-class.md)

`CPrivateObjectSecurityDesc`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlsecurity.h

##  <a name="converttoautoinherit"></a>  CPrivateObjectSecurityDesc::ConvertToAutoInherit

Güvenlik tanımlayıcısı ve onun erişim denetim listelerini (ACL'ler) otomatik yayma devralınabilir erişim denetimi girişlerinin (ACE'ler) destekleyen bir biçime dönüştürmek için bu yöntemi çağırın.

```
bool ConvertToAutoInherit(
    const CSecurityDesc* pParent,
    GUID* ObjectType,
    bool bIsDirectoryObject,
    PGENERIC_MAPPING GenericMapping) throw();
```

### <a name="parameters"></a>Parametreler

*pParent*<br/>
İşaretçi bir [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) nesnenin üst kapsayıcısını başvuran nesne. Hiçbir üst kapsayıcı mevcut değilse bu parametre NULL olur.

*ObjectType*<br/>
İşaretçi bir `GUID` geçerli nesneyle ilişkili nesne türünü tanımlayan yapısı. Ayarlama *ObjectType* nesne bir GUID yoksa null.

*bIsDirectoryObject*<br/>
Yeni nesne diğer nesneleri içerip içeremeyeceğini belirtir. True değeri yeni nesneye bir kapsayıcı olduğunu gösterir. False değeri yeni nesneye bir kapsayıcı olmadığını gösterir.

*GenericMapping*<br/>
İşaretçi bir [GENERIC_MAPPING](/windows/desktop/api/winnt/ns-winnt-_generic_mapping) eşlemesi genel her nesne için belirli haklar sağdan belirtiyor yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem denemeleri ACE isteğe bağlı erişim denetimi listesinin (DACL) belirlemek için ve geçerli güvenlik tanımlayıcısının sistem erişim denetimi listesini (SACL) üst güvenlik tanımlayıcısı ' devralınan. Çağrı [ConvertToAutoInheritPrivateObjectSecurity](/windows/desktop/api/securitybaseapi/nf-securitybaseapi-converttoautoinheritprivateobjectsecurity) işlevi.

##  <a name="cprivateobjectsecuritydesc"></a>  CPrivateObjectSecurityDesc::CPrivateObjectSecurityDesc

Oluşturucu.

```
CPrivateObjectSecurityDesc() throw();
```

### <a name="remarks"></a>Açıklamalar

Başlatır `CPrivateObjectSecurityDesc` nesne.

##  <a name="dtor"></a>  CPrivateObjectSecurityDesc::~CPrivateObjectSecurityDesc

Yıkıcı.

```
~CPrivateObjectSecurityDesc() throw();
```

### <a name="remarks"></a>Açıklamalar

Yok edici ayrılan tüm kaynakları serbest bırakır ve özel bir nesnenin güvenlik tanımlayıcısını siler.

##  <a name="create"></a>  CPrivateObjectSecurityDesc::Create

Ayırın ve çağrı kaynak yöneticisi tarafından oluşturulan özel nesne kendine bağlı güvenlik tanımlayıcısı'nı başlatmak için bu yöntemi çağırın.

```
bool Create(
    const CSecurityDesc* pParent,
    const CSecurityDesc* pCreator,
    bool bIsDirectoryObject,
    const CAccessToken& Token,
    PGENERIC_MAPPING GenericMapping) throw();

bool Create(
    const CSecurityDesc* pParent,
    const CSecurityDesc* pCreator,
    GUID* ObjectType,
    bool bIsContainerObject,
    ULONG AutoInheritFlags,
    const CAccessToken& Token,
    PGENERIC_MAPPING GenericMapping) throw();
```

### <a name="parameters"></a>Parametreler

*pParent*<br/>
İşaretçi bir [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) başvuran üst dizini içinde yeni bir nesne oluşturulmakta olan nesne. Üst dizini yok ise NULL olarak ayarlayın.

*pCreator*<br/>
Nesnesinin oluşturucusu tarafından sağlanan bir güvenlik tanımlayıcısının işaretçisi. Nesnenin oluşturucusu yeni bir nesne için güvenlik bilgileri açıkça geçemezse, bu parametre NULL olarak ayarlayın.

*bIsDirectoryObject*<br/>
Yeni nesne diğer nesneleri içerip içeremeyeceğini belirtir. True değeri yeni nesneye bir kapsayıcı olduğunu gösterir. False değeri yeni nesneye bir kapsayıcı olmadığını gösterir.

*Belirteç*<br/>
Başvuru [CAccessToken](../../atl/reference/caccesstoken-class.md) adına nesnesi oluşturulurken istemci işlemi için nesne.

*GenericMapping*<br/>
İşaretçi bir [GENERIC_MAPPING](/windows/desktop/api/winnt/ns-winnt-_generic_mapping) eşlemesi genel her nesne için belirli haklar sağdan belirtiyor yapısı.

*ObjectType*<br/>
İşaretçi bir `GUID` geçerli nesneyle ilişkili nesne türünü tanımlayan yapısı. Ayarlama *ObjectType* nesne bir GUID yoksa null.

*bIsContainerObject*<br/>
Yeni nesne diğer nesneleri içerip içeremeyeceğini belirtir. True değeri yeni nesneye bir kapsayıcı olduğunu gösterir. False değeri yeni nesneye bir kapsayıcı olmadığını gösterir.

*AutoInheritFlags*<br/>
Erişim denetimi girdileri (ACE) öğesinden devralınan nasıl kontrol bit bayrakları kümesini *pParent*. Bkz: [CreatePrivateObjectSecurityEx](/windows/desktop/api/securitybaseapi/nf-securitybaseapi-createprivateobjectsecurityex) daha fazla ayrıntı için.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntemin çağırdığı [CreatePrivateObjectSercurity](/windows/desktop/api/securitybaseapi/nf-securitybaseapi-createprivateobjectsecurity) veya [CreatePrivateObjectSecurityEx](/windows/desktop/api/securitybaseapi/nf-securitybaseapi-createprivateobjectsecurityex).

İkinci yöntem yeni nesnenin nesne türü GUID belirterek veya ACE nasıl devralınır denetleme izin verir.

> [!NOTE]
>  Bitişik bir bellek bloğu içinde tüm güvenlik bilgilerini depolayan bir güvenlik tanımlayıcısı kendine bağlı güvenlik tanımlayıcısıdır.

##  <a name="get"></a>  CPrivateObjectSecurityDesc::Get

Özel bir nesnenin güvenlik tanımlayıcısından bilgileri almak için bu yöntemi çağırın.

```
bool Get(
    SECURITY_INFORMATION si,
    CSecurityDesc* pResult) const throw();
```

### <a name="parameters"></a>Parametreler

*sı*<br/>
Almak için güvenlik tanımlayıcısı bölümlerini gösteren bit bayrakları kümesini. Bu değer bir birleşimi olabilir [SECURITY_INFORMATION](/windows/desktop/SecAuthZ/security-information) bit bayrakları.

*pResult*<br/>
İşaretçi bir [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) nesnesini belirtilen güvenlik tanımlayıcısından istenen bilgilerin bir kopyasını alır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Güvenlik tanımlayıcısı yapısı ve güvenli kılınabilir nesne için güvenlik bilgilerini içeren ilişkili veri olduğu.

##  <a name="operator_eq"></a>  CPrivateObjectSecurityDesc::operator =

Atama işleci.

```
CPrivateObjectSecurityDesc& operator= (const CPrivateObjectSecurityDesc& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
`CPrivateObjectSecurityDesc` Nesne geçerli nesneye atamak için.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş döndürür `CPrivateObjectSecurityDesc` nesne.

##  <a name="set"></a>  CPrivateObjectSecurityDesc::Set

Özel bir nesnenin güvenlik tanımlayıcısını değiştirmek için bu yöntemi çağırın.

```
bool Set(
    SECURITY_INFORMATION si,
    const CSecurityDesc& Modification,
    PGENERIC_MAPPING GenericMapping,
    const CAccessToken& Token) throw();

bool Set(
    SECURITY_INFORMATION si,
    const CSecurityDesc& Modification,
    ULONG AutoInheritFlags,
    PGENERIC_MAPPING GenericMapping,
    const CAccessToken& Token) throw();
```

### <a name="parameters"></a>Parametreler

*sı*<br/>
Ayarlamak için güvenlik tanımlayıcısı bölümlerini gösteren bit bayrakları kümesini. Bu değer bir birleşimi olabilir [SECURITY_INFORMATION](/windows/desktop/SecAuthZ/security-information) bit bayrakları.

*Değiştirme*<br/>
İşaretçi bir [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) nesne. Bu güvenlik tanımlayıcısı bölümlerini gösterilen *sı* parametresi, nesnenin güvenlik tanımlayıcısına uygulanır.

*GenericMapping*<br/>
İşaretçi bir [GENERIC_MAPPING](/windows/desktop/api/winnt/ns-winnt-_generic_mapping) eşlemesi genel her nesne için belirli haklar sağdan belirtiyor yapısı.

*Belirteç*<br/>
Başvuru [CAccessToken](../../atl/reference/caccesstoken-class.md) adına nesnesi oluşturulurken istemci işlemi için nesne.

*AutoInheritFlags*<br/>
Erişim denetimi girdileri (ACE) öğesinden devralınan nasıl kontrol bit bayrakları kümesini *pParent*. Bkz: [CreatePrivateObjectSecurityEx](/windows/desktop/api/securitybaseapi/nf-securitybaseapi-createprivateobjectsecurityex) daha fazla ayrıntı için.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

İkinci yöntem, nesnenin nesne türü GUID belirterek veya ACE nasıl devralınır denetleme izin verir.

## <a name="see-also"></a>Ayrıca bkz.

[SECURITY_DESCRIPTOR](/windows/desktop/api/winnt/ns-winnt-_security_descriptor)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)<br/>
[Güvenlik Genel İşlevleri](../../atl/reference/security-global-functions.md)<br/>
[CSecurityDesc Sınıfı](../../atl/reference/csecuritydesc-class.md)
