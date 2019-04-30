---
title: Derleyici Hatası C3498
ms.date: 11/04/2016
f1_keywords:
- C3498
helpviewer_keywords:
- C3498
ms.assetid: 0a5a7817-0872-4119-83bf-980a19113374
ms.openlocfilehash: 463e210e5a1ac5eb6d197062ed8921f9bbae4ad2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62381013"
---
# <a name="compiler-error-c3498"></a>Derleyici Hatası C3498

'var': bir yönetilen sahip bir değişken veya WinRTtype yakalayamazsınız

Bir lambda içinde yönetilen bir türe veya bir Windows çalışma zamanı türü içeren bir değişkeni yakalayamazsınız.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Yönetilen geçirin veya lambda ifadesi parametre listesine Windows çalışma zamanı değişken.

## <a name="example"></a>Örnek

Aşağıdaki örnek, yönetilen bir türe sahip bir değişken bir lambda ifadesinin yakalama listede göründüğünden C3498 oluşturur:

```
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

Aşağıdaki örnek, yönetilen değişkeni geçirerek C3498 çözümler `s` lambda ifadesi parametre listesine:

```
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