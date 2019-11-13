---
title: Derleyici Uyarısı (düzey 1) C4829
ms.date: 11/04/2016
f1_keywords:
- C4829
helpviewer_keywords:
- C4829
ms.assetid: 4ffabe2b-2ddc-4c52-8564-d1355c93cfa6
ms.openlocfilehash: e8765f206d099f808ab261fbbde19273e46b5c90
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051240"
---
# <a name="compiler-warning-level-1-c4829"></a>Derleyici Uyarısı (düzey 1) C4829

Ana işlev için yanlış parametreler. ' İntmain (Platform:: Array\<Platform:: String ^ > ^ argv) ' düşünün

Ana gibi bazı işlevler başvuru türü parametreleri alamaz. Derleme başarılı olur, sonuçta elde edilen görüntü muhtemelen çalıştırılmaz.

Aşağıdaki örnek C4829 oluşturur:

```cpp
// C4829.cpp
// compile by using: cl /EHsc /ZW /W4 /c C4829.cpp
int main(Platform::String ^ s) {}   // C4829
```