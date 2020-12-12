---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4183'
title: Derleyici Uyarısı (düzey 1) C4183
ms.date: 11/04/2016
f1_keywords:
- C4183
helpviewer_keywords:
- C4183
ms.assetid: dc48312c-4b34-44dd-80ff-eb5f11d5ca47
ms.openlocfilehash: 1e9753637d0ee52ef40ce875e4e2d66fbdaab9db
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266682"
---
# <a name="compiler-warning-level-1-c4183"></a>Derleyici Uyarısı (düzey 1) C4183

' tanımlayıcı ': dönüş türü eksik; ' int ' döndüren bir üye işlev olduğu varsayıldı

Bir sınıftaki veya yapıdaki üye işlevin satır içi tanımının dönüş türü yok. Bu üye işlevin varsayılan dönüş türüne sahip olduğu varsayılır **`int`** .

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
