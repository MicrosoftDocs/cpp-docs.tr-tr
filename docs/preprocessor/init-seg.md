---
title: init_seg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc-pragma.init_seg
- init_seg_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, init_seg
- init_seg pragma
- data segment initializing [C++]
ms.assetid: 40a5898a-5c85-4aa9-8d73-3d967eb13610
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a092ed554af1b078772d53fd0cc663e250a6ea3c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="initseg"></a>init_seg
**C++ özel**  
  
 Hangi başlangıç kod yürütülür sırasını etkiler anahtar sözcüğü veya kod bir bölüm belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#pragma init_seg({ compiler | lib | user | "section-name" [, func-name]} )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Koşulları anlamını *segment* ve *bölüm* bu konudaki birbirinin yerine kullanılabilir.  
  
 Genel statik nesnelerin başlatılması kod yürütmek içerebildiğinden, nesneleri ne zaman oluşturulması tanımlayan bir anahtar belirtmeniz gerekir. Kullanmak özellikle önemlidir **init_seg** dinamik bağlantı kitaplıklarını (DLL'ler) pragma veya başlatma gerektiren kitaplığı.  
  
 Seçenekler **init_seg** pragma şunlardır:  
  
 **compiler**  
 Microsoft C çalışma zamanı kitaplığı başlatma için ayrılmış. Bu gruptaki nesneleri ilk oluşturulur.  
  
 **lib**  
 Üçüncü taraf sınıf kitaplığı satıcıların başlatmaları için kullanılabilir. Bu gruptaki nesneleri olanlar olarak işaretlenmiş sonra oluşturulan **derleyici** ancak tüm diğerlerinden önce.  
  
 **Kullanıcı**  
 Herhangi bir kullanıcı için kullanılabilir. Bu gruptaki nesneleri son oluşturulur.  
  
 *Bölüm adı*  
 Başlatma bölümünün açık belirtimi sağlar. Kullanıcı tanımlı nesneler *bölüm adı* örtük olarak oluşturulmuş değil; ancak, adreslerini tarafından adlandırılmış bölüm yerleştirilir *bölüm adı*.  
  
 Size bölüm adı pragma sonra bu modülde tanımlanmış genel nesneler oluşturmak yardımcı işlev işaretçileri içerir.  
  
 Değil kullanmanız gereken bir bölüm oluştururken adlarının listesi için bkz: [/SECTION](../build/reference/section-specify-section-attributes.md).  
  
 *işlev adı*  
 Bir işlevi yerine çağrılacak belirtir `atexit` program çıktığında. Bu yardımcı işlevi de çağırır [atexit](../c-runtime-library/reference/atexit.md) genel nesne yıkıcı bir işaretçi ile. Formun pragma içinde işlevi tanımlayıcı belirtirseniz,  
  
```  
int __cdecl myexit (void (__cdecl *pf)(void))  
```  
  
 C çalışma zamanı kitaplık yerine, işlev çağrılmaz sonra `atexit`. Bu nesneleri yok etmek hazır olduğunuzda çağrılması gerekir Yıkıcılar listesi oluşturmanıza olanak sağlar.  
  
 (Örneğin, bir DLL'de) başlatma erteleme gerekiyorsa bölüm adı açıkça belirtmeyi seçebilirsiniz. Ardından, statik her nesne için oluşturucular çağırmanız gerekir.  
  
 Tanımlayıcı için hiçbir tırnak vardır `atexit` değiştirme.  
  
 Diğer XXX_seg pragmaları tarafından tanımlanan bölümlerde hala nesnelerinizi yer alır.  
  
 C çalışma zamanı tarafından modülde tanımlanmış nesneleri otomatik olarak başlatılmayacak. Bu kendiniz yapmanız gerekir.  
  
 Varsayılan olarak, `init_seg` bölümleri salt okunur. Bölüm adı ise. CRT, derleyici sessizce değiştirir öznitelik salt okunur olarak işaretlenmiş olsa bile yazma.  
  
 Belirtemeyeceğiniz **init_seg** bir çeviri biriminde bir kereden fazla.  
  
 Nesnenizin açıkça kod içinde tanımlanan bir oluşturucu bir kullanıcı tarafından tanımlanan oluşturucu yok olsa bile derleyici birini (örneğin v tablo işaretçileri bağlamak) oluşturabilir.  Bu nedenle, kodunuzu derleyicinin ürettiği oluşturucuyu çağırmak olacaktır.  
  
## <a name="example"></a>Örnek  
  
```  
// pragma_directive_init_seg.cpp  
#include <stdio.h>  
#pragma warning(disable : 4075)  
  
typedef void (__cdecl *PF)(void);  
int cxpf = 0;   // number of destructors we need to call  
PF pfx[200];    // pointers to destructors.  
  
int myexit (PF pf) {  
   pfx[cxpf++] = pf;  
   return 0;  
}  
  
struct A {  
   A() { puts("A()"); }  
   ~A() { puts("~A()"); }  
};  
  
// ctor & dtor called by CRT startup code   
// because this is before the pragma init_seg  
A aaaa;   
  
// The order here is important.  
// Section names must be 8 characters or less.  
// The sections with the same name before the $  
// are merged into one section. The order that  
// they are merged is determined by sorting  
// the characters after the $.  
// InitSegStart and InitSegEnd are used to set  
// boundaries so we can find the real functions  
// that we need to call for initialization.  
  
#pragma section(".mine$a", read)  
__declspec(allocate(".mine$a")) const PF InitSegStart = (PF)1;  
  
#pragma section(".mine$z",read)  
__declspec(allocate(".mine$z")) const PF InitSegEnd = (PF)1;  
  
// The comparison for 0 is important.  
// For now, each section is 256 bytes. When they  
// are merged, they are padded with zeros. You  
// can't depend on the section being 256 bytes, but  
// you can depend on it being padded with zeros.  
  
void InitializeObjects () {  
   const PF *x = &InitSegStart;  
   for (++x ; x < &InitSegEnd ; ++x)  
      if (*x) (*x)();  
}  
  
void DestroyObjects () {  
   while (cxpf>0) {  
      --cxpf;  
      (pfx[cxpf])();  
   }  
}  
  
// by default, goes into a read only section  
#pragma init_seg(".mine$m", myexit)  
  
A bbbb;   
A cccc;  
  
int main () {  
   InitializeObjects();  
   DestroyObjects();  
}  
```  
  
```Output  
A()  
A()  
A()  
~A()  
~A()  
~A()  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)