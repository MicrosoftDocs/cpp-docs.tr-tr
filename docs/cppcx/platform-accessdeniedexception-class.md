---
description: 'Daha fazla bilgi edinin: Platform:: AccessDeniedException Oluşturucusu sınıfı'
title: 'Platform:: AccessDeniedException Oluşturucusu sınıfı'
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::AccessDeniedException
- VCCORLIB/Platform::AccessDeniedException::AccessDeniedException
helpviewer_keywords:
- Platform::AccessDeniedException
ms.assetid: 6ae2155b-7b16-4587-8d2d-da05eab4c7e9
ms.openlocfilehash: 2dd1e543093000521bceb0abed128a1dac27a6e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276796"
---
# <a name="platformaccessdeniedexception-class"></a>Platform:: AccessDeniedException Oluşturucusu sınıfı

Bir kaynağa veya özelliğe erişim reddedildiğinde oluşturulur.

## <a name="syntax"></a>Syntax

```cpp
public ref class AccessDeniedException : COMException,    IException,    IPrintable,   IEquatable
```

### <a name="remarks"></a>Açıklamalar

Bu özel duruma ulaşırsanız, uygun yeteneği istemiş olduğunuzdan ve uygulamanızın paket bildiriminde gerekli bildirimleri oluşturduğunuzdan emin olun. Daha fazla bilgi için bkz. [COMException](../cppcx/platform-comexception-class.md) sınıfı.

### <a name="requirements"></a>Gereksinimler

**Desteklenen en düşük istemci:** Windows 8

**Desteklenen en düşük sunucu:** Windows Server 2012

**Ad alanı:** Platformunun

**Meta veri:** platform. winmd

## <a name="see-also"></a>Ayrıca bkz.

[Platform:: COMException sınıfı](../cppcx/platform-comexception-class.md)
