---
title: Derleyici Hatası C3866 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3866
dev_langs:
- C++
helpviewer_keywords:
- C3866
ms.assetid: 685870af-2440-4cdf-a6cb-284a5b96ef9d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eb56440dd67bc59e7719acdf70cee2784c889db2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46048909"
---
# <a name="compiler-error-c3866"></a>Derleyici Hatası C3866

bağımsız değişken listesi eksik işlev çağrısı

Bir statik olmayan üye işlev içinde bir yıkıcı veya Sonlandırıcı çağrısı bir bağımsız değişken listesi yok.

Aşağıdaki örnek, C3866 oluşturur:

```
// C3866.cpp
// compile with: /c
class C {
   ~C();
   void f() {
      this->~C;   // C3866
      this->~C();   // OK
   }
};
```