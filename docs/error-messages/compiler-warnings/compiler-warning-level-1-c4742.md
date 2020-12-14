---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4742'
title: Derleyici Uyarısı (düzey 1) C4742
ms.date: 07/22/2020
f1_keywords:
- C4742
helpviewer_keywords:
- C4742
ms.assetid: e520881d-1eeb-48b1-9df0-8017ee8ba076
ms.openlocfilehash: 009c8b894b9c53d3a0c802dbb0f5786fc9934b57
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228527"
---
# <a name="compiler-warning-level-1-c4742"></a>Derleyici Uyarısı (düzey 1) C4742

> '*Variable*', '*FILE1*' ve '*dosya2*' içinde farklı hizalamaya sahip: *Sayı1* ve *sayı2*

İki dosyada başvurulan veya tanımlanan bir dış değişkenin bu dosyalarda farklı hizalaması vardır.

## <a name="remarks"></a>Açıklamalar

Bu uyarı, derleyici **`alignof`** *FILE1* içindeki değişken için **`alignof`** *dosya2*' deki değişken için farklılık gösterir. Bunun nedeni, farklı dosyalardaki değişkeni bildirirken uyumsuz türler kullanılması veya farklı dosyalardaki eşleştirmesiz olarak kullanılması olabilir `#pragma pack` .

Bu uyarıyı çözümlemek için aynı tür tanımını kullanın ya da değişkenler için farklı adlar kullanın.

Daha fazla bilgi için bkz [`pack`](../../preprocessor/pack.md) . ve [ `alignof` işleci](../../cpp/alignof-operator.md).

## <a name="example"></a>Örnek

Bu, türü tanımlayan ilk dosyadır.

```c
// C4742a.c
// compile with: /c
struct X {
   char x, y, z, w;
} global;
```

Aşağıdaki örnek C4742 oluşturur.

```c
// C4742b.c
// compile with: C4742a.c /W1 /GL
// C4742 expected
extern struct X {
   int a;
} global;

int main() {
   global.a = 0;
}
```
