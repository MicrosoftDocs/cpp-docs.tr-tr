---
title: Derleyici Uyarısı C4355
ms.date: 11/04/2016
f1_keywords:
- C4355
helpviewer_keywords:
- C4355
ms.assetid: b819ecab-8a07-42d7-8fa4-1180d51626c0
ms.openlocfilehash: 6b74c8dd5ce9860cb218d21790f12ba05e9be22f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62151831"
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