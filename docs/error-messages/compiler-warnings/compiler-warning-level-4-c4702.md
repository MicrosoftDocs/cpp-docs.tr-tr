---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4702'
title: Derleyici Uyarısı (düzey 4) C4702
ms.date: 11/04/2016
f1_keywords:
- C4702
helpviewer_keywords:
- C4702
ms.assetid: d8198c1e-8762-42a6-9e6b-cb568b7a1686
ms.openlocfilehash: 9a171641a2c923083471d510e27fbdb3ebd08832
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97133802"
---
# <a name="compiler-warning-level-4-c4702"></a>Derleyici Uyarısı (düzey 4) C4702

erişilemeyen kod

Bu uyarı, Visual Studio .NET 2003: ulaşılamaz kod için yapılan derleyici uygunluk işinin sonucudur. Derleyici (arka uç) erişilemeyen kodu algıladığında, 4. düzey bir uyarı C4702 oluşturur.

Hem Visual Studio .NET 2003 hem de Visual C++ Visual Studio .NET sürümlerinde geçerli olan kod için, erişilemeyen kodu kaldırın veya tüm kaynak koduna bazı yürütme akışı tarafından erişilebildiğinden emin olur.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek C4702 oluşturur.

```cpp
// C4702.cpp
// compile with: /W4
#include <stdio.h>

int main() {
   return 1;
   printf_s("I won't print.\n");   // C4702 unreachable
}
```

**/GX**, **/EHC**, **/EHsc** veya **/EHac** ile derlerken ve extern c işlevlerini kullanırken, extern c işlevlerinin oluşturmadığı kabul edildiği için kod ulaşılamaz hale gelebilir, bu nedenle catch bloğunun ulaşılamaz olması gerekir.  Bu uyarının geçerli olmadığını düşünüyorsanız, bir işlev oluşturabileceğinden, oluşturulan özel duruma bağlı olarak **/EHa** veya **/EHS** ile derleyin.

Daha fazla bilgi için bkz. [/Eh (özel durum Işleme modeli)](../../build/reference/eh-exception-handling-model.md) .

Aşağıdaki örnek C4702 oluşturur.

```cpp
// C4702b.cpp
// compile with: /W4 /EHsc
#include <iostream>

using namespace std;
extern "C" __declspec(dllexport) void Function2(){}

int main() {
   try {
      Function2();
   }
   catch (...) {
      cout << "Exp: Function2!" << endl;   // C4702
   }
}
```
