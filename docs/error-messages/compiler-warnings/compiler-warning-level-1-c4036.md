---
title: Derleyici Uyarısı (düzey 1) C4036
ms.date: 11/04/2016
f1_keywords:
- C4036
helpviewer_keywords:
- C4036
ms.assetid: f0b15359-4d62-48ec-8cb1-a7b36587a47f
ms.openlocfilehash: 812f36884d24ac988353dbcb18609d4c506e3110
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80164267"
---
# <a name="compiler-warning-level-1-c4036"></a>Derleyici Uyarısı (düzey 1) C4036

gerçek parametre olarak adlandırılmamış ' Type '

Bir yapı, birleşim, numaralandırma veya gerçek parametre olarak kullanılan sınıf için tür adı verilmedi. İşlev prototipleri oluşturmak için [/zg](../../build/reference/zg-generate-function-prototypes.md) kullanıyorsanız, derleyici bu uyarıyı ve oluşturulan prototipteki biçimsel parametreyi dışarı açıklamayı verir.

Bu uyarıyı çözmek için bir tür adı belirtin.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4036 oluşturur.

```c
// C4036.c
// compile with: /Zg /W1
// D9035 expected
typedef struct { int i; } T;
void f(T* t) {}   // C4036

// OK
typedef struct MyStruct { int i; } T2;
void f2(T2 * t) {}
```
