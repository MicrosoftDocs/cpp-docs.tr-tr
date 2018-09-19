---
title: Derleyici Hatası C3418 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3418
dev_langs:
- C++
helpviewer_keywords:
- C3418
ms.assetid: 54042c04-3c45-41c1-bad7-90f9ee05a21b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 26fa67da6f24e578319660c17cb48d7d715be408
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46033283"
---
# <a name="compiler-error-c3418"></a>Derleyici Hatası C3418

erişim belirticisi 'belirticisi' desteklenmiyor

CLR bir erişim belirticisi yanlış olarak belirtildi.  Daha fazla bilgi için bkz: tür görünürlüğü ve üye görünürlüğü [nasıl yapılır: tanımlayın ve Consume Classes and Structs (C + +/ CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md).

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