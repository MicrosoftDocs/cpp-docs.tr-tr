---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2492'
title: Derleyici hatası C2492
ms.date: 11/04/2016
f1_keywords:
- C2492
helpviewer_keywords:
- C2492
ms.assetid: 8c44c9bb-c366-4fe5-a0ab-882e38608aaa
ms.openlocfilehash: ef31b2136a2cfc0422832899dba14ffb3108d965
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283685"
---
# <a name="compiler-error-c2492"></a>Derleyici hatası C2492

'*değişken*': iş parçacığı depolama süresine sahip verilerin dll arabirimi olmayabilir

Değişkeni, [iş parçacığı](../../cpp/thread.md) ÖZNITELIĞIYLE ve DLL arabirimiyle birlikte bildirilmiştir. `thread`Değişkenin adresi çalışma zamanına kadar bilinmiyor, bu nedenle BIR DLL içeri veya dışarı aktarmaya bağlanamaz.

Aşağıdaki örnek C2492 oluşturur:

```cpp
// C2492.cpp
// compile with: /c
class C {
public:
   char   ch;
};

__declspec(dllexport) __declspec(thread) C c_1;   // C2492
__declspec(thread) C c_1;   // OK
```
