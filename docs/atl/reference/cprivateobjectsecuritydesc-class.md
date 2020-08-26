---
title: CPrivateObjectSecurityDesc sınıfı
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
ms.openlocfilehash: f62d289418280a05f390bf9cdec23ea30632aed2
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833510"
---
# <a name="cprivateobjectsecuritydesc-class"></a>CPrivateObjectSecurityDesc sınıfı

Bu sınıf bir özel nesne güvenlik tanımlayıcısı nesnesini temsil eder.

## <a name="syntax"></a>Syntax

```
class CPrivateObjectSecurityDesc : public CSecurityDesc
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CPrivateObjectSecurityDesc:: CPrivateObjectSecurityDesc](#cprivateobjectsecuritydesc)|Oluşturucu.|
|[CPrivateObjectSecurityDesc:: ~ CPrivateObjectSecurityDesc](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CPrivateObjectSecurityDesc:: Converttooto Inherit](#converttoautoinherit)|Bir güvenlik tanımlayıcısını ve erişim denetimi listelerini (ACL 'Ler), devralınabilir erişim denetimi girişlerinin (ACE 'Ler) otomatik yayılmasını destekleyen bir biçime dönüştürmek için bu yöntemi çağırın.|
|[CPrivateObjectSecurityDesc:: Create](#create)|Çağıran Resource Manager tarafından oluşturulan özel nesne için kendine göreli bir güvenlik tanımlayıcısı ayırmak ve başlatmak için bu yöntemi çağırın.|
|[CPrivateObjectSecurityDesc:: Get](#get)|Özel bir nesnenin güvenlik tanımlayıcısından bilgi almak için bu yöntemi çağırın.|
|[CPrivateObjectSecurityDesc:: set](#set)|Bir özel nesnenin güvenlik tanımlayıcısını değiştirmek için bu yöntemi çağırın.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç =](#operator_eq)|Atama işleci.|

## <a name="remarks"></a>Açıklamalar

[CSecurityDesc](../../atl/reference/csecuritydesc-class.md)öğesinden türetilen bu sınıf, özel bir nesnenin güvenlik tanımlayıcısını oluşturmak ve yönetmek için yöntemler sağlar.

Windows 'daki erişim denetim modeline giriş için Windows SDK [Access Control](/windows/win32/SecAuthZ/access-control) bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CSecurityDesc](../../atl/reference/csecuritydesc-class.md)

`CPrivateObjectSecurityDesc`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity. h

## <a name="cprivateobjectsecuritydescconverttoautoinherit"></a><a name="converttoautoinherit"></a> CPrivateObjectSecurityDesc:: Converttooto Inherit

Bir güvenlik tanımlayıcısını ve erişim denetimi listelerini (ACL 'Ler), devralınabilir erişim denetimi girişlerinin (ACE 'Ler) otomatik yayılmasını destekleyen bir biçime dönüştürmek için bu yöntemi çağırın.

```
bool ConvertToAutoInherit(
    const CSecurityDesc* pParent,
    GUID* ObjectType,
    bool bIsDirectoryObject,
    PGENERIC_MAPPING GenericMapping) throw();
```

### <a name="parameters"></a>Parametreler

*pParent*<br/>
Nesnenin üst kapsayıcısına başvuran bir [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) nesnesine yönelik işaretçi. Üst kapsayıcı yoksa, bu parametre NULL olur.

*Nesne*<br/>
`GUID`Geçerli nesneyle ilişkili nesne türünü tanımlayan bir yapıya yönelik işaretçi. Nesne bir GUID içermiyorsa *ObjectType* öğesini null olarak ayarlayın.

*Bıdirectoryobject*<br/>
Yeni nesnenin diğer nesneleri içerip içeremeyeceğini belirtir. True değeri, yeni nesnenin bir kapsayıcı olduğunu gösterir. False değeri, yeni nesnenin bir kapsayıcı olmadığını gösterir.

*GenericMapping*<br/>
Nesne için her genel sağdan belirli haklara olan eşlemeyi belirten [GENERIC_MAPPING](/windows/win32/api/winnt/ns-winnt-generic_mapping) yapısına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, geçerli güvenlik tanımlayıcısının isteğe bağlı erişim denetimi listesi (DACL) ve sistem erişim denetimi listesi (SACL) içindeki Ace 'lerden üst güvenlik tanımlayıcısından devralınıp alınmayacağını saptamaya çalışır. [Converttooto ınherprınesnegüvenliği](/windows/win32/api/securitybaseapi/nf-securitybaseapi-converttoautoinheritprivateobjectsecurity) işlevini çağırır.

## <a name="cprivateobjectsecuritydesccprivateobjectsecuritydesc"></a><a name="cprivateobjectsecuritydesc"></a> CPrivateObjectSecurityDesc:: CPrivateObjectSecurityDesc

Oluşturucu.

```
CPrivateObjectSecurityDesc() throw();
```

### <a name="remarks"></a>Açıklamalar

Nesnesini başlatır `CPrivateObjectSecurityDesc` .

## <a name="cprivateobjectsecuritydesccprivateobjectsecuritydesc"></a><a name="dtor"></a> CPrivateObjectSecurityDesc:: ~ CPrivateObjectSecurityDesc

Yok edicisi.

```
~CPrivateObjectSecurityDesc() throw();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı, ayrılan tüm kaynakları serbest bırakır ve özel nesnenin güvenlik tanımlayıcısını siler.

## <a name="cprivateobjectsecuritydesccreate"></a><a name="create"></a> CPrivateObjectSecurityDesc:: Create

Çağıran Resource Manager tarafından oluşturulan özel nesne için kendine göreli bir güvenlik tanımlayıcısı ayırmak ve başlatmak için bu yöntemi çağırın.

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
Yeni bir nesnenin oluşturulduğu üst dizine başvuran bir [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) nesnesine yönelik işaretçi. Üst dizin yoksa, NULL olarak ayarlayın.

*pCreator*<br/>
Nesnenin oluşturucusu tarafından belirtilen bir güvenlik tanımlayıcısına yönelik işaretçi. Nesnenin Oluşturucusu yeni nesne için güvenlik bilgilerini açıkça geçirmezse, bu parametreyi NULL olarak ayarlayın.

*Bıdirectoryobject*<br/>
Yeni nesnenin diğer nesneleri içerip içeremeyeceğini belirtir. True değeri, yeni nesnenin bir kapsayıcı olduğunu gösterir. False değeri, yeni nesnenin bir kapsayıcı olmadığını gösterir.

*Belirteç*<br/>
Adına nesnesi oluşturulmakta olan istemci işlemi için [CAccessToken](../../atl/reference/caccesstoken-class.md) nesnesine başvuru.

*GenericMapping*<br/>
Nesne için her genel sağdan belirli haklara olan eşlemeyi belirten [GENERIC_MAPPING](/windows/win32/api/winnt/ns-winnt-generic_mapping) yapısına yönelik işaretçi.

*Nesne*<br/>
`GUID`Geçerli nesneyle ilişkili nesne türünü tanımlayan bir yapıya yönelik işaretçi. Nesne bir GUID içermiyorsa *ObjectType* öğesini null olarak ayarlayın.

*Bıcontainerobject*<br/>
Yeni nesnenin diğer nesneleri içerip içeremeyeceğini belirtir. True değeri, yeni nesnenin bir kapsayıcı olduğunu gösterir. False değeri, yeni nesnenin bir kapsayıcı olmadığını gösterir.

*Oto devralma bayrakları*<br/>
Erişim denetimi girişlerinin (ACE 'Ler) *pParent*'dan nasıl devralındığını denetleyen bir bit bayrakları kümesi. Daha fazla ayrıntı için bkz. [CreatePrivateObjectSecurityEx](/windows/win32/api/securitybaseapi/nf-securitybaseapi-createprivateobjectsecurityex) .

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem [CreatePrivateObjectSercurity](/windows/win32/api/securitybaseapi/nf-securitybaseapi-createprivateobjectsecurity) veya [CreatePrivateObjectSecurityEx](/windows/win32/api/securitybaseapi/nf-securitybaseapi-createprivateobjectsecurityex)öğesini çağırır.

İkinci yöntem, yeni nesnenin nesne türü GUID 'INI belirtmeye veya Ace 'Leri nasıl devralındığını denetlemeye izin verir.

> [!NOTE]
> Kendi kendine göreli güvenlik tanımlayıcısı, tüm güvenlik bilgilerini ardışık bir bellek bloğunda depolayan bir güvenlik tanımlayıcısıdır.

## <a name="cprivateobjectsecuritydescget"></a><a name="get"></a> CPrivateObjectSecurityDesc:: Get

Özel bir nesnenin güvenlik tanımlayıcısından bilgi almak için bu yöntemi çağırın.

```
bool Get(
    SECURITY_INFORMATION si,
    CSecurityDesc* pResult) const throw();
```

### <a name="parameters"></a>Parametreler

*ortası*<br/>
Alınacak güvenlik tanımlayıcısının parçalarını gösteren bir bit bayrakları kümesi. Bu değer [SECURITY_INFORMATION](/windows/win32/SecAuthZ/security-information) bit bayraklarının bir birleşimi olabilir.

*pResult*<br/>
Belirtilen güvenlik tanımlayıcısından istenen bilgilerin bir kopyasını alan bir [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) nesnesi işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Güvenlik tanımlayıcısı, güvenli kılınabilir bir nesne için güvenlik bilgilerini içeren bir yapıdır ve ilişkili bir veri.

## <a name="cprivateobjectsecuritydescoperator-"></a><a name="operator_eq"></a> CPrivateObjectSecurityDesc:: operator =

Atama işleci.

```
CPrivateObjectSecurityDesc& operator= (const CPrivateObjectSecurityDesc& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*sağ taraftan*<br/>
`CPrivateObjectSecurityDesc`Geçerli nesneye atanacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş nesneyi döndürür `CPrivateObjectSecurityDesc` .

## <a name="cprivateobjectsecuritydescset"></a><a name="set"></a> CPrivateObjectSecurityDesc:: set

Bir özel nesnenin güvenlik tanımlayıcısını değiştirmek için bu yöntemi çağırın.

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

*ortası*<br/>
Ayarlanacak güvenlik tanımlayıcısının parçalarını gösteren bir bit bayrakları kümesi. Bu değer [SECURITY_INFORMATION](/windows/win32/SecAuthZ/security-information) bit bayraklarının bir birleşimi olabilir.

*Değişiklik*<br/>
[CSecurityDesc](../../atl/reference/csecuritydesc-class.md) nesnesine yönelik işaretçi. Bu güvenlik tanımlayıcısının, *sı* parametresi tarafından belirtilen kısımları nesnenin güvenlik tanımlayıcısına uygulanır.

*GenericMapping*<br/>
Nesne için her genel sağdan belirli haklara olan eşlemeyi belirten [GENERIC_MAPPING](/windows/win32/api/winnt/ns-winnt-generic_mapping) yapısına yönelik işaretçi.

*Belirteç*<br/>
Adına nesnesi oluşturulmakta olan istemci işlemi için [CAccessToken](../../atl/reference/caccesstoken-class.md) nesnesine başvuru.

*Oto devralma bayrakları*<br/>
Erişim denetimi girişlerinin (ACE 'Ler) *pParent*'dan nasıl devralındığını denetleyen bir bit bayrakları kümesi. Daha fazla ayrıntı için bkz. [CreatePrivateObjectSecurityEx](/windows/win32/api/securitybaseapi/nf-securitybaseapi-createprivateobjectsecurityex) .

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

İkinci yöntem, nesnenin nesne türü GUID 'INI belirtmeye veya Ace 'Leri nasıl devralındığını denetlemeye izin verir.

## <a name="see-also"></a>Ayrıca bkz.

[SECURITY_DESCRIPTOR](/windows/win32/api/winnt/ns-winnt-security_descriptor)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[Güvenlik Genel Işlevleri](../../atl/reference/security-global-functions.md)<br/>
[CSecurityDesc sınıfı](../../atl/reference/csecuritydesc-class.md)
