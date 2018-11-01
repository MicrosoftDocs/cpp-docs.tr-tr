---
title: Derleyici Hatası C3234
ms.date: 11/04/2016
f1_keywords:
- C3234
helpviewer_keywords:
- C3234
ms.assetid: ebefc15a-e40d-424b-a3dd-d7e185d0ed7b
ms.openlocfilehash: fd6e918c115ed121dda5d589a62b1a94d14184a8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50477603"
---
# <a name="compiler-error-c3234"></a>Derleyici Hatası C3234

Genel sınıf bir genel tür parametresinden türetilemez

Genel sınıf bir genel tür parametresinden devralamaz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3234 oluşturur.

```
// C3234.cpp
// compile with: /clr /c
generic <class T>
public ref class C : T {};   // C3234
// try the following line instead
// public ref class C {};
```