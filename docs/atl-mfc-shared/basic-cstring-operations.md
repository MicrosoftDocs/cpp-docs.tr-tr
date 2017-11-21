---
title: Temel CString Operations | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords:
- CString objects, basic operations
- string literals, CString operations
- literal strings, CString operations
- CString objects
- string comparison, CString operations
- characters, accessing in CStrings
ms.assetid: 41db66b2-9427-4bb3-845a-9b6869159a6c
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 566f2d29da9ff8422b8a29178f63a553bfe33668
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="basic-cstring-operations"></a>Temel CString işlemleri
Bu konuda aşağıdaki temel açıklanmaktadır [CString](../atl-mfc-shared/reference/cstringt-class.md) işlemleri:  
  
- [CString nesneleri standart C değişmez değer dizeleri oluşturma](#_core_creating_cstring_objects_from_standard_c_literal_strings)  
  
- [Bir CString tek tek karakter erişme](#_core_accessing_individual_characters_in_a_cstring)  
  
- [Birleştirme iki CString nesneleri](#_core_concatenating_two_cstring_objects)  
  
- [CString nesneleri karşılaştırma](#_core_comparing_cstring_objects)  
  
- [CString nesneleri dönüştürme](#_core_converting_cstring_objects)  
  
 `Class CString`sınıf şablonunu temel alarak [CStringT sınıfı](../atl-mfc-shared/reference/cstringt-class.md). `CString`olan bir `typedef` , `CStringT`. Daha kesin olarak `CString` olan bir `typedef` , bir *açık uzmanlık* , `CStringT`, bir sınıf tanımlamak için bir sınıf şablonu kullanmak için yaygın bir yolu değil. Benzer şekilde tanımlanan sınıflar `CStringA` ve `CStringW`.  
  
 `CString`, `CStringA`, ve `CStringW` atlstr.h tanımlanır. `CStringT`cstringt.h içinde tanımlanmıştır.  
  
 `CString`, `CStringA`, ve `CStringW` bir dizi yöntem ve işleçler tarafından tanımlanan her alma `CStringT` destekledikleri dize verilerini ile kullanım için. Yinelenen ve bazı durumlarda, yöntemlerin bazıları C çalışma zamanı kitaplıkları dize hizmetlerini aşan.  
  
 Not: `CString` yerel bir sınıftır. C + kullanmak için bir dize sınıfı için +/ CLI yönetilen proje, kullanım `System.String`.  
  
##  <a name="_core_creating_cstring_objects_from_standard_c_literal_strings"></a>CString nesneleri standart C değişmez değer dizeleri oluşturma  
 C türü değişmez değer dizeleri atayabilirsiniz bir `CString` atayabilirsiniz gibi `CString` başka bir nesne.  
  
-   Bir C değişmez değer dize değerini atayın bir `CString` nesnesi.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#183](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_1.cpp)]  
  
-   Bir değer atamak `CString` başka bir `CString` nesnesi.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#184](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_2.cpp)]  
  
     İçeriği bir `CString` bir nesne kopyalanır `CString` nesne diğerine atanır. Bu nedenle, iki dizeyi dizesi hale karakterlerini başvuru paylaşmayın. Nasıl kullanılacağı hakkında daha fazla bilgi için `CString` nesneleri değerleri olarak bkz [CString semantiği](../atl-mfc-shared/cstring-semantics.md).  
  
    > [!NOTE]
    >  ANSI veya Unicode için derlenebilir böylece uygulamanız yazmak için değişmez değer dizeleri _T makrosu kullanarak kodlayın. Daha fazla bilgi için bkz: [Unicode ve çok baytlı karakter kümesi (MBCS) desteği](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md).  
  
##  <a name="_core_accessing_individual_characters_in_a_cstring"></a>Bir CString tek tek karakter erişme  
 Tek tek karakter erişebileceği bir `CString` kullanarak nesne `GetAt` ve `SetAt` yöntemleri. Dizi öğesi veya alt simge, işleci ([]) yerine kullanabilirsiniz `GetAt` tek tek karakterleri almak için. (Bu erişilirken dizi öğeleri standart C stilinde dizeleri olduğu dizine göre benzer.) Dizin için değerleri `CString` karakterlerdir sıfır tabanlı.  
  
##  <a name="_core_concatenating_two_cstring_objects"></a>Birleştirme iki CString nesneleri  
 İki birleştirmek için `CString` nesneleri, birleştirme işleçleri kullanın (+ veya +=) gibi.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#185](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_3.cpp)]  
  
 Birleştirme işleçleri için en az bir değişken (+ veya +=) olmalıdır bir `CString` nesnesi, ancak bir sabit karakter dizesi kullanabilirsiniz (örneğin, `"big"`) veya bir `char` (örneğin, ' x') diğer bağımsız değişkeni.  
  
##  <a name="_core_comparing_cstring_objects"></a>CString nesneleri karşılaştırma  
 `Compare` Yöntemi ve == işleci için `CString` eşdeğerdir. `Compare`, `operator==`, ve `CompareNoCase` MBCS ve Unicode farkında; olduğundan `CompareNoCase` ayrıca büyük küçük harfe duyarlıdır. `Collate` Yöntemi `CString` yerel ayara duyarlı ve genellikle daha yavaş `Compare`. Kullanım `Collate` yalnızca burada, sıralayarak uymanız gerekir kuralları belirtildiği şekilde geçerli bölgeye göre.  
  
 Aşağıdaki tabloda kullanılabilir gösterilmektedir [CString](../atl-mfc-shared/reference/cstringt-class.md) karşılaştırma işlevleri ve eşdeğer MBCS/Unicode-taşınabilir işlevlerini C Çalışma Zamanı Kitaplığı'nda.  
  
|CString işlevi|MBCS işlevi|Unicode işlevi|  
|----------------------|-------------------|----------------------|  
|`Compare`|`_mbscmp`|`wcscmp`|  
|`CompareNoCase`|`_mbsicmp`|`_wcsicmp`|  
|`Collate`|`_mbscoll`|`wcscoll`|  
  
 `CStringT` Sınıfı şablonu tanımlar ilişkisel işleçleri (<, \<=, > =, >, ==, ve! =), tarafından kullanım için kullanılabilir olan `CString`. İki karşılaştırabilirsiniz `CStrings` aşağıdaki örnekte gösterildiği gibi bu işleçleri kullanarak.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#186](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_4.cpp)]  
  
##  <a name="_core_converting_cstring_objects"></a>CString nesneleri dönüştürme  
 CString nesneleri için diğer dize türlerini dönüştürme hakkında daha fazla bilgi için bkz: [nasıl yapılır: Dönüştür arasında çeşitli dize türleri](../text/how-to-convert-between-various-string-types.md).  
  
## <a name="using-cstring-with-wcout"></a>CString wcout ile kullanma  
 CString ile kullanmak için `wcout` nesnesine açıkça atamalısınız bir `const wchar_t*` aşağıdaki örnekte gösterildiği gibi:  
  
```  
CString cs("meow");

    wcout <<(const wchar_t*) cs <<endl;  
 
```  
  
 Cast olmadan `cs` olarak işlem görür bir `void*` ve `wcout` nesnenin adresi yazdırır. Bu davranış C++ standart ile doğru kendileri şablon bağımsız değişken kesintisi ve aşırı çözümlemesi uyumluluğunu arasındaki Zarif etkileşimler kaynaklanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dizeler (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)   
 [CStringT sınıfı](../atl-mfc-shared/reference/cstringt-class.md)   
 [Şablonu özelleştirme](../cpp/template-specialization-cpp.md)   
 [Nasıl yapılır: çeşitli dize türleri arasında dönüştürme](../text/how-to-convert-between-various-string-types.md)

