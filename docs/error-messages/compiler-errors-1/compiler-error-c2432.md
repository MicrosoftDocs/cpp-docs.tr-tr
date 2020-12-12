---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2432'
title: Derleyici hatası C2432
ms.date: 11/04/2016
f1_keywords:
- C2432
helpviewer_keywords:
- C2432
ms.assetid: 0e3326e8-cab1-45a5-b48d-61edd33793e8
ms.openlocfilehash: 392108e0fd16952bc8bcf43682dc163c664171ea
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190022"
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
