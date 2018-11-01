---
title: Derleyici Uyarısı (düzey 1) C4829
ms.date: 11/04/2016
f1_keywords:
- C4829
helpviewer_keywords:
- C4829
ms.assetid: 4ffabe2b-2ddc-4c52-8564-d1355c93cfa6
ms.openlocfilehash: ace409cee05650e0dbfbcdd32cd15e85f8dbf006
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50594174"
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