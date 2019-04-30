---
title: Derleyici Hatası C3278
ms.date: 11/04/2016
f1_keywords:
- C3278
helpviewer_keywords:
- C3278
ms.assetid: 56f818f5-85a6-4792-843b-54fe16327658
ms.openlocfilehash: 7618336c08dd111e495d7e4102b8e61c6e927c39
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62382095"
---
# <a name="compiler-error-c3278"></a>Derleyici Hatası C3278

> doğrudan çağrı saf yönteminin veya arabiriminin '*yöntemi*' çalışma zamanında başarısız olur

## <a name="remarks"></a>Açıklamalar

Bir arabirim yöntemini veya verilmeyen saf bir yöntemle bir çağrı yapıldı.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3278 oluşturur:

```cpp
// C3278_2.cpp
// compile with: /clr
using namespace System;
interface class I
{
   void vmf();
};

public ref class C: public I
{
public:
   void vmf()
   {
      Console::WriteLine( "In C::vmf()" );
      I::vmf(); // C3278
   }

};

int main()
{
   C^ pC = gcnew C;
   pC->vmf();
}
```