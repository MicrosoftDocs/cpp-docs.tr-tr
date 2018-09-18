---
title: Derleyici Hatası C2533 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2533
dev_langs:
- C++
helpviewer_keywords:
- C2533
ms.assetid: 5b335652-076c-4824-87c8-a741f64a3ce0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 528b78e71713725907a9f0e2bd06cec1a8c62e67
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045412"
---
# <a name="compiler-error-c2533"></a>Derleyici Hatası C2533

'identifier': oluşturucuların bir dönüş türüne izin verilmiyor

Oluşturucusu bir dönüş türü olamaz (değil bile bir `void` dönüş türü).

Bu hatanın yaygın bir kaynağı bir sınıf tanımının son ve ilk Oluşturucu uygulaması arasında eksik noktalı virgüldür. Derleyici, sınıf oluşturucu işlevi için dönüş türü tanımı olarak görür ve C2533 oluşturur.

Aşağıdaki örnek, C2533 oluşturur ve bu sorunun nasıl gösterir:

```
// C2533.cpp
// compile with: /c
class X {
public:
   X();
};

int X::X() {}   // C2533 - constructor return type not allowed
X::X() {}   // OK - fix by using no return type
```