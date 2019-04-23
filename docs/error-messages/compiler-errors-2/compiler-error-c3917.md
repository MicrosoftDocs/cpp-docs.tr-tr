---
title: Derleyici Hatası C3917
ms.date: 11/04/2016
f1_keywords:
- C3917
helpviewer_keywords:
- C3917
ms.assetid: a24cd0c9-262f-46e5-9488-1c01f945933d
ms.openlocfilehash: 9cb6d594124d995d766df280da2584665ab6d7a2
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59776372"
---
# <a name="compiler-error-c3917"></a>Derleyici Hatası C3917

'*özelliği*': eski bildirim stili yapısı

Bir özellik veya olay tanımı bir sürümünden önce Visual Studio 2005 söz dizimi kullanılır.

Daha fazla bilgi için [özelliği](../../extensions/property-cpp-component-extensions.md).

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