---
title: Derleyici Uyarısı (düzey 1) C4378 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4378
dev_langs:
- C++
helpviewer_keywords:
- C4378
ms.assetid: d08e11ef-891a-4752-9a5e-360e7394acf7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b34e02b884546bd1b7a3858ba6b668fd3d45258f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46135808"
---
# <a name="compiler-warning-level-1-c4378"></a>Derleyici Uyarısı (düzey 1) C4378

Başlatıcıları çalıştırmak için işlev işaretçilerinin edinmeniz gerekir; :: resolvemethodhandle kullanmayı düşünün

Altında **/CLR**, başlatıcı sembolleri işlevi belirteçleri, işlev işaretçilerini içerir.  Belirteçleri kullanarak işaretçileri dönüştürmek gereken <xref:System.ModuleHandle.ResolveMethodHandle%2A>.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4378 oluşturur.

```
// C4378.cpp
// compile with: /W1 /clr /c
typedef void (__cdecl *PF)(void);
int cxpf = 0;   // number of destructors to call
PF pfx[200];   // ptrs to those dtors, watch for overflow

int myexit (PF pf) {
   pfx[cxpf++] = pf;
   return 0;
}

struct A {
   A() {}
   ~A() {}
};

A aaaa;

#pragma data_seg(".mine$a")
PF InitSegStart = (PF)1;
#pragma data_seg(".mine$z")
PF InitSegEnd = (PF)1;
#pragma data_seg()

void InitializeObjects () {
   PF *x = &InitSegStart;
   for (++x ; x < &InitSegEnd ; ++x)
      if (*x)
         (*x)();
}

#pragma init_seg(".mine$m",myexit)   // C4378
A bbbb;   // crash

int main () {
   InitializeObjects();
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4378 çözme işlemi gösterilmektedir.

```
// C4378_b.cpp
// compile with: /clr
#pragma warning(disable:4378)
using namespace System;
typedef void (__cdecl *PF)(void);
typedef void (__clrcall * CLRPF)(void);

int cxpf = 0;  // number of destructors we need to call
PF pfx[200];   // ptrs to those dtors. Watch out for overflow!

ref class TypeClassHolder {
public:
   static TypeClassHolder ^typeClass = gcnew TypeClassHolder();
};

CLRPF FuncTokenToFuncPtr(PF tknFunc) {
   ModuleHandle type =
      Type::GetTypeFromHandle(Type::GetTypeHandle(TypeClassHolder::typeClass))->Module->ModuleHandle;
   return (CLRPF)type.ResolveMethodHandle((int)(size_t)(tknFunc)).GetFunctionPointer().ToPointer();
}

int myexit (PF pf) {
   pfx[cxpf++] = pf;
   return 0;
}

struct A {
   A() {}
   ~A() {}
};

A aaaa;

#pragma data_seg(".mine$a")
PF InitSegStart = (PF)1;
#pragma data_seg(".mine$z")
PF InitSegEnd = (PF)1;
#pragma data_seg()

void InitializeObjects () {
   PF *x = &InitSegStart;
   for (++x ; x < &InitSegEnd ; ++x)
      if(*x) {
         CLRPF realppfunc;
         realppfunc = FuncTokenToFuncPtr(*x);
         (realppfunc)();
      }
}

#pragma init_seg(".mine$m",myexit)
A bbbb; // constructor call succeeds

int main () {
   InitializeObjects();
}
```