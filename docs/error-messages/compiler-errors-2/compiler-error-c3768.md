---
title: Derleyici Hatası C3768
ms.date: 11/04/2016
f1_keywords:
- C3768
helpviewer_keywords:
- C3768
ms.assetid: 091f0d53-1dff-43fd-813d-5c43c85b6ab0
ms.openlocfilehash: e9c385fd178dc967e72f5e0ca7fab27b28ad962f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50676755"
---
# <a name="compiler-error-c3768"></a>Derleyici Hatası C3768

> saf yönetilen kod içindeki sanal vararg işlevinin adresi alınamaz

## <a name="remarks"></a>Açıklamalar

**/CLR: pure** derleyici seçeneğini Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor.

İle derlerken **/CLR: pure**, sanal bir adresi alınamaz `vararg` işlevi.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3768 oluşturur:

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