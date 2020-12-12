---
description: 'Daha fazla bilgi edinin: önemli hata C1189'
title: Önemli hata C1189
ms.date: 04/27/2018
f1_keywords:
- C1189
helpviewer_keywords:
- C1189
ms.assetid: 2e5c8a78-edd4-411c-b619-558a96be148a
ms.openlocfilehash: 4e71903c6567aedf85de81db59b66e45684d8507
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123597"
---
# <a name="fatal-error-c1189"></a>Önemli hata C1189

> **\# hata:** *Kullanıcı tarafından sağlanan hata iletisi*

## <a name="remarks"></a>Açıklamalar

C1189, yönergesi tarafından oluşturulur `#error` . Yönergeyi kodlayan geliştirici hata iletisinin metnini belirtir. Daha fazla bilgi için bkz. [#error yönergesi (C/C++)](../../preprocessor/hash-error-directive-c-cpp.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C1189 oluşturur. Örnekte, geliştirici özel bir hata iletisi yayınlar çünkü `_WIN32` tanımlayıcı tanımlı değil:

```cpp
// C1189.cpp
#undef _WIN32
#if !defined(_WIN32)
#error _WIN32 must be defined   // C1189
#endif
```

## <a name="see-also"></a>Ayrıca bkz.

[#define yönergesi (C/C++)](../../preprocessor/hash-define-directive-c-cpp.md)
