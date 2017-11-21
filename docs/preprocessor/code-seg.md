---
title: code_seg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- code_seg_CPP
- vc-pragma.code_seg
dev_langs: C++
helpviewer_keywords:
- pragmas, code_seg
- code_seg pragma
ms.assetid: bf4faac1-a511-46a6-8d9e-456851d97d56
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 91834205187ecfa3c56c04aaac9cd0a2d25b49fe
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="codeseg"></a>code_seg
İşlevlerin .obj dosyasında saklandığı metin segmentini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#pragma code_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `code_seg` Pragma yönergesi örneklenen şablonları için oluşturulan nesne kodu ya da örtük olarak derleyici tarafından üretilen kod yerleşimini denetlemez — Örneğin, özel üye işlevleri. Kullanmanızı öneririz [__declspec(code_seg(...)) ](../cpp/code-seg-declspec.md) verdiğinden yerine özniteliğini kontrol tüm nesne kodu yerleştirme. Bu, derleyicinin ürettiği kodu içerir.  
  
 A *segment* bir .obj adlandırılmış bir birim olarak belleğe yüklenmiş bir veri bloğunun dosyasıdır. A *metin segment* yürütülebilir kod içeren bir kesim. Bu makalede, koşulları *segment* ve *bölüm* birbirlerinin yerine kullanılır.  
  
 `code_seg` Pragma yönergesi bildiren tüm sonraki nesne kodu çeviri biriminden adlı bir metin kesimi yerleştirilecek derleyici `segment-name`. Varsayılan olarak, .obj dosyasındaki işlevler için kullanılan metin segmenti .text olarak adlandırılır.  
  
 A `code_seg` parametresiz pragma yönergesi için .text sonraki nesne kodu metin segment adını sıfırlar.  
  
 **Anında iletme** (isteğe bağlı)  
 İç derleyici yığınına bir kayıt yerleştirir. A **itme** olabilir bir `identifier` ve `segment-name`.  
  
 **POP** (isteğe bağlı)  
 Derleyici iç yığının en üstünden bir kayıt kaldırır.  
  
 `identifier`(isteğe bağlı)  
 İle kullanıldığında **itme**, iç derleyici yığında kaydı bir adı atar. İle kullanıldığında **pop**, POP kadar iç yığından kayıtları `identifier` ; kaldırılır `identifier` bulunamadı iç yığında bir şey Sil'i.  
  
 `identifier`yalnızca biriyle Sil'i birden çok kayıt etkinleştirir **pop** komutu.  
  
 "`segment-name`" (isteğe bağlı)  
 Bir segmentin adı. İle kullanıldığında **pop**, yığın Sil'i ve `segment-name` etkin metin segment adı olur.  
  
 "`segment-class`" (isteğe bağlı)  
 Yoksayıldı, ancak C++ 2. 0 öncesi sürümler ile uyumluluk için eklendi.  
  
 Kullanabileceğiniz [DUMPBIN. EXE](../build/reference/dumpbin-command-line.md) .obj dosyaları görüntülemek için uygulama. Her bir desteklenen hedef mimari DUMPBIN sürümleri ile birlikte [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  
  
## <a name="example"></a>Örnek  
 Bu örnek nasıl kullanılacağını gösterir `code_seg` pragma yönergesi nesne kodu nereye put denetlemek için:  
  
```  
// pragma_directive_code_seg.cpp  
void func1() {                  // stored in .text  
}  
  
#pragma code_seg(".my_data1")  
void func2() {                  // stored in my_data1  
}  
  
#pragma code_seg(push, r1, ".my_data2")  
void func3() {                  // stored in my_data2  
}  
  
#pragma code_seg(pop, r1)      // stored in my_data1  
void func4() {  
}  
  
int main() {  
}  
```  
  
 Bir bölüm oluşturmak için kullanılmamalıdır adları listesi için bkz: [/SECTION](../build/reference/section-specify-section-attributes.md).  
  
 Bölümler başlatılmış veriler için de belirtebilirsiniz ([data_seg](../preprocessor/data-seg.md)), veri başlatılmadı ([bss_seg](../preprocessor/bss-seg.md)) ve const değişkenler ([const_seg](../preprocessor/const-seg.md)).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [code_seg (__declspec)](../cpp/code-seg-declspec.md)   
 [Pragma yönergeleri ve __Pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)