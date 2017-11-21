---
title: bss_seg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc-pragma.bss_seg
- bss_seg_CPP
dev_langs: C++
helpviewer_keywords:
- pragmas, bss_seg
- bss_seg pragma
ms.assetid: 755f0154-de51-4778-97d3-c9b24e445079
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 95fbd0b845bc3e827e2e62c4bd2e97f5cff220d3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="bssseg"></a>bss_seg
Başlatılmamış değişkenleri .obj dosyasında depolandığı kesimini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#pragma bss_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Obj dosyaları ile görüntülenebilir [DUMPBIN](../build/reference/dumpbin-command-line.md) uygulama. Başlatılmamış veriler için .obj dosyasında varsayılan kesimi .bss ' dir. Bazı durumlarda kullanımını **bss_seg** hızlandırabilir yükleme süreleri bir bölüme başlatılmamış veri gruplandırarak.  
  
 **bss_seg** parametresiz kesim için .bss sıfırlar.  
  
 **anında iletme**(isteğe bağlı)  
 İç derleyici yığınına bir kayıt yerleştirir. A **itme** olabilir bir *tanımlayıcısı* ve *segment adı*.  
  
 **POP** (isteğe bağlı)  
 Derleyici iç yığının en üstünden bir kayıt kaldırır.  
  
 *tanımlayıcı* (isteğe bağlı)  
 İle kullanıldığında **itme**, iç derleyici yığında kaydı bir adı atar. İle kullanıldığında **pop**, POP kadar iç yığından kayıtları *tanımlayıcısı* ; kaldırılır *tanımlayıcısı* bulunamadı iç yığında bir şey Sil'i.  
  
 *tanımlayıcı* tek bir tıklatmayla Sil'i birden çok kayıt etkinleştirir **pop** komutu.  
  
 *"segment-name"*(isteğe bağlı)  
 Bir segmentin adı. İle kullanıldığında **pop**, yığın Sil'i ve *segment adı* etkin kesimi adı olur.  
  
 *"sınıf segment"* (isteğe bağlı)  
 Sürüm 2.0'dan önceki C++ ile uyumluluk sağlamak için dahil edilir. Yoksayılır.  
  
## <a name="example"></a>Örnek  
  
```  
// pragma_directive_bss_seg.cpp  
int i;                     // stored in .bss  
#pragma bss_seg(".my_data1")  
int j;                     // stored in "my_data1"  
  
#pragma bss_seg(push, stack1, ".my_data2")     
int l;                     // stored in "my_data2"  
  
#pragma bss_seg(pop, stack1)   // pop stack1 from stack  
int m;                     // stored in "stack_data1"  
  
int main() {  
}  
```  
  
 Bölümler başlatılmış veriler için de belirtebilirsiniz ([data_seg](../preprocessor/data-seg.md)), işlevleri ([code_seg](../preprocessor/code-seg.md)) ve const değişkenler ([const_seg](../preprocessor/const-seg.md)).  
  
 Kullanılarak ayrılmış veri **bss_seg** pragma konumuna hakkında hiçbir bilgi korumak değil.  
  
 Bkz: [/SECTION](../build/reference/section-specify-section-attributes.md) değil kullanmanız gereken bir bölüm oluştururken adları listesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pragma yönergeleri ve __Pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)