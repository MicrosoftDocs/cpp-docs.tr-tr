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
ms.openlocfilehash: 66188a2c944379cfae813220937ac1e7e98fb41d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62278039"
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
[SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560)<br/>
[Güvenlik tanımlayıcısı](/windows/desktop/api/winnt/ns-winnt-_security_descriptor)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)<br/>
[Güvenlik Genel İşlevleri](../../atl/reference/security-global-functions.md)
