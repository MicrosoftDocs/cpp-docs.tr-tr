---
title: Platform::AccessDeniedException sınıfı
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::AccessDeniedException
- VCCORLIB/Platform::AccessDeniedException::AccessDeniedException
helpviewer_keywords:
- Platform::AccessDeniedException
ms.assetid: 6ae2155b-7b16-4587-8d2d-da05eab4c7e9
ms.openlocfilehash: 4abbac977a256ff27f99caaf77393450d3ccf858
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62161777"
---
# <a name="platformaccessdeniedexception-class"></a>Platform::AccessDeniedException sınıfı

Özel bir kaynağa eriştiğinizde veya özellik engellendi.

## <a name="syntax"></a>Sözdizimi

```cpp
public ref class AccessDeniedException : COMException,    IException,    IPrintable,   IEquatable
```

### <a name="remarks"></a>Açıklamalar

Bu özel durumu, istenen uygun özellik ve gerekli bildirimleri uygulama paketi bildiriminde yapılan emin olun. Daha fazla bilgi için [COMException](../cppcx/platform-comexception-class.md) sınıfı.

### <a name="requirements"></a>Gereksinimler

**En düşük desteklenen istemci:** Windows 8

**Sunucu desteklenen en düşük:** Windows Server 2012

**Namespace:** Platform

**Meta veri:** platform.winmd

## <a name="see-also"></a>Ayrıca bkz.

[Platform::COMException Sınıfı](../cppcx/platform-comexception-class.md)
