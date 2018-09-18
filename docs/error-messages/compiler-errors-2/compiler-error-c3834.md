---
title: Derleyici Hatası C3834 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3834
dev_langs:
- C++
helpviewer_keywords:
- C3834
ms.assetid: 059e0dc4-300b-4e74-b6c2-41a57831fe2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1032c8210cc3df8f9000452ebe18576a10cf5437
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072764"
---
# <a name="compiler-error-c3834"></a>Derleyici Hatası C3834

Geçersiz açık bir sabitleme işaretçisine dönüştürme; Bunun yerine sabitlenmiş bir yerel değişken kullanın

Açık yayınları sabitlenmiş bir işaretçiye izin verilmez.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3834 oluşturur.

```
// C3834.cpp
// compile with: /clr
int main() {
   int x = 33;

   pin_ptr<int> p = safe_cast<pin_ptr<int> >(&x);   // C3834
   pin_ptr<int> p2 = &x;   // OK
}
```
