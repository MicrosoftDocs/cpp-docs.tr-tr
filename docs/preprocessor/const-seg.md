---
title: const_seg | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a3081837cc4516750f8c2c0d75cfc37eef208f9d
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2018
ms.locfileid: "42464762"
---
# <a name="constseg"></a>const_seg
Segmenti belirtir burada [const](../cpp/const-cpp.md) değişkenlerin .obj dosyasında depolanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#pragma const_seg ( [ [ { push | pop}, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 
Koşulları anlamını *segment* ve *bölümü* bu konudaki birbirinin yerine kullanılabilir.  
  
OBJ dosyaları görüntülenebilir [dumpbin](../build/reference/dumpbin-command-line.md) uygulama. .Obj dosyasındaki varsayılan segment `const` değişkenleri .rdata'dır. Bazı `const` skalerler gibi değişkenleri otomatik olarak satır içi kod akışı. Satır içine alınan kod .rdata'da görünmez.  
  
İçinde dinamik başlatma gerektiren bir nesne tanımlayan bir `const_seg` tanımsız davranışlara neden olur.  
  
`#pragma const_seg` Hiçbir parametre olmadan, segmenti .rdata olarak sıfırlar.  
  
*anında iletme* (isteğe bağlı)  
İç derleyici yığınına bir kayıt yerleştirir. A *anında iletme* olabilir bir *tanımlayıcı* ve *segment-name*.  
  
*POP* (isteğe bağlı)  
Derleyici iç yığının en üstünden bir kayıt kaldırır.  
  
*tanımlayıcı* (isteğe bağlı)  
İle kullanıldığında *anında iletme*, iç derleyici yığınındaki kayda bir ad atar. İle kullanıldığında *pop*, yığından kayıtları kadar iç yığının *tanımlayıcı* ; kaldırılır *tanımlayıcı* bulunamazsa iç yığında hiçbir şey kaldırılmaz.  
  
Kullanarak *tanımlayıcı* tek bir POP birden çok kayıt getirir *pop* komutu.  
  
"*segment-name*" (isteğe bağlı)  
Bir segmentin adı. İle kullanıldığında *pop*, yığın silinir ve *segment-name* etkin segment adı haline gelir.  
  
"*segment sınıfı*" (isteğe bağlı)  
Sürüm 2.0'dan önceki C++ ile uyumluluk sağlamak için dahil edilir. Yoksayılır.  
  
## <a name="example"></a>Örnek  
  
```cpp  
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
 
Bkz: [/SECTION](../build/reference/section-specify-section-attributes.md) kullanmamanız bölüm oluştururken adları listesi.  
  
Başlatılmış veriler için bölümler belirtebilirsiniz ([data_seg](../preprocessor/data-seg.md)), başlatılmamış veriler ([bss_seg](../preprocessor/bss-seg.md)) ve işlevleri ([code_seg](../preprocessor/code-seg.md)).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 
[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)