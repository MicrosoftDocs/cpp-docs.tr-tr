---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4366'
title: Derleyici Uyarısı (düzey 4) C4366
ms.date: 11/04/2016
f1_keywords:
- C4366
helpviewer_keywords:
- C4366
ms.assetid: 65d2942f-3741-42f4-adf2-4920d5a055ca
ms.openlocfilehash: 9fa703d64ca48090d3bf6c2f5d9e21668d9acd71
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330595"
---
# <a name="compiler-warning-level-4-c4366"></a>Derleyici Uyarısı (düzey 4) C4366

Birli ' operator ' işlecinin sonucu hizalanmamış olabilir

Bir yapı üyesi paketleme nedeniyle hiç hizalanmazsa, söz konusu üyenin adresi hizalanmış bir işaretçiye atandığında derleyici uyarır. Varsayılan olarak, tüm işaretçiler hizalanır.

C4366 çözümlemek için yapının hizalamasını değiştirin ya da işaretçiyi [__unaligned](../../cpp/unaligned.md) anahtar sözcüğüyle bildirin.

Daha fazla bilgi için bkz. __unaligned ve [Pack](../../preprocessor/pack.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C4366 oluşturur.

```cpp
// C4366.cpp
// compile with: /W4 /c
// processor: IPF x64
#pragma pack(1)
struct X {
   short s1;
   int s2;
};

int main() {
   X x;
   short * ps1 = &x.s1;   // OK
   int * ps2 = &x.s2;   // C4366
}
```
