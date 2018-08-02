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
ms.openlocfilehash: d49f915174383273f538c38a6ec002558601ca10
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39466676"
---
# <a name="rules-and-limitations-for-naked-functions"></a>Naked İşlevleri için Kurallar ve Sınırlamalar
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Naked işlevleri için aşağıdaki kurallar ve sınırlamalar uygulanır:  
  
-   **Dönüş** deyimi izin verilmez.  
  
-   Yığın çerçevesi geriye doğru olduğundan yapılandırılmış özel durum işleme ve C++ özel durum işleme yapılarına izin verilmez.  
  
-   Aynı nedenle, herhangi bir biçimde `setjmp` yasaktır.  
  
-   Kullanım `_alloca` işlevi kullanılamaz.  
  
-   Yerel değişkenler için başlatma kodu yok önce giriş dizisinde görünmesini sağlamak için başlatılmamış yerel değişkenleri işlev kapsamında izin verilmez. Özellikle, C++ nesnelerin bildirimi işlev kapsamında izin verilmiyor. Ancak olabilir başlatılmış veriler iç içe bir kapsam içinde.  
  
-   Çerçeve işaretçisi iyileştirme (/Oy derleyici seçeneği) önerilmez, ancak otomatik olarak çıplak bir işlev için engellenir.  
  
-   C++ sınıfı nesne işlevi sözlü kapsamda bildiremezsiniz. Ancak, iç içe geçmiş bir bloğu içindeki nesneleri bildirebilirsiniz.  
  
-   **Naked** ile derleme yaparken anahtar sözcüğünü sayılır [/CLR](../build/reference/clr-common-language-runtime-compilation.md).  
  
-   İçin [__fastcall](../cpp/fastcall.md) çıplak İşlevler, C/C++ kodu yazmaç bağımsız değişkenlerden biri için bir başvuru olduğunda giriş kodu, bu değişken için yığın konumunu yazmacına değerlerini depolamanız gerekir. Örneğin:  
  
```cpp 
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
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Naked İşlevi Çağrıları](../cpp/naked-function-calls.md)