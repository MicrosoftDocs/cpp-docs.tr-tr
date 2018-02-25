---
title: const_seg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc-pragma.const_seg
- const_seg_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, const_seg
- const_seg pragma
ms.assetid: 1eb58ee2-fb0e-4a39-9621-699c8f5ef957
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c4c87ee9f0e867223186868de0ef2b39203c3710
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="constseg"></a>const_seg
Kesimini belirtir nerede [const](../cpp/const-cpp.md) değişkenleri .obj dosyasında depolanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#pragma const_seg ( [ [ { push | pop}, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Koşulları anlamını *segment* ve *bölüm* bu konudaki birbirinin yerine kullanılabilir.  
  
 OBJ dosyaları ile görüntülenebilir [DUMPBIN](../build/reference/dumpbin-command-line.md) uygulama. .Obj dosyasında varsayılan kesimi `const` değişkenleri olan .rdata. Bazı `const` skalerler gibi değişkenleri otomatik olarak kod akışa içermesinden. Satır içine alınan kod .rdata'da görünmez.  
  
 Dinamik başlatma gerektiren bir nesneyi tanımlayan bir `const_seg` tanımsız davranışa neden olur.  
  
 `#pragma const_seg` Parametresiz kesim için .rdata sıfırlar.  
  
 `push` (isteğe bağlı)  
 İç derleyici yığınına bir kayıt yerleştirir. A `push` olabilir bir `identifier` ve `segment-name`.  
  
 `pop` (isteğe bağlı)  
 Derleyici iç yığının en üstünden bir kayıt kaldırır.  
  
 `identifier` (isteğe bağlı)  
 İle kullanıldığında `push`, iç derleyici yığında kaydı bir adı atar. İle kullanıldığında `pop`, POP kadar iç yığından kayıtları `identifier` ; kaldırılır `identifier` bulunamadı iç yığında bir şey Sil'i.  
  
 Kullanarak `identifier` tek bir tıklatmayla Sil'i birden çok kayıt etkinleştirir `pop` komutu.  
  
 "`segment-name`" (isteğe bağlı)  
 Bir segmentin adı. İle kullanıldığında `pop`, yığın Sil'i ve `segment-name` etkin kesimi adı olur.  
  
 "`segment-class`" (isteğe bağlı)  
 Sürüm 2.0'dan önceki C++ ile uyumluluk sağlamak için dahil edilir. Yoksayılır.  
  
## <a name="example"></a>Örnek  
  
```  
// pragma_directive_const_seg.cpp  
// compile with: /EHsc  
#include <iostream>  
  
const int i = 7;               // inlined, not stored in .rdata  
const char sz1[]= "test1";     // stored in .rdata  
  
#pragma const_seg(".my_data1")  
const char sz2[]= "test2";     // stored in .my_data1  
  
#pragma const_seg(push, stack1, ".my_data2")  
const char sz3[]= "test3";     // stored in .my_data2  
  
#pragma const_seg(pop, stack1) // pop stack1 from stack  
const char sz4[]= "test4";     // stored in .my_data1  
  
int main() {  
    using namespace std;  
   // const data must be referenced to be put in .obj  
   cout << sz1 << endl;  
   cout << sz2 << endl;  
   cout << sz3 << endl;  
   cout << sz4 << endl;  
}  
```  
  
```Output  
test1  
test2  
test3  
test4  
```  
  
## <a name="comments"></a>Açıklamalar  
 Bkz: [/SECTION](../build/reference/section-specify-section-attributes.md) değil kullanmanız gereken bir bölüm oluştururken adları listesi.  
  
 Bölümler başlatılmış veriler için de belirtebilirsiniz ([data_seg](../preprocessor/data-seg.md)), veri başlatılmadı ([bss_seg](../preprocessor/bss-seg.md)) ve işlevleri ([code_seg](../preprocessor/code-seg.md)).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)