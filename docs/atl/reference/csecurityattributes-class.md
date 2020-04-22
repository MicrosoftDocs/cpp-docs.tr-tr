---
title: CSecurityAttributes Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes::CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes::Set
helpviewer_keywords:
- CSecurityAttributes class
ms.assetid: a094880c-52e1-4a28-97ff-752d5869908e
ms.openlocfilehash: e0ac813008a028bb233adfb4c7409a0ad62a6b78
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81746497"
---
# <a name="csecurityattributes-class"></a>CSecurityAttributes Sınıfı

Bu sınıf, güvenlik öznitelikleri yapısı için ince bir sarıcıdır.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CSecurityAttributes : public SECURITY_ATTRIBUTES
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CSecurityAttributes::csecurityAttributes](#csecurityattributes)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CSecurityAttributes::Set](#set)|Nesnenin özniteliklerini ayarlamak `CSecurityAttributes` için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

Yapı, `SECURITY_ATTRIBUTES` bir nesnenin oluşturulması için kullanılan bir [güvenlik tanımlayıcısı](/windows/win32/api/winnt/ns-winnt-security_descriptor) içerir ve bu yapıyı belirterek alınan tutamacın devralınıp alınamayacağını belirtir.

Windows'daki erişim denetimi modeline giriş için Windows SDK'daki [Access Denetimi'ne](/windows/win32/SecAuthZ/access-control) bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`SECURITY_ATTRIBUTES`

`CSecurityAttributes`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity.h

## <a name="csecurityattributescsecurityattributes"></a><a name="csecurityattributes"></a>CSecurityAttributes::csecurityAttributes

Oluşturucu.

```
CSecurityAttributes() throw();
explicit CSecurityAttributes(const CSecurityDesc& rSecurityDescriptor, bool bInheritsHandle = false) throw(...);
```

### <a name="parameters"></a>Parametreler

*rSecurityDescriptor*<br/>
Güvenlik tanımlayıcısına başvuru.

*bInheritsHandle*<br/>
Yeni bir işlem oluşturulduğunda döndürülen tanıtıcının devralınıp alınmayacağını belirtir. Bu üye doğruysa, yeni işlem tanıtıcıyı devralır.

## <a name="csecurityattributesset"></a><a name="set"></a>CSecurityAttributes::Set

Nesnenin özniteliklerini ayarlamak `CSecurityAttributes` için bu yöntemi çağırın.

```cpp
void Set(const CSecurityDesc& rSecurityDescriptor, bool bInheritHandle = false) throw(...);
```

### <a name="parameters"></a>Parametreler

*rSecurityDescriptor*<br/>
Güvenlik tanımlayıcısına başvuru.

*bInheritHandle*<br/>
Yeni bir işlem oluşturulduğunda döndürülen tanıtıcının devralınıp alınmayacağını belirtir. Bu üye doğruysa, yeni işlem tanıtıcıyı devralır.

### <a name="remarks"></a>Açıklamalar

Bu `CSecurityAttributes` yöntem, nesneyi başlatmayı oluşturmak için kurucu tarafından kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[Güvenlik Örneği](../../overview/visual-cpp-samples.md)<br/>
[Securıty_attrıbutes](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\))<br/>
[güvenlik tanımlayıcısı](/windows/win32/api/winnt/ns-winnt-security_descriptor)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)<br/>
[Güvenlik Genel İşlevleri](../../atl/reference/security-global-functions.md)
