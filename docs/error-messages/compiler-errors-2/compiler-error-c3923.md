---
title: Derleyici Hatası C3923 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3923
dev_langs:
- C++
helpviewer_keywords:
- C3923
ms.assetid: db8838e9-6344-4cd6-83e0-a8abeb12c4c0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b00edbb824e7815e93b961b792513a88cf96f4be
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031346"
---
# <a name="compiler-error-c3923"></a>Derleyici Hatası C3923

'member': yerel sınıf, yapı veya birleşim tanımlarına bir WinRT veya yönetilen sınıfının üye işlevinde izin verilmez

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3923 oluşturur.

```
// C3923.cpp
// compile with: /clr /c
ref struct x {
   void Test() {
      struct a {};   // C3923
      class b {};   // C3923
      union c {};   // C3923
   }
};
```