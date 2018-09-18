---
title: Derleyici Hatası C2271 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2271
dev_langs:
- C++
helpviewer_keywords:
- C2271
ms.assetid: ea47bf57-f55d-4171-8e98-95a71d62820e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b47619bfc42037703b908ff9cb551307063f2bfa
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46065471"
---
# <a name="compiler-error-c2271"></a>Derleyici Hatası C2271

'operator': yeni/delete biçimsel liste değiştiricilerine sahip olamaz

İşleç (`new` veya `delete`) bellek-model tanımlayıcısı ile bildirilir.

Aşağıdaki örnek, C2271 oluşturur:

```
// C2271.cpp
// compile with: /c
void* operator new(size_t) const {   // C2271
// try the following line instead
// void* operator new(size_t) {
   return 0;
}

struct X {
   static void* operator new(size_t) const;   // C2271
   // try the following line instead
   // void * X::operator new(size_t) const;   // static member operator new
};
```