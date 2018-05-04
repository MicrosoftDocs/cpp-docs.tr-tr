---
title: Naked işlevleri için kurallar ve sınırlamalar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- naked functions [C++]
ms.assetid: ff203858-2dd3-4a76-8a57-d0d06817adef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cb18f3e75bb7d912cbafbde01893d6283a4c61f6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="rules-and-limitations-for-naked-functions"></a>Naked İşlevleri için Kurallar ve Sınırlamalar
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Naked işlevleri için aşağıdaki kurallar ve sınırlamalar uygulanır:  
  
-   `return` Deyimi izin verilmez.  
  
-   Yığın çerçevesi bırakma gerekir çünkü yapılandırılmış özel durum işleme ve C++ özel durum işleme yapılarına izin verilmez.  
  
-   Aynı nedenle, herhangi bir biçimde `setjmp` engellendi.  
  
-   Kullanımı `_alloca` işlevi yasaktır.  
  
-   Yerel değişkenler için hiçbir başlatma kodu önce giriş sırası görünmesini sağlamak için başlatılmış yerel değişkenler işlevi kapsamda izin verilmez. Özellikle, C++ nesneleri bildirimi işlevi kapsamında izin verilmiyor. Ancak olabilir başlatılmış veri iç içe geçmiş kapsamdaki.  
  
-   Çerçeve işaretçisi en iyi duruma getirme (/Oy derleyici seçeneği) önerilmez, ancak otomatik olarak çıplak işlev için engellenir.  
  
-   C++ sınıf nesnelerinin işlevi sözcük kapsamındaki bildiremezsiniz. Ancak, iç içe geçmiş bir bloğu içindeki nesneleri bildirebilirsiniz.  
  
-   `naked` Anahtar sözcüğü ile derleme yapılırken yoksayılır [/CLR](../build/reference/clr-common-language-runtime-compilation.md).  
  
-   İçin [__fastcall](../cpp/fastcall.md) naked işlevleri, C/C++ kod kayıt bağımsız değişkenlerden biri için bir başvuru olduğunda giriş kodu değerlerin konusu kasanın Bu değişken için yığın konuma depolamanız gerekir. Örneğin:  
  
```  
// nkdfastcl.cpp  
// compile with: /c  
// processor: x86  
__declspec(naked) int __fastcall  power(int i, int j) {  
   // calculates i^j, assumes that j >= 0  
  
   // prolog  
   __asm {  
      push ebp  
      mov ebp, esp  
      sub esp, __LOCAL_SIZE  
     // store ECX and EDX into stack locations allocated for i and j  
     mov i, ecx  
     mov j, edx  
   }  
  
   {  
      int k = 1;   // return value  
      while (j-- > 0)   
         k *= i;  
      __asm {   
         mov eax, k   
      };  
   }  
  
   // epilog  
   __asm {  
      mov esp, ebp  
      pop ebp  
      ret  
   }  
}  
```  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Naked İşlevi Çağrıları](../cpp/naked-function-calls.md)