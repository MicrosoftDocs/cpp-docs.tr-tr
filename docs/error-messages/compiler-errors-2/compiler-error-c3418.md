---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3418'
title: Derleyici hatası C3418
ms.date: 11/04/2016
f1_keywords:
- C3418
helpviewer_keywords:
- C3418
ms.assetid: 54042c04-3c45-41c1-bad7-90f9ee05a21b
ms.openlocfilehash: 38082b7fe9ffa0ebcc7b4857e77395664a9f0c42
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316238"
---
# <a name="compiler-error-c3418"></a>Derleyici hatası C3418

' tanımlayıcı ' erişim belirticisi desteklenmiyor

CLR erişim belirticisi yanlış belirtildi.  Daha fazla bilgi için bkz. [nasıl yapılır: sınıfları ve yapıları tanımlama ve kullanma (C++/CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md)içindeki tür görünürlüğü ve üye görünürlüğü.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3418 oluşturur.

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
