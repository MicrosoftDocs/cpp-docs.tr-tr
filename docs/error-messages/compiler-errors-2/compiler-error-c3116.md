---
title: Derleyici hatası C3116
ms.date: 11/04/2016
f1_keywords:
- C3116
helpviewer_keywords:
- C3116
ms.assetid: 597463e1-a5cc-4ed3-a917-eae9a61d3312
ms.openlocfilehash: b336588d732fca2fd45b753429a563360f575912
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223453"
---
# <a name="compiler-error-c3116"></a>Derleyici hatası C3116

' depolama tanımlayıcısı ': arabirim yöntemi için geçersiz depolama sınıfı

**`typedef`** **`register`** **`static`** Bir arabirim yöntemi için depolama sınıfı olarak, veya öğesini kullandınız. Bu depolama sınıflarına arabirim üyelerinde izin verilmez.

Aşağıdaki örnek C3116 oluşturur:

```cpp
// C3116.cpp
__interface ImyInterface
{
   static void myFunc();   // C3116
};
```
