---
title: Derleyici Uyarısı (düzey 1) C4742
ms.date: 11/04/2016
f1_keywords:
- C4742
helpviewer_keywords:
- C4742
ms.assetid: e520881d-1eeb-48b1-9df0-8017ee8ba076
ms.openlocfilehash: 00ac67fec3aafa5a259b5222bd6bb8654210fa61
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50436368"
---
# <a name="compiler-warning-level-1-c4742"></a>Derleyici Uyarısı (düzey 1) C4742

'var', 'dosya1' ve 'dosya2' farklı hizalamaya sahip: ve numarası

Başvurulan veya iki dosyalarında tanımlanan bir dış değişkenine bu dosyaları farklı hizalamaya sahip. Bu uyarı, derleyici bulduğunda yayıldığını `__alignof` değişken için *dosya1* farklıdır `__alignof` değişken için *dosya2*. Bu farklı dosyalar değişken bildirirken uyumsuz türler kullanan veya eşleşmeyen kullanarak kaynaklanabilir `#pragma pack` içinde farklı dosyalar.

Bu uyarıyı çözmek için aynı tür tanımını kullanabilir veya değişkenleri için farklı adlar kullanın.

Daha fazla bilgi için [paketi](../../preprocessor/pack.md) ve [__alignof işleci](../../cpp/alignof-operator.md).

## <a name="example"></a>Örnek

Bu türü tanımlayan ilk dosyasıdır.

```
// C4742a.c
// compile with: /c
struct X {
   char x, y, z, w;
} global;
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4742 oluşturur.

```
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