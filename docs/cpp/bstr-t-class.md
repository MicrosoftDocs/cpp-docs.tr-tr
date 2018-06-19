---
title: _bstr_t sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t
dev_langs:
- C++
helpviewer_keywords:
- BSTR object
- _bstr_t class
- BSTR object [C++], COM encapsulation
ms.assetid: 58841fef-fe21-4a84-aab9-780262b5201f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8bea9f863df08342f17419a16b14579fa6a257b8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32415289"
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
|[Attach](../cpp/bstr-t-attach.md)|Bağlantıları bir `_bstr_t` sarmalayıcı bir `BSTR`.|  
|[Kopyalama](../cpp/bstr-t-copy.md)|Yalıtılmış bir kopyasını oluşturur `BSTR`.|  
|[Detach](../cpp/bstr-t-detach.md)|Döndürür `BSTR` tarafından Sarmalanan bir `_bstr_t` ve ayırır `BSTR` gelen `_bstr_t`.|  
|[GetAddress](../cpp/bstr-t-getaddress.md)|İşaret `BSTR` tarafından Sarmalanan bir `_bstr_t`.|  
|[GetBSTR](../cpp/bstr-t-getbstr.md)|Başlangıcına işaret `BSTR` tarafından Sarmalanan `_bstr_t`.|  
|[uzunluğu](../cpp/bstr-t-length.md)|Karakter sayısını verir `_bstr_t`.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[işleç =](../cpp/bstr-t-operator-equal.md)|Var olan yeni bir değer atar `_bstr_t` nesnesi.|  
|[+= işleci](../cpp/bstr-t-operator-add-equal-plus.md)|Karakter sonuna ekler `_bstr_t` nesnesi.|  
|[işleç +](../cpp/bstr-t-operator-add-equal-plus.md)|İki dizeyi art arda ekler.|  
|[işleç !](../cpp/bstr-t-operator-logical-not.md)|Denetler kapsüllenmiş `BSTR` olan bir **NULL** dize.|  
|[operator ==,! =, \<, >, \<=, > =](../cpp/bstr-t-relational-operators.md)|İki karşılaştırır `_bstr_t` nesneleri.|  
|[işleç wchar_t * &#124; char\*](../cpp/bstr-t-wchar-t-star-bstr-t-char-star.md)|Kapsüllenmiş Unicode ya da çok baytlı işaretçiler ayıklamak `BSTR` nesnesi.|  
  
**SON Microsoft özel**  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<comutil.h >  
  
 **LIB:** comsuppw.lib veya comsuppwd.lib (bkz [/ZC: wchar_t (wchar_t yerel tür olan)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) daha fazla bilgi için)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici COM Desteği Sınıfları](../cpp/compiler-com-support-classes.md)