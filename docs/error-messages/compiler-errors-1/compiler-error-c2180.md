---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2180'
title: Derleyici hatası C2180
ms.date: 11/04/2016
f1_keywords:
- C2180
helpviewer_keywords:
- C2180
ms.assetid: ea71b39e-b977-48a7-b7bd-af68ef5e263b
ms.openlocfilehash: 46ab20e3abfc35355543f90389677737e231257f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335190"
---
# <a name="compiler-error-c2180"></a>Derleyici hatası C2180

Denetim ifadesi ' Type ' türüne sahip

,,, Veya deyimindeki denetim ifadesi, ' a **`if`** **`while`** **`for`** **`do`** bir ifade tür **`void`** . Bu sorunu giderecek şekilde denetlemek için, denetim ifadesini bir **`bool`** veya olarak dönüştürülebileceği bir tür üreten bir tür ile değiştirin **`bool`** .

Aşağıdaki örnek C2180 oluşturur:

```c
// C2180.c

int main() {
   while ((void)1)   // C2180
      return 1;
   while (1)         // OK
      return 0;
}
```
