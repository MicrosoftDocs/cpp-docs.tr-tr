---
title: Derleyici hatası C2432
ms.date: 11/04/2016
f1_keywords:
- C2432
helpviewer_keywords:
- C2432
ms.assetid: 0e3326e8-cab1-45a5-b48d-61edd33793e8
ms.openlocfilehash: d4234626bc246d6da87be68b03d44562dd5990ff
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744517"
---
# <a name="compiler-error-c2432"></a>Derleyici hatası C2432

' Identifier ' içinde 16-bit verilere geçersiz başvuru

16 bit kayıt, dizin veya temel kayıt olarak kullanılır. Derleyici 16 bit veriye başvurmayı desteklemez. 32 bit kod derlenirken, 16 bit Yazmaçları dizin veya temel kayıt olarak kullanılamaz.

Aşağıdaki örnek C2432 oluşturur:

```cpp
// C2432.cpp
// processor: x86
int main() {
   _asm mov eax, DWORD PTR [bx]   // C2432
}
```
