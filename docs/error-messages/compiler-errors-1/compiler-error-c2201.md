---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2201'
title: Derleyici hatası C2201
ms.date: 11/04/2016
f1_keywords:
- C2201
helpviewer_keywords:
- C2201
ms.assetid: ed927659-6e9c-447d-9963-19969ae1e957
ms.openlocfilehash: 334a459a6fbfa930c99e3c203b1fb214cb36706a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319007"
---
# <a name="compiler-error-c2201"></a>Derleyici hatası C2201

' tanımlayıcı ': içeri/içeri aktarılabilmek için dış bağlantı olmalıdır

İçe aktarılmış tanımlayıcı **`static`** .

Aşağıdaki örnek C2286 oluşturur:

```cpp
// C2201.cpp
// compile with: /c
__declspec(dllexport) static void func() {}   // C2201 func() is static
__declspec(dllexport) void func2() {}   // OK
```

## <a name="see-also"></a>Ayrıca bkz.

[Bağlantı Türleri](../../cpp/program-and-linkage-cpp.md)
