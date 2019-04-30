---
title: Derleyici Uyarısı (düzey 1) C4829
ms.date: 11/04/2016
f1_keywords:
- C4829
helpviewer_keywords:
- C4829
ms.assetid: 4ffabe2b-2ddc-4c52-8564-d1355c93cfa6
ms.openlocfilehash: 1afb29b10352150cac2969849979fb5b5e2b8719
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62378485"
---
# <a name="compiler-warning-level-1-c4829"></a>Derleyici Uyarısı (düzey 1) C4829

Büyük olasılıkla yanlış parametreler ana işlev. Göz önünde bulundurun ' intmain (Platform::Array\<Platform::String ^ > ^ argv)'

Bazı işlevler, ana gibi tür parametreleri başvuru alamıyor. Derleme başarılı olur, ancak elde edilen görüntü çalıştırma olmayabilir.

Aşağıdaki örnek, C4829 oluşturur:

```
// C4829.cpp
// compile by using: cl /EHsc /ZW /W4 /c C4829.cpp
int main(Platform::String ^ s) {}   // C4829
```