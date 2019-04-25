---
title: Önemli hata C1189
ms.date: 04/27/2018
f1_keywords:
- C1189
helpviewer_keywords:
- C1189
ms.assetid: 2e5c8a78-edd4-411c-b619-558a96be148a
ms.openlocfilehash: 06d42316a0109ac063bba43cefebd9aab71c2e72
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62229065"
---
# <a name="fatal-error-c1189"></a>Önemli hata C1189

> **\#Hata:** *kullanıcı tarafından sağlanan hata iletisi*

## <a name="remarks"></a>Açıklamalar

Tarafından oluşturulan C1189 `#error` yönergesi. Yönerge kodları geliştiriciye hata iletisinin metni belirtir. Daha fazla bilgi için [#error yönergesi (C/C++)](../../preprocessor/hash-error-directive-c-cpp.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C1189 oluşturur. Aşağıdaki örnekte, çünkü Geliştirici özel hata iletisi sorunlarını `_WIN32` tanımlayıcı tanımlı değil:

```cpp
// C1189.cpp
#undef _WIN32
#if !defined(_WIN32)
#error _WIN32 must be defined   // C1189
#endif
```

## <a name="see-also"></a>Ayrıca bkz.

[#define Yönergesi (C/C++)](../../preprocessor/hash-define-directive-c-cpp.md)