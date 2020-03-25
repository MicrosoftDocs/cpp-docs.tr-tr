---
title: Derleyici Uyarısı (düzey 1) C4739
ms.date: 11/04/2016
f1_keywords:
- C4739
helpviewer_keywords:
- C4739
ms.assetid: 600873b3-7c85-4cd4-944e-cd8e01bfcbb0
ms.openlocfilehash: 9c68a9e0a2873de7e919fafbef68835f0970c03b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185704"
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
