---
title: Derleyici Hatası C3768 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3768
dev_langs:
- C++
helpviewer_keywords:
- C3768
ms.assetid: 091f0d53-1dff-43fd-813d-5c43c85b6ab0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5e6b7a2d1617591609f75b2b07f1a94983ee22f4
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704964"
---
# <a name="compiler-error-c3768"></a>Derleyici Hatası C3768

> bir sanal vararg işlev adresi saf yönetilen kodda alamıyor

## <a name="remarks"></a>Açıklamalar

**/CLR: pure** derleyici seçeneği Visual Studio 2015'te kullanım dışı ve Visual Studio 2017 içinde desteklenmiyor.

İle derleme yapılırken **/CLR: pure**, bir sanal adresini alamıyor `vararg` işlevi.

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