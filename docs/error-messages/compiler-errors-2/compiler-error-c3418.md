---
title: Derleyici Hatası C3418
ms.date: 11/04/2016
f1_keywords:
- C3418
helpviewer_keywords:
- C3418
ms.assetid: 54042c04-3c45-41c1-bad7-90f9ee05a21b
ms.openlocfilehash: 8456e9b17b72cd4ac98349d2f2871a1c59f56911
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62311505"
---
# <a name="compiler-error-c3418"></a>Derleyici Hatası C3418

erişim belirticisi 'belirticisi' desteklenmiyor

CLR bir erişim belirticisi yanlış olarak belirtildi.  Daha fazla bilgi için bkz: tür görünürlüğü ve üye görünürlüğü [nasıl yapılır: Sınıfları ve yapıları tanımlama ve kullanma (C++/CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3418 oluşturur.

```cpp
// C3418.cpp
// compile with: /clr /c
ref struct m {
internal public:   // C3418
   void test(){}
};

ref struct n {
internal:   // OK
   void test(){}
};
```