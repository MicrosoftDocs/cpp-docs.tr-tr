---
title: Derleyici Hatası C2094 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2094
dev_langs:
- C++
helpviewer_keywords:
- C2094
ms.assetid: 9e4f8f88-f189-46e7-91c9-481bacc7af87
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6e3591fef423bc24562a2f2edf18f7f2774cfcc4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46073531"
---
# <a name="compiler-error-c2094"></a>Derleyici Hatası C2094

'identifier' etiketi tanımlanmadı

Tarafından kullanılan etiketi bir [goto](../../cpp/goto-statement-cpp.md) deyimi işlev yok.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2094 oluşturur:

```cpp
// C2094.c
int main() {
   goto test;
}   // C2094
```

Olası çözüm:

```cpp
// C2094b.c
int main() {
   goto test;
   test:
   {
   }
}
```