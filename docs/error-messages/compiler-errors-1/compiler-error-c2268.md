---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2268'
title: Derleyici hatası C2268
ms.date: 11/04/2016
f1_keywords:
- C2268
helpviewer_keywords:
- C2268
ms.assetid: 0ed055c9-3c6f-4df2-a5b6-85cf0e01a249
ms.openlocfilehash: 2ce70c43cc9365aebdf8441b916715ac67731c49
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295048"
---
# <a name="compiler-error-c2268"></a>Derleyici hatası C2268

' function ', derleyici önceden tanımlanmış bir kitaplık yardımcıdır. Kitaplık yardımcıları/GL ile desteklenmez; ' File ' nesne dosyasını/GLNO olmadan derleyin.

Kaynak kodunuzda tanımlanan bir işlev, iç derleyici işleviyle aynı ada sahip. İşlev içeren modülü [/GL](../../build/reference/gl-whole-program-optimization.md)olmadan derleyin.

Aşağıdaki örnek C2268 oluşturur:

```c
// C2268.c
// compile with: /c
// processor: x86
extern int SHFusionLoadLibrary(int lpLibFileName);

int __cdecl _except_handler3(void) {
   return SHFusionLoadLibrary(0);
}

extern int main(void);

void* mainCRTStartup(void* p) {
   p = main;
   return p;
}
```

ve ardından:

```c
// C2268b.c
// compile with: C2268.c /EHsc /GL /Ob0 /O2 /Fa /GS- /link /nodefaultlib
// processor: x86
extern int SHFusionLoadLibrary(int lpLibFileName);

extern int __cdecl _except_handler3(void);
extern void mainCRTStartup(void*);
int g = 2;

#define ENTERCONTEXT(fail) \
   int ulCookie = 0;\
   if (!SHActivateContext(&ulCookie)) \
      return fail;\
   __try {

#define LEAVECONTEXT \
    } __finally {SHDeactivateContext(ulCookie);}

int SHActivateContext(int* a) {
    return *a == g || !*a ||_except_handler3();
}

void SHDeactivateContext(int a) {
    g = a;
}

int SHFusionLoadLibrary(int lpLibFileName) {   // C2268
    ENTERCONTEXT(0)
    g = lpLibFileName;
    LEAVECONTEXT

    return lpLibFileName;
}

int main(void) {
    g = SHFusionLoadLibrary(10);
    return 0;
}
```
