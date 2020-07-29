---
title: Derleyici hatası C2714
ms.date: 07/22/2020
f1_keywords:
- C2714
helpviewer_keywords:
- C2714
ms.assetid: 401a5a42-660c-4bad-9d63-1a2d092bc489
ms.openlocfilehash: d3f733f065af5b3217dc19d46b46e504d39151f4
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225416"
---
# <a name="compiler-error-c2714"></a>Derleyici hatası C2714

> `alignof(void)`izin verilmiyor

Bir işlece geçersiz bir değer geçirildi.

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [ `alignof` işleç](../../cpp/alignof-operator.md) .

## <a name="example"></a>Örnek

Aşağıdaki örnek C2714 oluşturur.

```cpp
// C2714.cpp
int main() {
   return alignof(void);   // C2714
   return alignof(char);   // OK
}
```
