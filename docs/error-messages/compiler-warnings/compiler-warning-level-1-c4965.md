---
title: Derleyici Uyarısı (düzey 1) C4965 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4965
dev_langs:
- C++
helpviewer_keywords:
- C4965
ms.assetid: 47f3f6dc-459b-4a25-9947-f394c8966cb5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d8613585d1f34060fb2e60f976f76c6801005aca
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46036650"
---
# <a name="compiler-warning-level-1-c4965"></a>Derleyici Uyarısı (düzey 1) C4965

örtük 0 tamsayı kutusunu; nullptr veya açık tür dönüştürme kullanın

Visual C++ değer türlerini örtük kutulama sunar. C++ için Yönetilen Uzantılar kullanarak, artık bir null ataması sonuçlanan bir yönerge kutulanmış int atama haline gelir.

Daha fazla bilgi için [kutulama](../../windows/boxing-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4965 oluşturur.

```
// C4965.cpp
// compile with: /clr /W1
int main() {
   System::Object ^o = 0;   // C4965

   // the previous line is the same as the following line
   // using Managed Extensions for C++
   // System::Object *o = __box(0);

   // OK
   System::Object ^o2 = nullptr;
   System::Object ^o3 = safe_cast<System::Object^>(0);
}
```