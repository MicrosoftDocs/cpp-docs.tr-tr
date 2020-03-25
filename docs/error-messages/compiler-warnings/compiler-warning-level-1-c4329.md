---
title: Derleyici Uyarısı (düzey 1) C4329
ms.date: 11/04/2016
f1_keywords:
- C4329
helpviewer_keywords:
- C4329
ms.assetid: 4316f51a-2c56-4b3f-831e-65d24b83b65c
ms.openlocfilehash: e8ef8c75a5e065f4f1679219d0d5fe57e5cfe86c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80162965"
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
