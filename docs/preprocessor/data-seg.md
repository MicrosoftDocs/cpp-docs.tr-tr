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
ms.openlocfilehash: b1be97919f0f5b55d6e63eca8e59eb15e8ef9dff
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2018
ms.locfileid: "42466159"
---
# <a name="dataseg"></a>data_seg
Başlatılmamış değişkenler .obj dosyasında depolandığı veri segmenti belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#pragma data_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## <a name="remarks"></a>Açıklamalar 

Koşulları anlamını *segment* ve *bölümü* bu konudaki birbirinin yerine kullanılabilir.  
  
OBJ dosyaları görüntülenebilir [dumpbin](../build/reference/dumpbin-command-line.md) uygulama. Başlatılmış değişkenleri için .obj dosyasındaki varsayılan segment .data ' dir. Başlatılmamış değişkenler sıfıra başlatılması kabul edilir ve .bss içinde depolanır.  
  
**data_seg** hiçbir parametre olmadan için .data kesimi sıfırlar.  
  
*anında iletme* (isteğe bağlı)  
İç derleyici yığınına bir kayıt yerleştirir. A *anında iletme* olabilir bir *tanımlayıcı* ve *segment-name*.  
  
*POP* (isteğe bağlı)  
Derleyici iç yığının en üstünden bir kayıt kaldırır.  
  
*tanımlayıcı* (isteğe bağlı)  
İle kullanıldığında *anında iletme*, iç derleyici yığınındaki kayda bir ad atar. İle kullanıldığında *pop*, yığından kayıtları kadar iç yığının *tanımlayıcı* ; kaldırılır *tanımlayıcı* bulunamazsa iç yığında hiçbir şey kaldırılmaz.  
  
*tanımlayıcı* tek bir POP birden çok kayıt getirir *pop* komutu.  
  
*"segment-name"*(isteğe bağlı)  
Bir segmentin adı. İle kullanıldığında *pop*, yığın silinir ve *segment-name* etkin segment adı haline gelir.  
  
*"segment-class"* (isteğe bağlı)  
Sürüm 2.0'dan önceki C++ ile uyumluluk sağlamak için dahil edilir. Yoksayılır.  
  
## <a name="example"></a>Örnek  
  
```cpp  
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
  
Kullanılarak yer ayrılmış veri **data_seg** konumuna hakkındaki tüm bilgileri sürdürmez.  
  
Bkz: [/SECTION](../build/reference/section-specify-section-attributes.md) kullanmamanız bölüm oluştururken adları listesi.  
  
Const değişkenleri için bölümler belirtebilirsiniz ([const_seg](../preprocessor/const-seg.md)), başlatılmamış veriler ([bss_seg](../preprocessor/bss-seg.md)) ve işlevleri ([code_seg](../preprocessor/code-seg.md)).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 
[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)