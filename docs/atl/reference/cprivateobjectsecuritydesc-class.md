---
title: CPrivateObjectSecurityDesc Sınıfı
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
ms.openlocfilehash: 2fcfdfecab649b571047613ec0889b02d2c7a7a0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331418"
---
# <a name="cprivateobjectsecuritydesc-class"></a>CPrivateObjectSecurityDesc Sınıfı

Bu sınıf özel bir nesne güvenlik tanımlayıcı nesnesi temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CPrivateObjectSecurityDesc : public CSecurityDesc
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CPrivateObjectSecurityDesc::CPrivateObjectSecurityDesc](#cprivateobjectsecuritydesc)|Oluşturucu.|
|[CPrivateObjectSecurityDesc::~CPrivateObjectSecurityDesc](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CPrivateObjectSecurityDesc::ConvertToAutoInherit](#converttoautoinherit)|Bir güvenlik tanımlayıcısını ve erişim denetim listelerini (ALA'ları) devredilebilir erişim denetimi girişlerinin (ACE) otomatik olarak yayılmasını destekleyen bir biçime dönüştürmek için bu yöntemi arayın.|
|[CPrivateObjectSecurityDesc::Oluştur](#create)|Çağrı kaynağı yöneticisi tarafından oluşturulan özel nesne için kendi bağıl güvenlik tanımlayıcısı ayırmak ve başlatmak için bu yöntemi çağırın.|
|[CPrivateObjectSecurityDesc::Get](#get)|Özel bir nesnenin güvenlik tanımlayıcısından bilgi almak için bu yöntemi arayın.|
|[CPrivateObjectSecurityDesc::Set](#set)|Özel bir nesnenin güvenlik tanımlayıcısını değiştirmek için bu yöntemi çağırın.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işleç =](#operator_eq)|Atama işleci.|

## <a name="remarks"></a>Açıklamalar

[CSecurityDesc'ten](../../atl/reference/csecuritydesc-class.md)türetilen bu sınıf, özel bir nesnenin güvenlik tanımlayıcısını oluşturma ve yönetme yöntemleri sağlar.

Windows'daki erişim denetimi modeline giriş için Windows SDK'daki [Access Denetimi'ne](/windows/win32/SecAuthZ/access-control) bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Csecuritydesc](../../atl/reference/csecuritydesc-class.md)

`CPrivateObjectSecurityDesc`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity.h

## <a name="cprivateobjectsecuritydescconverttoautoinherit"></a><a name="converttoautoinherit"></a>CPrivateObjectSecurityDesc::ConvertToAutoInherit

Bir güvenlik tanımlayıcısını ve erişim denetim listelerini (ALA'ları) devredilebilir erişim denetimi girişlerinin (ACE) otomatik olarak yayılmasını destekleyen bir biçime dönüştürmek için bu yöntemi arayın.

```
bool ConvertToAutoInherit(
    const CSecurityDesc* pParent,
    GUID* ObjectType,
    bool bIsDirectoryObject,
    PGENERIC_MAPPING GenericMapping) throw();
```

### <a name="parameters"></a>Parametreler

*pParent*<br/>
Nesnenin üst kapsayıcısına başvuran [csecurityDesc](../../atl/reference/csecuritydesc-class.md) nesnesine işaretçi. Üst kapsayıcı yoksa, bu parametre NULL'dur.

*Nesnetürü*<br/>
Geçerli nesneyle ilişkili nesne türünü tanımlayan bir `GUID` yapıyı işaretçi. Nesnenin GUID'i yoksa *ObjectType'ı* NULL olarak ayarlayın.

*bIsDirectoryObject*<br/>
Yeni nesnenin diğer nesneleri içerip içeremeyeceğini belirtir. True değeri, yeni nesnenin bir kapsayıcı olduğunu gösterir. False değeri, yeni nesnenin kapsayıcı olmadığını gösterir.

*Genel Haritalama*<br/>
Her genel sağdan nesneiçin belirli haklara eşlemi belirten [GENERIC_MAPPING](/windows/win32/api/winnt/ns-winnt-generic_mapping) bir yapıyı işaretle.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, isteğe bağlı erişim denetim listesindeki (DACL) ve geçerli güvenlik tanımlayıcısının sistem erişim denetim listesindeki (SACL) ACE'lerin üst güvenlik tanımlayıcısından devralınıp alınmadığını belirlemeye çalışır. [ConvertToAutoInheritPrivateObjectSecurity](/windows/win32/api/securitybaseapi/nf-securitybaseapi-converttoautoinheritprivateobjectsecurity) işlevini çağırır.

## <a name="cprivateobjectsecuritydesccprivateobjectsecuritydesc"></a><a name="cprivateobjectsecuritydesc"></a>CPrivateObjectSecurityDesc::CPrivateObjectSecurityDesc

Oluşturucu.

```
CPrivateObjectSecurityDesc() throw();
```

### <a name="remarks"></a>Açıklamalar

Nesneyi baş `CPrivateObjectSecurityDesc` harfe doğru laştırır.

## <a name="cprivateobjectsecuritydesccprivateobjectsecuritydesc"></a><a name="dtor"></a>CPrivateObjectSecurityDesc::~CPrivateObjectSecurityDesc

Yıkıcı.

```
~CPrivateObjectSecurityDesc() throw();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı, ayrılan tüm kaynakları serbest böler ve özel nesnenin güvenlik tanımlayıcısını siler.

## <a name="cprivateobjectsecuritydesccreate"></a><a name="create"></a>CPrivateObjectSecurityDesc::Oluştur

Çağrı kaynağı yöneticisi tarafından oluşturulan özel nesne için kendi bağıl güvenlik tanımlayıcısı ayırmak ve başlatmak için bu yöntemi çağırın.

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
Yeni bir nesnenin oluşturulduğu üst dizine başvuran [csecurityDesc](../../atl/reference/csecuritydesc-class.md) nesnesine işaretçi. Üst dizini yoksa NULL olarak ayarlayın.

*pCreator*<br/>
Nesnenin oluşturucusu tarafından sağlanan bir güvenlik tanımlayıcısı işaretçisi. Nesnenin oluşturucusu yeni nesnenin güvenlik bilgilerini açıkça geçirmiyorsa, bu parametreyi NULL olarak ayarlayın.

*bIsDirectoryObject*<br/>
Yeni nesnenin diğer nesneleri içerip içeremeyeceğini belirtir. True değeri, yeni nesnenin bir kapsayıcı olduğunu gösterir. False değeri, yeni nesnenin kapsayıcı olmadığını gösterir.

*Belirte -ci*<br/>
Nesnenin oluşturulduğu istemci işlemi için [CAccessToken](../../atl/reference/caccesstoken-class.md) nesnesine başvuru.

*Genel Haritalama*<br/>
Her genel sağdan nesneiçin belirli haklara eşlemi belirten [GENERIC_MAPPING](/windows/win32/api/winnt/ns-winnt-generic_mapping) bir yapıyı işaretle.

*Nesnetürü*<br/>
Geçerli nesneyle ilişkili nesne türünü tanımlayan bir `GUID` yapıyı işaretçi. Nesnenin GUID'i yoksa *ObjectType'ı* NULL olarak ayarlayın.

*bIsContainerObject*<br/>
Yeni nesnenin diğer nesneleri içerip içeremeyeceğini belirtir. True değeri, yeni nesnenin bir kapsayıcı olduğunu gösterir. False değeri, yeni nesnenin kapsayıcı olmadığını gösterir.

*AutoInheritFlags*<br/>
Erişim denetimi girişlerinin (ACE'ler) *pParent'ten*nasıl devralını kontrol eden bit bayrakları kümesi. Daha fazla bilgi için [CreatePrivateObjectSecurityEx'e](/windows/win32/api/securitybaseapi/nf-securitybaseapi-createprivateobjectsecurityex) bakın.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem [CreatePrivateObjectSercurity](/windows/win32/api/securitybaseapi/nf-securitybaseapi-createprivateobjectsecurity) veya [CreatePrivateObjectSecurityEx](/windows/win32/api/securitybaseapi/nf-securitybaseapi-createprivateobjectsecurityex)çağırır.

İkinci yöntem, yeni nesnenin nesne türü GUID'ini belirtmeye veya ACE'lerin nasıl devraldığını denetlemeye izin verir.

> [!NOTE]
> Kendi kendine göreceli güvenlik tanımlayıcısı, tüm güvenlik bilgilerini bitişik bir bellek bloğunda depolayan bir güvenlik tanımlayıcısıdır.

## <a name="cprivateobjectsecuritydescget"></a><a name="get"></a>CPrivateObjectSecurityDesc::Get

Özel bir nesnenin güvenlik tanımlayıcısından bilgi almak için bu yöntemi arayın.

```
bool Get(
    SECURITY_INFORMATION si,
    CSecurityDesc* pResult) const throw();
```

### <a name="parameters"></a>Parametreler

*Si*<br/>
Alınacak güvenlik tanımlayıcısının bölümlerini gösteren bit bayrakları kümesi. Bu [değer, SECURITY_INFORMATION](/windows/win32/SecAuthZ/security-information) bit bayraklarının bir birleşimi olabilir.

*pResult*<br/>
Belirtilen güvenlik tanımlayıcısından istenen bilgilerin bir kopyasını alan [csecurityDesc](../../atl/reference/csecuritydesc-class.md) nesnesine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Güvenlik tanımlayıcısı, alınabilecek bir nesnenin güvenlik bilgilerini içeren bir yapı ve ilişkili veridir.

## <a name="cprivateobjectsecuritydescoperator-"></a><a name="operator_eq"></a>CPrivateObjectSecurityDesc::operatör =

Atama işleci.

```
CPrivateObjectSecurityDesc& operator= (const CPrivateObjectSecurityDesc& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*Rhs*<br/>
Geçerli `CPrivateObjectSecurityDesc` nesneye atayacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CPrivateObjectSecurityDesc` nesneyi döndürür.

## <a name="cprivateobjectsecuritydescset"></a><a name="set"></a>CPrivateObjectSecurityDesc::Set

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

*Si*<br/>
Ayarlanan güvenlik tanımlayıcısının bölümlerini gösteren bit bayrakları kümesi. Bu [değer, SECURITY_INFORMATION](/windows/win32/SecAuthZ/security-information) bit bayraklarının bir birleşimi olabilir.

*Değişiklik*<br/>
[CSecurityDesc](../../atl/reference/csecuritydesc-class.md) nesnesine işaretçi. Si parametresi ile gösterilen *si* bu güvenlik tanımlayıcısının bölümleri nesnenin güvenlik tanımlayıcısına uygulanır.

*Genel Haritalama*<br/>
Her genel sağdan nesneiçin belirli haklara eşlemi belirten [GENERIC_MAPPING](/windows/win32/api/winnt/ns-winnt-generic_mapping) bir yapıyı işaretle.

*Belirte -ci*<br/>
Nesnenin oluşturulduğu istemci işlemi için [CAccessToken](../../atl/reference/caccesstoken-class.md) nesnesine başvuru.

*AutoInheritFlags*<br/>
Erişim denetimi girişlerinin (ACE'ler) *pParent'ten*nasıl devralını kontrol eden bit bayrakları kümesi. Daha fazla bilgi için [CreatePrivateObjectSecurityEx'e](/windows/win32/api/securitybaseapi/nf-securitybaseapi-createprivateobjectsecurityex) bakın.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

İkinci yöntem, nesnenin GUID nesne türünü belirtmeye veya ACE'lerin nasıl devraldığını denetlemeye izin verir.

## <a name="see-also"></a>Ayrıca bkz.

[Securıty_descrıptor](/windows/win32/api/winnt/ns-winnt-security_descriptor)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)<br/>
[Güvenlik Genel İşlevleri](../../atl/reference/security-global-functions.md)<br/>
[CSecurityDesc Sınıfı](../../atl/reference/csecuritydesc-class.md)
