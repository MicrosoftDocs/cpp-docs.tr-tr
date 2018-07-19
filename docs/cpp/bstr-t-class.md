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
ms.openlocfilehash: 15ed9c32a204bdef726a5ace88d811d2eeeb2c53
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/13/2018
ms.locfileid: "39027254"
---
# <a name="bstrt-class"></a>_bstr_t Sınıfı
**Microsoft'a özgü**  
  
 A `_bstr_t` kapsülleyen nesne [BSTR veri türü](http://msdn.microsoft.com/1b2d7d2c-47af-4389-a6b6-b01b7e915228). Sınıf kaynak ayırmayı ve ayırmayı kaldırma işlev çağrılarıyla yönetir `SysAllocString` ve `SysFreeString` ve diğer `BSTR` API'leri uygun olduğunda. `_bstr_t` Sınıfı aşırı ek yükten kaçınmak için başvuru sayımını kullanır.  
  
### <a name="construction"></a>Oluşturma  
  
|||  
|-|-|  
|[_bstr_t](../cpp/bstr-t-bstr-t.md)|Oluşturur bir `_bstr_t` nesne.|  
  
### <a name="operations"></a>İşlemler  
  
|||  
|-|-|  
|[Ata](../cpp/bstr-t-assign.md)|Kopya bir `BSTR` içine `BSTR` tarafından Sarmalanan bir `_bstr_t`.|  
|[Attach](../cpp/bstr-t-attach.md)|Bağlantılar bir `_bstr_t` sarmalayıcısını bir `BSTR`.|  
|[kopyalama](../cpp/bstr-t-copy.md)|Kapsüllenmiş bir kopyasını oluşturur `BSTR`.|  
|[Detach](../cpp/bstr-t-detach.md)|Döndürür `BSTR` tarafından Sarmalanan bir `_bstr_t` ve ayırır `BSTR` gelen `_bstr_t`.|  
|[GetAddress](../cpp/bstr-t-getaddress.md)|İşaret `BSTR` tarafından Sarmalanan bir `_bstr_t`.|  
|[GetBSTR](../cpp/bstr-t-getbstr.md)|Başlangıcına işaret `BSTR` tarafından Sarmalanan `_bstr_t`.|  
|[Uzunluğu](../cpp/bstr-t-length.md)|Karakter sayısını döndürür `_bstr_t`.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[işleç =](../cpp/bstr-t-operator-equal.md)|Mevcut bir yeni bir değer atar `_bstr_t` nesne.|  
|[+= işleci](../cpp/bstr-t-operator-add-equal-plus.md)|Sonuna karakterler ekler `_bstr_t` nesne.|  
|[işleç +](../cpp/bstr-t-operator-add-equal-plus.md)|İki dizeyi art arda ekler.|  
|[işleç !](../cpp/bstr-t-operator-logical-not.md)|Denetler kapsüllenmiş `BSTR` boş bir dizi.|  
|[işleç ==,! =, \<, >, \<=, > =](../cpp/bstr-t-relational-operators.md)|İki karşılaştırır `_bstr_t` nesneleri.|  
|[işleç wchar_t * &#124; char\*](../cpp/bstr-t-wchar-t-star-bstr-t-char-star.md)|İşaretçileri kapsüllenmiş Unicode veya çok baytlı ayıklamak `BSTR` nesne.|  
  
**END Microsoft özgü**  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<comutil.h >  
  
 **Lib:** comsuppw.lib veya comsuppwd.lib (bkz [/ZC: wchar_t (wchar_t yerel türü olduğu)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) daha fazla bilgi için)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici COM Desteği Sınıfları](../cpp/compiler-com-support-classes.md)