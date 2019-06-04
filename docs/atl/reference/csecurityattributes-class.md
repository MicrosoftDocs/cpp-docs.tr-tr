---
title: CSecurityAttributes sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes::CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes::Set
helpviewer_keywords:
- CSecurityAttributes class
ms.assetid: a094880c-52e1-4a28-97ff-752d5869908e
ms.openlocfilehash: b26de7a2a3426ed2fe86bd7ef50f6c5410fa5364
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66503204"
---
# <a name="csecurityattributes-class"></a>CSecurityAttributes sınıfı

Güvenlik öznitelikleri yapısı için basit bir sarmalayıcı sınıftır.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CSecurityAttributes : public SECURITY_ATTRIBUTES
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSecurityAttributes::CSecurityAttributes](#csecurityattributes)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSecurityAttributes::Set](#set)|Öznitelikleri ayarlamak için bu yöntemi çağırın `CSecurityAttributes` nesne.|

## <a name="remarks"></a>Açıklamalar

`SECURITY_ATTRIBUTES` Yapısının bir [güvenlik tanımlayıcısı](/windows/desktop/api/winnt/ns-winnt-_security_descriptor) bir nesne oluşturmak için kullanılan ve bu yapı belirterek alınan tanıtıcı devralınabilir olup olmadığını belirtir.

Windows, erişim denetimi modeli için bir giriş için bkz [erişim denetimi](/windows/desktop/SecAuthZ/access-control) Windows SDK.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`SECURITY_ATTRIBUTES`

`CSecurityAttributes`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlsecurity.h

##  <a name="csecurityattributes"></a>  CSecurityAttributes::CSecurityAttributes

Oluşturucu.

```
CSecurityAttributes() throw();
explicit CSecurityAttributes(const CSecurityDesc& rSecurityDescriptor, bool bInheritsHandle = false) throw(...);
```

### <a name="parameters"></a>Parametreler

*rSecurityDescriptor*<br/>
Bir güvenlik tanımlayıcısının başvuru.

*bInheritsHandle*<br/>
Yeni bir işlem oluşturulurken döndürülen tanıtıcının devralınan olup olmadığını belirtir. Bu üye true ise, yeni işlem tanıtıcısı devralır.

##  <a name="set"></a>  CSecurityAttributes::Set

Öznitelikleri ayarlamak için bu yöntemi çağırın `CSecurityAttributes` nesne.

```
void Set(const CSecurityDesc& rSecurityDescriptor, bool bInheritHandle = false) throw(...);
```

### <a name="parameters"></a>Parametreler

*rSecurityDescriptor*<br/>
Bir güvenlik tanımlayıcısının başvuru.

*bInheritHandle*<br/>
Yeni bir işlem oluşturulurken döndürülen tanıtıcının devralınan olup olmadığını belirtir. Bu üye true ise, yeni işlem tanıtıcısı devralır.

### <a name="remarks"></a>Açıklamalar

Bu yöntem başlatmak için oluşturucu tarafından kullanılan `CSecurityAttributes` nesne.

## <a name="see-also"></a>Ayrıca bkz.

[Güvenliği örneği](../../overview/visual-cpp-samples.md)<br/>
[SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\))<br/>
[Güvenlik tanımlayıcısı](/windows/desktop/api/winnt/ns-winnt-_security_descriptor)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)<br/>
[Güvenlik Genel İşlevleri](../../atl/reference/security-global-functions.md)
