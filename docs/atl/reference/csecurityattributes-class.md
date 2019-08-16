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
ms.openlocfilehash: ebffbea120101a77450a5e8da3cdb6e34723e7be
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496494"
---
# <a name="csecurityattributes-class"></a>CSecurityAttributes sınıfı

Bu sınıf, güvenlik öznitelikleri yapısına yönelik ince bir sarmalayıcıdır.

> [!IMPORTANT]
>  Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

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
|[CSecurityAttributes:: set](#set)|`CSecurityAttributes` Nesnesinin özniteliklerini ayarlamak için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

Yapı, bir nesnenin oluşturulması için kullanılan bir [güvenlik tanımlayıcısı](/windows/win32/api/winnt/ns-winnt-security_descriptor) içerir ve bu yapıyı belirterek alınan tanıtıcının devralınıp alınmayacağını belirtir. `SECURITY_ATTRIBUTES`

Windows 'daki erişim denetim modeline giriş için Windows SDK [Access Control](/windows/win32/SecAuthZ/access-control) bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`SECURITY_ATTRIBUTES`

`CSecurityAttributes`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity. h

##  <a name="csecurityattributes"></a>CSecurityAttributes:: CSecurityAttributes

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

##  <a name="set"></a>CSecurityAttributes:: set

`CSecurityAttributes` Nesnesinin özniteliklerini ayarlamak için bu yöntemi çağırın.

```
void Set(const CSecurityDesc& rSecurityDescriptor, bool bInheritHandle = false) throw(...);
```

### <a name="parameters"></a>Parametreler

*rSecurityDescriptor*<br/>
Bir güvenlik tanımlayıcısına başvuru.

*bInheritHandle*<br/>
Yeni bir işlem oluşturulduğunda döndürülen tanıtıcının devralınıp alınmayacağını belirtir. Bu üye true ise, yeni işlem tanıtıcıyı devralır.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `CSecurityAttributes` nesneyi başlatmak için Oluşturucu tarafından kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[Güvenlik örneği](../../overview/visual-cpp-samples.md)<br/>
[SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\))<br/>
[Güvenlik tanımlayıcısı](/windows/win32/api/winnt/ns-winnt-security_descriptor)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[Güvenlik Genel İşlevleri](../../atl/reference/security-global-functions.md)
