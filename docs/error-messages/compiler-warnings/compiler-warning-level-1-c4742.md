---
title: Derleyici Uyarısı (düzey 1) C4742
ms.date: 11/04/2016
f1_keywords:
- C4742
helpviewer_keywords:
- C4742
ms.assetid: e520881d-1eeb-48b1-9df0-8017ee8ba076
ms.openlocfilehash: af97c72f496177d2e94cf18f9685ac33c5e62404
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185665"
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
