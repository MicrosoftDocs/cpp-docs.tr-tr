---
title: Derleyici Uyarısı (düzey 4) C4289
ms.date: 11/04/2016
f1_keywords:
- C4289
helpviewer_keywords:
- C4289
ms.assetid: 0dbd2863-4cde-4e16-894b-104a2d5fa724
ms.openlocfilehash: 8742fd5e64f2ba1877fa3fbecfb221ef295d463e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219904"
---
# <a name="compiler-warning-level-4-c4289"></a>Derleyici Uyarısı (düzey 4) C4289

standart olmayan uzantı kullanıldı : 'var': for döngüsünde bildirimi yapılan döngü denetim değişkeni for döngüsü kapsamının dışında kullanılıyor

[/Ze](../../build/reference/za-ze-disable-language-extensions.md) ve **/Zc: forScope**ile derlerken, [for](../../cpp/for-statement-cpp.md) döngüsünde belirtilen bir değişken **`for`** -Loop kapsamından sonra kullanıldı.

/Ze ile Döngülerde standart davranış belirtme hakkında bilgi için bkz. [/Zc: forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) **`for`** . **/Ze**

Bu uyarı varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Aşağıdaki örnek C4289 oluşturur:

```cpp
// C4289.cpp
// compile with: /W4 /Zc:forScope-
#pragma warning(default:4289)
int main() {
   for (int i = 0 ; ; )   // C4289
      break;
   i++;
}
```
