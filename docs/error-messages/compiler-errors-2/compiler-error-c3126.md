---
title: Derleyici hatası C3126
ms.date: 11/04/2016
f1_keywords:
- C3126
helpviewer_keywords:
- C3126
ms.assetid: e72658a3-5d85-4a31-89a4-dbc3d475973d
ms.openlocfilehash: 2b8901ce9914f35d4cd219f4d51477582fa676a8
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760731"
---
# <a name="compiler-error-c3126"></a>Derleyici hatası C3126

' Type ' yönetilen türünün içinde ' Union ' birleşimi tanımlanamaz

Bir birleşim yönetilen bir tür içinde tanımlanamaz.

Aşağıdaki örnek C3126 oluşturur:

```cpp
// C3126_2.cpp
// compile with: /clr /c
ref class Test
{
   union x
   {   // C3126
      int a;
      int b;
   };
};
```
