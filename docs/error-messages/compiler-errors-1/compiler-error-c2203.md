---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2203'
title: Derleyici hatası C2203
ms.date: 11/04/2016
f1_keywords:
- C2203
helpviewer_keywords:
- C2203
ms.assetid: 5497df43-86f6-43d5-b6cb-723c4c589b10
ms.openlocfilehash: 98da34221da5bc054de795579d33be00fb3657cd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245791"
---
# <a name="compiler-error-c2203"></a>Derleyici hatası C2203

delete işleci bir dizi için sınırları belirtemez

**/Za** (ANSI) seçeneğiyle, **`delete`** işleci bir dizinin tamamını veya dizi parçalarını veya belirli üyelerini silebilir.

Aşağıdaki örnek C2203 oluşturur:

```cpp
// C2203.cpp
// compile with: /Za
int main() {
   int *ar = new int[10];
   delete [4] ar;   // C2203
   // try the following line instead
   // delete [] ar;
}
```
