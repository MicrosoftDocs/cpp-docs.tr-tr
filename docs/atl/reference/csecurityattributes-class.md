---
description: 'Daha fazla bilgi edinin: CSecurityAttributes sınıfı'
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
ms.openlocfilehash: 8cb772e574aef4ad941feef1cb838fb91d937576
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140822"
---
# <a name="csecurityattributes-class"></a>CSecurityAttributes sınıfı

Bu sınıf, güvenlik öznitelikleri yapısına yönelik ince bir sarmalayıcıdır.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Syntax

```
class CSecurityAttributes : public SECURITY_ATTRIBUTES
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSecurityAttributes:: CSecurityAttributes](#csecurityattributes)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSecurityAttributes:: set](#set)|Nesnesinin özniteliklerini ayarlamak için bu yöntemi çağırın `CSecurityAttributes` .|

## <a name="remarks"></a>Açıklamalar

`SECURITY_ATTRIBUTES`Yapı, bir nesnenin oluşturulması için kullanılan bir [güvenlik tanımlayıcısı](/windows/win32/api/winnt/ns-winnt-security_descriptor) içerir ve bu yapıyı belirterek alınan tanıtıcının devralınıp alınmayacağını belirtir.

Windows 'daki erişim denetim modeline giriş için Windows SDK [Access Control](/windows/win32/SecAuthZ/access-control) bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`SECURITY_ATTRIBUTES`

`CSecurityAttributes`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity. h

## <a name="csecurityattributescsecurityattributes"></a><a name="csecurityattributes"></a> CSecurityAttributes:: CSecurityAttributes

Oluşturucu.

```
CSecurityAttributes() throw();
explicit CSecurityAttributes(const CSecurityDesc& rSecurityDescriptor, bool bInheritsHandle = false) throw(...);
```

### <a name="parameters"></a>Parametreler

*rSecurityDescriptor*<br/>
Bir güvenlik tanımlayıcısına başvuru.

*bInheritsHandle*<br/>
Yeni bir işlem oluşturulduğunda döndürülen tanıtıcının devralınıp alınmayacağını belirtir. Bu üye true ise, yeni işlem tanıtıcıyı devralır.

## <a name="csecurityattributesset"></a><a name="set"></a> CSecurityAttributes:: set

Nesnesinin özniteliklerini ayarlamak için bu yöntemi çağırın `CSecurityAttributes` .

```cpp
void Set(const CSecurityDesc& rSecurityDescriptor, bool bInheritHandle = false) throw(...);
```

### <a name="parameters"></a>Parametreler

*rSecurityDescriptor*<br/>
Bir güvenlik tanımlayıcısına başvuru.

*bInheritHandle*<br/>
Yeni bir işlem oluşturulduğunda döndürülen tanıtıcının devralınıp alınmayacağını belirtir. Bu üye true ise, yeni işlem tanıtıcıyı devralır.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, nesneyi başlatmak için Oluşturucu tarafından kullanılır `CSecurityAttributes` .

## <a name="see-also"></a>Ayrıca bkz.

[Güvenlik örneği](../../overview/visual-cpp-samples.md)<br/>
[SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\))<br/>
[Güvenlik tanımlayıcısı](/windows/win32/api/winnt/ns-winnt-security_descriptor)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[Güvenlik Genel Işlevleri](../../atl/reference/security-global-functions.md)
