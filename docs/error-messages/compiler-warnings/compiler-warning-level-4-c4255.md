---
title: Derleyici Uyarısı (düzey 4) C4255
ms.date: 11/04/2016
f1_keywords:
- C4255
helpviewer_keywords:
- C4255
ms.assetid: 2087b635-4b4c-4182-8a01-c26770d2bb88
ms.openlocfilehash: 49d3965ed7190e6a763e135bb1307a0b847697d7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161119"
---
# <a name="compiler-warning-level-4-c4255"></a>Derleyici Uyarısı (düzey 4) C4255

' function ': hiçbir işlev prototipi verilmedi: ' () ', ' (void) ' olarak dönüştürülüyor

Derleyici, bir işleve bağımsız değişkenlerin açık bir listesini bulamadı. Bu uyarı yalnızca C derleyicisi içindir.

Bu uyarı varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Aşağıdaki örnek C4255 oluşturur:

```c
// C4255.c
// compile with: /W4 /WX
#pragma warning (default : 4255)

void f()  { // C4255
// try the following line instead
//void f(void) {
}

int main(int argc, char *argv[]) {
   f();
}
```
