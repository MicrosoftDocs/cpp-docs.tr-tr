---
title: Önemli hata C1189
ms.date: 04/27/2018
f1_keywords:
- C1189
helpviewer_keywords:
- C1189
ms.assetid: 2e5c8a78-edd4-411c-b619-558a96be148a
ms.openlocfilehash: 2217b865109cc48151e4e96b2d38b88764c0c64f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80203662"
---
# <a name="fatal-error-c1189"></a>Önemli hata C1189

> **\#hatası:** *Kullanıcı tarafından sağlanan hata iletisi*

## <a name="remarks"></a>Açıklamalar

C1189, `#error` yönergesi tarafından oluşturulur. Yönergeyi kodlayan geliştirici hata iletisinin metnini belirtir. Daha fazla bilgi için bkz. [#error yönergesi (CC++/)](../../preprocessor/hash-error-directive-c-cpp.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C1189 oluşturur. Örnekte, geliştirici özel bir hata iletisi yayınlar çünkü `_WIN32` tanımlayıcısı tanımlı değil:

```cpp
// C1189.cpp
#undef _WIN32
#if !defined(_WIN32)
#error _WIN32 must be defined   // C1189
#endif
```

## <a name="see-also"></a>Ayrıca bkz.

[#define Yönergesi (C/C++)](../../preprocessor/hash-define-directive-c-cpp.md)
