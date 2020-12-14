---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4125'
title: Derleyici Uyarısı (düzey 4) C4125
ms.date: 11/04/2016
f1_keywords:
- C4125
helpviewer_keywords:
- C4125
ms.assetid: a081d1f4-0789-4915-91df-7ff0b28ca245
ms.openlocfilehash: 82c94743e2ff52efacdf1b5f139bc4d9d40d0eed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261924"
---
# <a name="compiler-warning-level-4-c4125"></a>Derleyici Uyarısı (düzey 4) C4125

ondalık basamak sekizlik kaçış sırasını sonlandırır

Derleyici sekizli sayıyı ondalık basamak olmadan değerlendirir ve ondalık basamağın bir karakter olduğunu varsayar.

## <a name="example"></a>Örnek

```cpp
// C4125a.cpp
// compile with: /W4
char array1[] = "\709"; // C4125
int main()
{
}
```

9. basamak bir karakter olarak tasarlanıyorsa, örneği aşağıdaki gibi düzeltin:

```cpp
// C4125b.cpp
// compile with: /W4
char array[] = "\0709";  // C4125 String containing "89"
int main()
{
}
```
