---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3768'
title: Derleyici hatası C3768
ms.date: 11/04/2016
f1_keywords:
- C3768
helpviewer_keywords:
- C3768
ms.assetid: 091f0d53-1dff-43fd-813d-5c43c85b6ab0
ms.openlocfilehash: 3203fe74fb1da91f24312f76ca11ac49711da8f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291720"
---
# <a name="compiler-error-c3768"></a>Derleyici hatası C3768

> saf yönetilen kodda bir sanal vararg işlevinin adresi alınamaz

## <a name="remarks"></a>Açıklamalar

**/Clr: Pure** derleyici seçeneği visual Studio 2015 ' de kullanımdan kaldırılmıştır ve visual Studio 2017 ' de desteklenmez.

**/Clr: Pure** ile derlerken, sanal bir işlevin adresini alamaz `vararg` .

## <a name="example"></a>Örnek

Aşağıdaki örnek C3768 oluşturur:

```cpp
// C3768.cpp
// compile with: /clr:pure
struct A
{
   virtual void f(...);
};

int main()
{
   &(A::f);   // C3768
}
```
