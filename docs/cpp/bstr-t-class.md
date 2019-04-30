---
title: _bstr_t Sınıfı
ms.date: 11/04/2016
f1_keywords:
- _bstr_t
helpviewer_keywords:
- BSTR object
- _bstr_t class
- BSTR object [C++], COM encapsulation
ms.assetid: 58841fef-fe21-4a84-aab9-780262b5201f
ms.openlocfilehash: f394a48c0326058be705d14fb0413e23e8052ae2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386167"
---
# <a name="bstrt-class"></a>_bstr_t Sınıfı

**Microsoft'a özgü**

A `_bstr_t` kapsülleyen nesne [BSTR veri türü](/previous-versions/windows/desktop/automat/bstr). Sınıf kaynak ayırmayı ve ayırmayı kaldırma işlev çağrılarıyla yönetir `SysAllocString` ve `SysFreeString` ve diğer `BSTR` API'leri uygun olduğunda. **_Bstr_t** sınıfı aşırı ek yükten kaçınmak için başvuru sayımını kullanır.

### <a name="construction"></a>Oluşturma

|||
|-|-|
|[_bstr_t](../cpp/bstr-t-bstr-t.md)|Oluşturur bir `_bstr_t` nesne.|

### <a name="operations"></a>İşlemler

|||
|-|-|
|[Assign](../cpp/bstr-t-assign.md)|Kopya bir `BSTR` içine `BSTR` tarafından Sarmalanan bir `_bstr_t`.|
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

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici COM Desteği Sınıfları](../cpp/compiler-com-support-classes.md)