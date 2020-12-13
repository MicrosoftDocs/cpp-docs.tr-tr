---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3917'
title: Derleyici hatası C3917
ms.date: 11/04/2016
f1_keywords:
- C3917
helpviewer_keywords:
- C3917
ms.assetid: a24cd0c9-262f-46e5-9488-1c01f945933d
ms.openlocfilehash: 3e30e93f650e1b835aafd6639687560aa7349c1f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143942"
---
# <a name="compiler-error-c3917"></a>Derleyici hatası C3917

'*Property*': Kullanımdan kaldırılmış yapı bildirimi stili

Bir özellik veya olay tanımı, Visual Studio 2005 öncesindeki bir sürümden sözdizimi kullandı.

Daha fazla bilgi için bkz. [özellik](../../extensions/property-cpp-component-extensions.md).

## <a name="example"></a>Örnek

```cpp
// C3917.cpp
// compile with: /clr /c
public ref class  C {
private:
   int m_length;
public:
   C() {
      m_length = 0;
   }

   property int get_Length();   // C3917

   // The correct property definition:
   property int Length {
      int get() {
         return m_length;
      }

      void set( int i ) {
         m_length = i;
      }
   }
};
```
