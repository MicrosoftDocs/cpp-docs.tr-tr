---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3152'
title: Derleyici hatası C3152
ms.date: 11/04/2016
f1_keywords:
- C3152
helpviewer_keywords:
- C3152
ms.assetid: 4ee6e2cd-5d19-4b73-833d-765c35797e4b
ms.openlocfilehash: b7e98535003a03ec5ac8b06d23b105d3727ff605
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322068"
---
# <a name="compiler-error-c3152"></a>Derleyici hatası C3152

' yapı ': ' anahtar sözcüğü ' yalnızca bir sınıfa, yapıya veya sanal üye işleve uygulanabilir

Bazı anahtar sözcükler yalnızca bir C++ sınıfına uygulanabilir.

Aşağıdaki örnek C3152 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C3152.cpp
// compile with: /clr /c
ref class C {
   int (*pfn)() sealed;   // C3152
   virtual int g() sealed;   // OK
};
```
