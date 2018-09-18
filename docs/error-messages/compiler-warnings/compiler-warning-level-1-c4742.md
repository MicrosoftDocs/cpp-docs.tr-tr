---
title: Derleyici Uyarısı (düzey 1) C4742 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4742
dev_langs:
- C++
helpviewer_keywords:
- C4742
ms.assetid: e520881d-1eeb-48b1-9df0-8017ee8ba076
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 622a1b1cd62024da58191ce1312c391dd39e0d28
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088598"
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