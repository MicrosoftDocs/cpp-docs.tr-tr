---
title: Derleyici Uyarısı (düzey 1) C4183
ms.date: 11/04/2016
f1_keywords:
- C4183
helpviewer_keywords:
- C4183
ms.assetid: dc48312c-4b34-44dd-80ff-eb5f11d5ca47
ms.openlocfilehash: 4c2c7ce23cfaea5ebf31e78d84b7ff7fbdbf4c85
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175941"
---
# <a name="compiler-warning-level-1-c4183"></a>Derleyici Uyarısı (düzey 1) C4183

' tanımlayıcı ': dönüş türü eksik; ' int ' döndüren bir üye işlev olduğu varsayıldı

Bir sınıftaki veya yapıdaki üye işlevin satır içi tanımının dönüş türü yok. Bu üye işlevi, `int`varsayılan dönüş türüne sahip olduğu varsayılır.

Aşağıdaki örnek C4183 oluşturur:

```cpp
// C4183.cpp
// compile with: /W1 /c
#pragma warning(disable : 4430)
class MyClass1;
class MyClass2 {
   MyClass1() {};   // C4183
};
```
