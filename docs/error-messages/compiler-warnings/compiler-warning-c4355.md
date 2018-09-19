---
title: Derleyici Uyarısı C4355 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4355
dev_langs:
- C++
helpviewer_keywords:
- C4355
ms.assetid: b819ecab-8a07-42d7-8fa4-1180d51626c0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 44833c8e640002f2f94d44938641fa3c1fa33db7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46115313"
---
# <a name="compiler-warning-c4355"></a>Derleyici Uyarısı C4355

'this' : taban üye başlatıcı listesinde kullanıldı

**Bu** işaretçi yalnızca statik olmayan üye işlevlerinde geçerlidir. Başlatıcı listesinde bir temel sınıf için kullanılamaz.

Önce çağırılır temel sınıf oluşturucuları ve sınıf üye oluşturucuları **bu** Oluşturucusu. Aslında, unconstructed nesneyi başka bir oluşturucu için bir işaretçi geçirildi. Bu diğer oluşturucuların tüm üyelerine erişmek veya üye işlevlerini bu çağırın, sonucu tanımsız olur. Kullanmamalısınız **bu** tüm yapı tamamlanana kadar işaretçi.

Varsayılan olarak bu uyarıyı kapalıdır. Bkz: [derleyici uyarıları emin olan kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.

Aşağıdaki örnek, C4355 oluşturur:

```
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