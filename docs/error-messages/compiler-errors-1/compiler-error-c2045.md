---
title: Derleyici Hatası C2045
ms.date: 11/04/2016
f1_keywords:
- C2045
helpviewer_keywords:
- C2045
ms.assetid: 2fca668e-9b20-4933-987a-18c0fd0187df
ms.openlocfilehash: 55eccbae84fb7f700c3ac9fdf6721d3f25582862
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408894"
---
# <a name="compiler-error-c2045"></a>Derleyici Hatası C2045

'identifier': Etiket yeniden tanımlandı

Aynı işlevde birden çok deyime önce etiket görünür.

Aşağıdaki örnek, C2045 oluşturur:

```
// C2045.cpp
int main() {
   label: {
   }
   goto label;
   label: {}   // C2045
}
```