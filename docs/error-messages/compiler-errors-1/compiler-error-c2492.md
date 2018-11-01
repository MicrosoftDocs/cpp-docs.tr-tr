---
title: Derleyici Hatası C2492
ms.date: 11/04/2016
f1_keywords:
- C2492
helpviewer_keywords:
- C2492
ms.assetid: 8c44c9bb-c366-4fe5-a0ab-882e38608aaa
ms.openlocfilehash: e2b08ef3e46681147c4efd77cbffadb096bbfc16
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50590469"
---
# <a name="compiler-error-c2492"></a>Derleyici Hatası C2492

'*değişkeni*': iş parçacığı depolama süresine sahip verilerin dll arabirimi olmayabilir

Değişkeni ile bildirilen [iş parçacığı](../../cpp/thread.md) özniteliği ve DLL ile arabirim. Adresini `thread` değişkeni için bir DLL içeri veya dışarı aktarma bağlanamaz için çalışma zamanına kadar tanınmıyor.

Aşağıdaki örnek, C2492 oluşturur:

```
// C2492.cpp
// compile with: /c
class C {
public:
   char   ch;
};

__declspec(dllexport) __declspec(thread) C c_1;   // C2492
__declspec(thread) C c_1;   // OK
```