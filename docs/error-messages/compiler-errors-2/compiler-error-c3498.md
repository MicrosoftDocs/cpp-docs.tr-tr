---
title: Derleyici hatası C3498
ms.date: 11/04/2016
f1_keywords:
- C3498
helpviewer_keywords:
- C3498
ms.assetid: 0a5a7817-0872-4119-83bf-980a19113374
ms.openlocfilehash: 771e8c72ab4386bb45a11983318f412e784f5bc9
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738108"
---
# <a name="compiler-error-c3498"></a>Derleyici hatası C3498

' var ': yönetilen veya WinRTtype içeren bir değişken yakalayamazsınız

Lambda içinde yönetilen bir türe veya Windows Çalışma Zamanı türüne sahip bir değişken yakalayamazsınız.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Yönetilen veya Windows Çalışma Zamanı değişkenini lambda ifadesinin parametre listesine geçirin.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir lambda ifadesinin yakalama listesinde yönetilen bir türe sahip bir değişken göründüğünden, C3498 oluşturur:

```cpp
// C3498a.cpp
// compile with: /clr
using namespace System;

int main()
{
   String ^ s = "Hello";
   [&s](String ^ r)
      { return String::Concat(s, r); } (", World!"); // C3498
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, yönetilen değişkeni `s` lambda ifadesinin parametre listesine geçirerek C3498 'i çözer:

```cpp
// C3498b.cpp
// compile with: /clr
using namespace System;

int main()
{
   String ^ s = "Hello";
   [](String ^ s, String ^ r)
      { return String::Concat(s, r); } (s, ", World!");
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)
