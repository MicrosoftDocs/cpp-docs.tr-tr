---
title: "_bstr_t sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _bstr_t
dev_langs: C++
helpviewer_keywords:
- BSTR object
- _bstr_t class
- BSTR object [C++], COM encapsulation
ms.assetid: 58841fef-fe21-4a84-aab9-780262b5201f
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0af38fe5e88540bf7e8947808c49c5283d742a4a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="bstrt-class"></a>_bstr_t Sınıfı
**Microsoft özel**  
  
 A `_bstr_t` nesne yalıtır [BSTR veri türü](http://msdn.microsoft.com/en-us/1b2d7d2c-47af-4389-a6b6-b01b7e915228). Kaynak ayırma ve ayırmayı kaldırma işlev çağrılarını aracılığıyla sınıfı yönetir **SysAllocString** ve **SysFreeString** ve diğer `BSTR` API'leri uygun olduğunda. `_bstr_t` Sınıfı başvuru aşırı yükünü önlemek için sayım kullanır.  
  
### <a name="construction"></a>Yapı  
  
|||  
|-|-|  
|[_bstr_t](../cpp/bstr-t-bstr-t.md)|Oluşturan bir `_bstr_t` nesnesi.|  
  
### <a name="operations"></a>İşlemler  
  
|||  
|-|-|  
|[Ata](../cpp/bstr-t-assign.md)|Kopya bir `BSTR` içine `BSTR` tarafından Sarmalanan bir `_bstr_t`.|  
|[Ekleme](../cpp/bstr-t-attach.md)|Bağlantıları bir `_bstr_t` sarmalayıcı bir `BSTR`.|  
|[kopyalama](../cpp/bstr-t-copy.md)|Yalıtılmış bir kopyasını oluşturur `BSTR`.|  
|[Ayırma](../cpp/bstr-t-detach.md)|Döndürür `BSTR` tarafından Sarmalanan bir `_bstr_t` ve ayırır `BSTR` gelen `_bstr_t`.|  
|[GetAddress](../cpp/bstr-t-getaddress.md)|İşaret `BSTR` tarafından Sarmalanan bir `_bstr_t`.|  
|[GetBSTR](../cpp/bstr-t-getbstr.md)|Başlangıcına işaret `BSTR` tarafından Sarmalanan `_bstr_t`.|  
|[uzunluğu](../cpp/bstr-t-length.md)|Karakter sayısını verir `_bstr_t`.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[işleç =](../cpp/bstr-t-operator-equal.md)|Var olan yeni bir değer atar `_bstr_t` nesnesi.|  
|[+= işleci](../cpp/bstr-t-operator-add-equal-plus.md)|Karakter sonuna ekler `_bstr_t` nesnesi.|  
|[operator +](../cpp/bstr-t-operator-add-equal-plus.md)|İki dizeyi art arda ekler.|  
|[işleci!](../cpp/bstr-t-operator-logical-not.md)|Denetler kapsüllenmiş `BSTR` olan bir **NULL** dize.|  
|[operator ==,! =, \<, >, \<=, > =](../cpp/bstr-t-relational-operators.md)|İki karşılaştırır `_bstr_t` nesneleri.|  
|[işleç wchar_t * &#124; char\*](../cpp/bstr-t-wchar-t-star-bstr-t-char-star.md)|Kapsüllenmiş Unicode ya da çok baytlı işaretçiler ayıklamak `BSTR` nesnesi.|  
  
**SON Microsoft özel**  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** comutil.h  
  
 **LIB:** comsuppw.lib veya comsuppwd.lib (bkz [/ZC: wchar_t (wchar_t yerel tür olan)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) daha fazla bilgi için)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici COM desteği sınıfları](../cpp/compiler-com-support-classes.md)