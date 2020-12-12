---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2714'
title: Derleyici hatası C2714
ms.date: 07/22/2020
f1_keywords:
- C2714
helpviewer_keywords:
- C2714
ms.assetid: 401a5a42-660c-4bad-9d63-1a2d092bc489
ms.openlocfilehash: 7bea0fc27de49f5767b8b250254f255964423cdc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320837"
---
# <a name="compiler-error-c2714"></a>Derleyici hatası C2714

> `alignof(void)` izin verilmiyor

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
