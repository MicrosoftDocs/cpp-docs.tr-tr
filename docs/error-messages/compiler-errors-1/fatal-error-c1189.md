---
title: Önemli hata C1189 | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C1189
dev_langs:
- C++
helpviewer_keywords:
- C1189
ms.assetid: 2e5c8a78-edd4-411c-b619-558a96be148a
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b49f227b5fda20ab0ba202d3d7eca99492509b35
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="fatal-error-c1189"></a>Önemli hata C1189

> **\#Hata:** *kullanıcı tarafından sağlanan hata iletisi*

## <a name="remarks"></a>Açıklamalar

C1189 tarafından oluşturulur `#error` yönergesi. Yönergesi kodları Geliştirici hata iletisinin metnini belirtir. Daha fazla bilgi için bkz: [#error yönergesi (C/C++)](../../preprocessor/hash-error-directive-c-cpp.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C1189 oluşturur. Örnekte, çünkü Geliştirici özel hata iletisi sorunları `_WIN32` tanımlayıcısı tanımlı değil:

```cpp
// C1189.cpp
#undef _WIN32
#if !defined(_WIN32)
#error _WIN32 must be defined   // C1189
#endif
```

## <a name="see-also"></a>Ayrıca bkz.

[#define Yönergesi (C/C++)](../../preprocessor/hash-define-directive-c-cpp.md)