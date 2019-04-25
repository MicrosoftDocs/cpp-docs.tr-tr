---
title: Derleyici Hatası C2815
ms.date: 11/04/2016
f1_keywords:
- C2815
helpviewer_keywords:
- C2815
ms.assetid: d0256fd6-0721-4c99-b03c-52d96e77a613
ms.openlocfilehash: ab6708e7ae0a56bd71adebad4fb42d6ea9abe116
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62175413"
---
# <a name="compiler-error-c2815"></a>Derleyici Hatası C2815

'operator delete': ilk biçimsel parametre olmalıdır ' void *', ancak 'param' kullanıldı

Tüm kullanıcı tanımlı [delete işleci](../../standard-library/new-operators.md#op_delete) işlevi türünde bir ilk biçimsel parametre gerçekleştirmeniz gereken `void *`.

Aşağıdaki örnek, C2815 oluşturur:

```
// C2815.cpp
// compile with: /c
class CMyClass {
public:
   void mf1(int *a);
   void operator delete(CMyClass *);   // C2815
   void operator delete(void *);
};
```