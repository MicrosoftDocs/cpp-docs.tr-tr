---
description: 'Daha fazla bilgi edinin: Derleyici Uyarısı (düzey 3) C4641'
title: Derleyici Uyarısı (düzey 3) C4641
ms.date: 11/04/2016
f1_keywords:
- C4641
helpviewer_keywords:
- C4641
ms.assetid: 28fe5c3e-6039-42da-9100-1312b5b15aea
ms.openlocfilehash: 4b1111075b4cf375ef102899f0971773080f33ba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332167"
---
# <a name="compiler-warning-level-3-c4641"></a>Derleyici Uyarısı (düzey 3) C4641

XML belgesi açıklamasında belirsiz bir çapraz başvuru vardır

Derleyici bir başvuruyu kesin olarak çözümleyemedi. Bu uyarıyı çözmek için, başvuruyu belirsiz hale getirmek için gereken parametre bilgilerini belirtin.

Daha fazla bilgi için bkz. [XML belgeleri](../../build/reference/xml-documentation-visual-cpp.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C4641 oluşturur.

```cpp
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
