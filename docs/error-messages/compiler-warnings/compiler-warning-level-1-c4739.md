---
title: Derleyici Uyarısı (düzey 1) C4739
ms.date: 11/04/2016
f1_keywords:
- C4739
helpviewer_keywords:
- C4739
ms.assetid: 600873b3-7c85-4cd4-944e-cd8e01bfcbb0
ms.openlocfilehash: df8f3bcf6cfcc9feb2a400526285ccd9cb0396e4
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052418"
---
# <a name="compiler-warning-level-1-c4739"></a>Derleyici Uyarısı (düzey 1) C4739

' var ' değişkenine yapılan başvuru depolama alanını aşıyor

Bir değişkene bir değer atandı, ancak değer değişkenin boyutundan büyük. Bellek, değişkenin bellek konumunun ötesinde yazılır ve veri kaybı mümkündür.

Bu uyarıyı çözmek için, yalnızca boyutu değeri barındırabilecek bir değişkene bir değer atayın.

Aşağıdaki örnek C4739 oluşturur:

```cpp
// C4739.cpp
// compile with: /RTCs /Zi /W1 /c
char *pc;
int main() {
   char c;
   *(int *)&c = 1;   // C4739

   // OK
   *(char *)&c = 1;
}
```