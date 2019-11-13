---
title: Derleyici Uyarısı (düzey 1) C4329
ms.date: 11/04/2016
f1_keywords:
- C4329
helpviewer_keywords:
- C4329
ms.assetid: 4316f51a-2c56-4b3f-831e-65d24b83b65c
ms.openlocfilehash: 0eb99d9ab6ac58f32013a8b50330f6139548f499
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966070"
---
# <a name="compiler-warning-level-1-c4329"></a>Derleyici Uyarısı (düzey 1) C4329

Enum üzerinde __declspec (align ()) yoksayılıyor

[__Declspec](../../cpp/declspec.md) değiştiricinin [align](../../cpp/align-cpp.md) anahtar sözcüğünün kullanılmasına `enum`izin verilmez. Aşağıdaki örnek C4329 oluşturur:

```cpp
// C4329.cpp
// compile with: /W1 /LD
enum __declspec(align(256)) TestEnum {   // C4329
   TESTVAL1,
   TESTVAL2,
   TESTVAL3
};
__declspec(align(256)) enum TestEnum1;
```