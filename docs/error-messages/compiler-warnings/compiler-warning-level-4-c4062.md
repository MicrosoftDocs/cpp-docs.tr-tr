---
title: Derleyici Uyarısı (düzey 4) C4062
ms.date: 04/05/2019
f1_keywords:
- C4062
helpviewer_keywords:
- C4062
ms.assetid: 36d1c6ae-c917-4b08-bf30-2eb49ee94169
ms.openlocfilehash: efe021c9994e20f2630e31537bcc6099783b4308
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220008"
---
# <a name="compiler-warning-level-4-c4062"></a>Derleyici Uyarısı (düzey 4) C4062

> '*Enumeration*' numaralandırmasının anahtarındaki Numaralandırıcı '*Identifier*' işlenmiyor

Numaralandırıcı *tanımlayıcısının* `case` bir ifadede ilişkili işleyicisi yok **`switch`** ve **`default`** bunu yakalayasağlayan bir etiket yok. Eksik durum, hatalı bir bakış olabilir ve kodunuzda olası bir hatadır. Büyük/küçük harfli olmayan ifadelerde kullanılmayan numaralandırıcılara ilişkin ilgili uyarı için **`switch`** **`default`** bkz. [C4061](compiler-warning-level-4-c4061.md).

Bu uyarı varsayılan olarak kapalıdır. Varsayılan olarak kapalı olan uyarıların nasıl etkinleştirileceği hakkında daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C4062 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C4062.cpp
// compile with: /EHsc /W4
#pragma warning(default : 4062)
enum E { a, b, c };
void func ( E e ) {
   switch(e) {
      case a:
      case b:
   // case c:  // to fix, uncomment this line
      break;   // no default label
   }   // C4062, enumerator 'c' not handled
}

int main() {
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Uyarısı (düzey 4) C4061](compiler-warning-level-4-c4061.md)
