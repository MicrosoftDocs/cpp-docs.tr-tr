---
title: code_seg | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- code_seg_CPP
- vc-pragma.code_seg
dev_langs:
- C++
helpviewer_keywords:
- pragmas, code_seg
- code_seg pragma
ms.assetid: bf4faac1-a511-46a6-8d9e-456851d97d56
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 052e9a55d443fa263ecf8443c9e3933baeb1f3b8
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/14/2018
ms.locfileid: "42465630"
---
# <a name="codeseg"></a>code_seg
İşlevlerin .obj dosyasında saklandığı metin segmentini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#pragma code_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 
**Code_seg** pragma yönergesi, örneklenmiş şablonlar için oluşturulan nesne kodunun ya da örtük olarak derleyici tarafından oluşturulan kodu yerleşimini denetlemez — Örneğin, özel üye işlevleri. Kullanmanızı öneririz [__declspec(code_seg(...)) ](../cpp/code-seg-declspec.md) verdiğinden özniteliği, bunun yerine, tüm nesne kodu yerleşimi üzerinde denetim. Bu, derleyicinin ürettiği kodu içerir.  
  
A *segment* belleğe bir birim olarak yüklenen verilerin adlandırılmış bir blok içinde bir .obj dosyasıdır. A *metin segmenti* yürütülebilir kod içeren bir segmenttir. Bu makalede, koşulları *segment* ve *bölümü* birbirinin yerine kullanılır.  
  
**Code_seg** pragma yönergesi, derleyicinin tüm sonraki nesne kodlarının çeviri biriminden adlı bir metin segmentine yerleştirilmesini söyler *segment-name*. Varsayılan olarak, .obj dosyasındaki işlevler için kullanılan metin segmenti .text olarak adlandırılır.  
  
A **code_seg** parametresiz pragma yönergesi metin segmentinin adı için sonraki nesne kodu .text olarak sıfırlar.  
  
*anında iletme* (isteğe bağlı)  
İç derleyici yığınına bir kayıt yerleştirir. A *anında iletme* olabilir bir *tanımlayıcı* ve *segment-name*.  
  
*POP* (isteğe bağlı)  
Derleyici iç yığının en üstünden bir kayıt kaldırır.  
  
*tanımlayıcı* (isteğe bağlı)  
İle kullanıldığında *anında iletme*, iç derleyici yığınındaki kayda bir ad atar. İle kullanıldığında *pop*, yığından kayıtları kadar iç yığının *tanımlayıcı* ; kaldırılır *tanımlayıcı* bulunamazsa iç yığında hiçbir şey kaldırılmaz.  
  
*tanımlayıcı* ile yalnızca bir tane POP birden çok kayıt getirir *pop* komutu.  
  
"*segment-name*" (isteğe bağlı)  
Bir segmentin adı. İle kullanıldığında *pop*, yığın silinir ve *segment-name* etkin metin segmentinin adı haline gelir.  
  
"*segment sınıfı*" (isteğe bağlı)  
Yoksayıldı, ancak C++ 2. 0 öncesi sürümler ile uyumluluk için eklendi.  
  
Kullanabileceğiniz [DUMPBIN. EXE](../build/reference/dumpbin-command-line.md) .obj dosyalarını görüntülemek için uygulama. Visual Studio ile DUMPBIN sürümleri her desteklenen hedef mimari dahildir.  
  
## <a name="example"></a>Örnek  

Bu örnek nasıl kullanılacağını gösterir **code_seg** pragma yönergesini nesne kodunun nereye yerleştirildiğini denetlemek için:  
  
```cpp  
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
  
Bir bölüm oluşturmak için kullanılmaması adlarının listesi için bkz. [/SECTION](../build/reference/section-specify-section-attributes.md).  
  
Başlatılmış veriler için bölümler belirtebilirsiniz ([data_seg](../preprocessor/data-seg.md)), başlatılmamış veriler ([bss_seg](../preprocessor/bss-seg.md)) ve const değişkenleri ([const_seg](../preprocessor/const-seg.md)).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 
[code_seg (__declspec)](../cpp/code-seg-declspec.md)   
[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)