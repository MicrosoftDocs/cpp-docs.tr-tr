---
title: Derleyici Uyarısı (düzey 4) C4702 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4702
dev_langs:
- C++
helpviewer_keywords:
- C4702
ms.assetid: d8198c1e-8762-42a6-9e6b-cb568b7a1686
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1d15072099c6329eced8ab9dd9c78f8f48c31fe7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057146"
---
# <a name="compiler-warning-level-4-c4702"></a>Derleyici Uyarısı (düzey 4) C4702

erişilemeyen kodları

Bu bir uyarıdır için Visual Studio .NET 2003 yapıldığı derleyici uyumluluğu iş sonucu: erişilemeyen kod. Erişilemeyen kod derleyici (arka uç) algıladığında, C4702, oluşturur bir düzey 4 uyarısı.

Visual Studio .NET 2003 ve Visual Studio .NET Visual C++ sürümlerinde geçerli olan kod, erişilemeyen kodları kaldırma veya tüm kaynak kodu yürütme bazı flow tarafından erişilebilir olduğunu güvence altına alır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4702 oluşturur.

```
// C4702.cpp
// compile with: /W4
#include <stdio.h>

int main() {
   return 1;
   printf_s("I won't print.\n");   // C4702 unreachable
}
```

## <a name="example"></a>Örnek

İle derlerken **/GX**, **/ehc**, **/ehsc**, veya **/EHac** ve extern C işlevleri'ni kullanarak kod ulaşılamaz hale gelebilir çünkü extern C İşlevler oluşturma için kabul edilir, böylece catch bloğu erişilebilir değil.  Bir işlev oluşturabilecek çünkü bu uyarının geçerli olmadığını düşünüyorsanız, derleme **/eha** veya **EHS**bağlı olarak özel durum oluştu.

Daha fazla bilgi için [/EH (özel durum işleme modeli)](../../build/reference/eh-exception-handling-model.md) daha fazla bilgi için.

Aşağıdaki örnek, C4702 oluşturur.

```
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