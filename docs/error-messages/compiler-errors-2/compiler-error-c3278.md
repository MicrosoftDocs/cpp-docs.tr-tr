---
title: Derleyici hatası C3278
ms.date: 11/04/2016
f1_keywords:
- C3278
helpviewer_keywords:
- C3278
ms.assetid: 56f818f5-85a6-4792-843b-54fe16327658
ms.openlocfilehash: ec51064853afa37f75022042c8c6121b6c5248a4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80201441"
---
# <a name="compiler-error-c3278"></a>Derleyici hatası C3278

> Interface veya saf '*Method*' metodunun doğrudan çağrısı çalışma zamanında başarısız olacak

## <a name="remarks"></a>Açıklamalar

Arabirim yöntemine veya saf yönteme bir çağrı yapıldı; buna izin verilmez.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3278 oluşturur:

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
