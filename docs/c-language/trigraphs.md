---
title: "Trigrafları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ??) trigraph
- ??- trigraph
- question mark, in trigraphs
- ??= trigraph
- ?? trigraph
- ??< trigraph
- ??/ trigraph
- trigraphs
- '? symbol, trigraph'
- ??> trigraph
- ??! trigraph
- ??' trigraph
ms.assetid: 617f76ec-b8e8-4cfe-916c-4bc32cbd9aeb
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a480a38411536266c8cd4c23f8b29190550d3444
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="trigraphs"></a>Trigraflar
C kaynak programlarının kaynak karakter kümesi 7 bit ASCII karakter kümesi içinde yer alır, ancak ISO 646-1983 Sabit Kod Kümesi'nin bir üst kümesidir. Trigraf dizileri, C programlarının yalnızca ISO (Uluslararası Standartlar Enstitüsü) Sabit Kod Kümesi kullanarak yazılmasına izin verir. Trigraflar, derleyicinin karşılık gelen noktalama karakterleriyle değiştirdiği üç karakterli dizilerdir (birbirini izleyen iki soru işareti ile yazılır). Trigrafları, C kaynak dosyalarında bazı noktalama karakterleri için uygun grafik sunumlar içermeyen bir karakter kümesiyle kullanabilirsiniz.  
  
 C ++ 17 trigrafları dilinden kaldırır. Uygulamaları uygulama tanımlı eşlemeden fiziksel kaynak dosyaya bir parçası olarak trigrafları desteklemeye devam edebilir *temel kaynak karakter kümesi*ancak bunu yapmak için uygulamalar standart önerir. C ++ 14, olduğu gibi C. trigrafları desteklenir  
  
 Visual C++ trigrafı değiştirme desteklemeye devam eder, ancak varsayılan olarak devre dışıdır. Trigrafı değiştirme etkinleştirme hakkında daha fazla bilgi için bkz: [/ZC: trigraphs (Trigrafları değiştirme)](../build/reference/zc-trigraphs-trigraphs-substitution.md).  
  
 Aşağıdaki tablo, dokuz trigraf dizisini göstermektedir. Noktalama karakterlerinin kaynak dosyasında ilk sütunda görünen tüm örneklerinin yerine karşılık gelen karakterler ikinci sütuna konur.  
  
### <a name="trigraph-sequences"></a>Trigraf Dizileri  
  
|Trigraf|Noktalama Karakteri|  
|--------------|---------------------------|  
|??=|#|  
|??(|[|  
|??/|\|  
|??)|]|  
|??'|^|  
|??\<|{|  
|??!|&#124;|  
|??>|}|  
|??-|~|  
  
 Bir trigraf her zaman tek kaynaklı karakter olarak işlem görür. Trigrafları çevrilmesi gerçekleşir ilk [çeviri aşaması](../preprocessor/phases-of-translation.md), önce kaçış karakterleri tanıma dize değişmez değerleri ve karakter sabitleri. Yalnızca yukarıdaki tabloda gösterilen dokuz trigraf tanınır. Diğer tüm karakter dizileri çevrilmeden bırakılır.  
  
 Karakteri kaçış sırası  **\\?**, trigrafı benzeri karakter sıralarının misinterpretation engeller. (Kaçış dizileri hakkında daha fazla bilgi için bkz: [kaçış sıraları](../c-language/escape-sequences.md).) Örneğin, `What??!` dizesini bu `printf` ifadesiyle yazdırmaya çalışırsanız  
  
```  
printf( "What??!\n" );  
```  
  
 Yazdırılan dizesi `What|` çünkü `??!` ile değiştirilir bir trigrafı sırası `|` karakter. Diziyi düzgün şekilde yazdırmak için ifadeyi aşağıdaki gibi yazın:  
  
```  
printf( "What?\?!\n" );  
```  
  
 Bu `printf` deyiminde, ikinci soru işaretinin önündeki bir ters eğik çizgi kaçış karakteri, `??!` öğesinin bir trigraf olarak yanlış yorumlanmasını önler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [/ ZC: trigraphs (trigrafları değiştirme)](../build/reference/zc-trigraphs-trigraphs-substitution.md)   
 [C tanımlayıcıları](../c-language/c-identifiers.md)