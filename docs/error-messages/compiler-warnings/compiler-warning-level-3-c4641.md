---
title: Derleyici Uyarısı (Düzey 3) C4641
ms.date: 11/04/2016
f1_keywords:
- C4641
helpviewer_keywords:
- C4641
ms.assetid: 28fe5c3e-6039-42da-9100-1312b5b15aea
ms.openlocfilehash: 9357088106a45026eae543f8627ea59988e73995
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57818511"
---
# <a name="compiler-warning-level-3-c4641"></a>Derleyici Uyarısı (Düzey 3) C4641

XML belgesi açıklamasında belirsiz bir çapraz başvuru var

Derleyici, bir başvuru dönüştürmelerle çözemedi. Bu uyarıyı çözmek için başvuru anlaşılır hale getirmek için gerekli parametre bilgilerini belirtin.

Daha fazla bilgi için [XML belgeleri](../../build/reference/xml-documentation-visual-cpp.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4641 oluşturur.

```
// C4641.cpp
// compile with: /W3 /doc /clr /c

/// <see cref="f" />   // C4641
// try the following line instead
// /// <see cref="f(int)" />
public ref class GR {
public:
   void f( int ) {}
   void f( char ) {}
};
```