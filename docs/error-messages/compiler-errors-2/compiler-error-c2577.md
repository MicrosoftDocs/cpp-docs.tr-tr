---
title: Derleyici Hatası C2577 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2577
dev_langs:
- C++
helpviewer_keywords:
- C2577
ms.assetid: fc79ef83-8362-40a2-9257-8037c3195ce4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5d9a2b09fc9b8b15c4fc21f5eb537f18f5d3b03e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46065822"
---
# <a name="compiler-error-c2577"></a>Derleyici Hatası C2577

'member': yıkıcı/Sonlandırıcı dönüş türüne sahip olamaz

Yıkıcı veya Sonlandırıcı değerini döndüremez `void` veya diğer herhangi bir türü. Kaldırma `return` yok Edicisi tanımından deyimi.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2577 oluşturur.

```
// C2577.cpp
// compile with: /c
class A {
public:
   A() {}
   ~A(){
      return 0;   // C2577
   }
};
```