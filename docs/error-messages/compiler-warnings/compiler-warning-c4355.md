---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı C4355'
title: Derleyici Uyarısı C4355
ms.date: 11/04/2016
f1_keywords:
- C4355
helpviewer_keywords:
- C4355
ms.assetid: b819ecab-8a07-42d7-8fa4-1180d51626c0
ms.openlocfilehash: fd4d38aae7a3728370c89cb2298438dbc0ba616c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180779"
---
# <a name="compiler-warning-c4355"></a>Derleyici Uyarısı C4355

'this' : taban üye başlatıcı listesinde kullanıldı

**`this`** İşaretçi yalnızca statik olmayan üye işlevleri içinde geçerlidir. Temel sınıf için Başlatıcı listesinde kullanılamaz.

Temel sınıf oluşturucular ve sınıf üye oluşturucuları, oluşturucunun önüne çağırılır **`this`** . Aslında, oluşturulmamış bir nesneye başka bir oluşturucuya işaretçi geçirdiniz. Bu diğer oluşturucular herhangi bir üyeye veya çağrı üye işlevlerine erişse, sonuç tanımsız olur. **`this`** Tüm oluşturma tamamlanana kadar işaretçiyi kullanmamalısınız.

Bu uyarı varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Aşağıdaki örnek C4355 oluşturur:

```cpp
// C4355.cpp
// compile with: /w14355 /c
#include <tchar.h>

class CDerived;
class CBase {
public:
   CBase(CDerived *derived): m_pDerived(derived) {};
   ~CBase();
   virtual void function() = 0;

   CDerived * m_pDerived;
};

class CDerived : public CBase {
public:
   CDerived() : CBase(this) {};   // C4355 "this" used in derived c'tor
   virtual void function() {};
};

CBase::~CBase() {
   m_pDerived -> function();
}

int main() {
   CDerived myDerived;
}
```
