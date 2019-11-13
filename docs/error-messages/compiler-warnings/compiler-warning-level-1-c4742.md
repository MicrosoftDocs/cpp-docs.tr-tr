---
title: Derleyici Uyarısı (düzey 1) C4742
ms.date: 11/04/2016
f1_keywords:
- C4742
helpviewer_keywords:
- C4742
ms.assetid: e520881d-1eeb-48b1-9df0-8017ee8ba076
ms.openlocfilehash: 11663a9b8672e2f91feb59e275181dbe645484e9
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051305"
---
# <a name="compiler-warning-level-1-c4742"></a>Derleyici Uyarısı (düzey 1) C4742

' var ', ' FILE1 ' ve ' dosya2 ': Number ve Number değerlerinde farklı hizalamaya sahip

İki dosyada başvurulan veya tanımlanan bir dış değişkenin bu dosyalarda farklı hizalaması vardır. Derleyici, *FILE1* içindeki değişken için `__alignof`, *dosya2*içindeki değişken için `__alignof` farklılık gösterdiğinde bu uyarı yayınlanır. Bunun nedeni, farklı dosyalardaki değişkeni bildirirken uyumsuz türler kullanılması veya farklı dosyalarda eşleşmeyen `#pragma pack` kullanılması olabilir.

Bu uyarıyı çözümlemek için aynı tür tanımını kullanın ya da değişkenler için farklı adlar kullanın.

Daha fazla bilgi için bkz. [Pack](../../preprocessor/pack.md) ve [__alignof işleci](../../cpp/alignof-operator.md).

## <a name="example"></a>Örnek

Bu, türü tanımlayan ilk dosyadır.

```c
// C4742a.c
// compile with: /c
struct X {
   char x, y, z, w;
} global;
```

## <a name="example"></a>Örnek

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