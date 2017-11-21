---
title: "Derleyici Hatası C2268 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2268
dev_langs: C++
helpviewer_keywords: C2268
ms.assetid: 0ed055c9-3c6f-4df2-a5b6-85cf0e01a249
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 38ac7b0aa76a16516652bfc1736826072ad473dd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2268"></a>Derleyici Hatası C2268
'' bir önceden tanımlanmış derleyici kitaplığı yardımcı işlevdir. Kitaplık Yardımcıları ile /GL desteklenmez; nesne dosyası /GL. olmadan ' dosya' derleme  
  
 Kaynak kodunuz tanımlanan bir işlev bir iç derleyici işlevinde aynı ada sahiptir. İşlev olmadan içeren modülü derleme [/GL](../../build/reference/gl-whole-program-optimization.md).  
  
 Aşağıdaki örnek C2268 oluşturur:  
  
```  
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
  
 Ve ardından:  
  
```  
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