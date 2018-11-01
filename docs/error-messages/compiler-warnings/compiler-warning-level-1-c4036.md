---
title: Derleyici Uyarısı (düzey 1) C4036
ms.date: 11/04/2016
f1_keywords:
- C4036
helpviewer_keywords:
- C4036
ms.assetid: f0b15359-4d62-48ec-8cb1-a7b36587a47f
ms.openlocfilehash: 632e88bb64568c97e937e83e177598054a954f22
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50609579"
---
# <a name="compiler-warning-level-1-c4036"></a>Derleyici Uyarısı (düzey 1) C4036

'type' gerçek parametre olarak adsız

Yapı, birleşim, sabit listesi veya gerçek bir parametre olarak kullanılan sınıf için hiçbir tür adı verilir. Kullanıyorsanız [/Zg](../../build/reference/zg-generate-function-prototypes.md) işlev prototipleri üret, derleyici bu uyarı ve açıklamaları çıkış oluşturulan prototipteki biçimsel parametresi verir.

Bu uyarıyı çözmek için bir tür adı belirtin.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4036 oluşturur.

```
// C4036.c
// compile with: /Zg /W1
// D9035 expected
typedef struct { int i; } T;
void f(T* t) {}   // C4036

// OK
typedef struct MyStruct { int i; } T2;
void f2(T2 * t) {}
```