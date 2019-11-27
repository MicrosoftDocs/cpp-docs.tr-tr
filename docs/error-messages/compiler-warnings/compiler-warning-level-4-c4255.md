---
title: Derleyici Uyarısı (düzey 4) C4255
ms.date: 11/04/2016
f1_keywords:
- C4255
helpviewer_keywords:
- C4255
ms.assetid: 2087b635-4b4c-4182-8a01-c26770d2bb88
ms.openlocfilehash: 7b64da554d6afbac4422c79ff593429ba90a4378
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541708"
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