---
title: Derleyici Uyarısı (düzey 4) C4289
ms.date: 11/04/2016
f1_keywords:
- C4289
helpviewer_keywords:
- C4289
ms.assetid: 0dbd2863-4cde-4e16-894b-104a2d5fa724
ms.openlocfilehash: cc1a22065be6d5f7f49d6c32f6bc9b6479399e29
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541968"
---
# <a name="compiler-warning-level-4-c4289"></a>Derleyici Uyarısı (düzey 4) C4289

standart olmayan uzantı kullanıldı : 'var': for döngüsünde bildirimi yapılan döngü denetim değişkeni for döngüsü kapsamının dışında kullanılıyor

[/Ze](../../build/reference/za-ze-disable-language-extensions.md) ve **/Zc: forScope**ile derlerken, [for döngüsünde belirtilen bir değişken](../../cpp/for-statement-cpp.md) **for**döngüsü kapsamından sonra kullanılır.

**/Ze**ile döngüler **için** standart davranışın nasıl belirtilme hakkında bilgi için bkz. [/Zc: forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) .

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