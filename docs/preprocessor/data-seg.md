---
title: data_seg | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- data_seg_CPP
- vc-pragma.data_seg
dev_langs:
- C++
helpviewer_keywords:
- data_seg pragma
- pragmas, data_seg
ms.assetid: 65c66466-4c98-494f-93af-106beb4caf78
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7a463d966c681557525bb9512762731c01a7ce30
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="dataseg"></a>data_seg
Başlatılmış değişkenleri .obj dosyasında depolandığı veri kesimini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#pragma data_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Koşulları anlamını *segment* ve *bölüm* bu konudaki birbirinin yerine kullanılabilir.  
  
 OBJ dosyaları ile görüntülenebilir [DUMPBIN](../build/reference/dumpbin-command-line.md) uygulama. .Obj dosyasında başlatılmış değişkenleri için varsayılan kesimi .data ' dir. Başlatılmamış değişkenleri sıfır olarak başlatılması için kabul edilir ve .bss içinde depolanır.  
  
 **data_seg** parametresiz kesim için .data sıfırlar.  
  
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
// pragma_directive_data_seg.cpp  
int h = 1;                     // stored in .data  
int i = 0;                     // stored in .bss  
#pragma data_seg(".my_data1")  
int j = 1;                     // stored in "my_data1"  
  
#pragma data_seg(push, stack1, ".my_data2")     
int l = 2;                     // stored in "my_data2"  
  
#pragma data_seg(pop, stack1)   // pop stack1 off the stack  
int m = 3;                     // stored in "stack_data1"  
  
int main() {  
}  
```  
  
 Kullanılarak ayrılmış veri **data_seg** konumuna hakkında hiçbir bilgi sürdürmez.  
  
 Bkz: [/SECTION](../build/reference/section-specify-section-attributes.md) değil kullanmanız gereken bir bölüm oluştururken adları listesi.  
  
 Const değişkenleri için bölümleri de belirtebilirsiniz ([const_seg](../preprocessor/const-seg.md)), veri başlatılmadı ([bss_seg](../preprocessor/bss-seg.md)) ve işlevleri ([code_seg](../preprocessor/code-seg.md)).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)