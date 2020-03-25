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
ms.openlocfilehash: 3ef89c6f6742d528c427c49fd2a62d8820625e79
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190384"
---
# <a name="_bstr_t-class"></a>_bstr_t Sınıfı

**Microsoft 'a özgü**

`_bstr_t` nesne [BSTR veri türünü](/previous-versions/windows/desktop/automat/bstr)kapsüller. Sınıfı, uygun olduğunda `SysAllocString` ve `SysFreeString` ve diğer `BSTR` API 'Leri için işlev çağrıları aracılığıyla kaynak ayırmayı ve ayırmayı yönetir. **_Bstr_t** sınıfı aşırı yükten kaçınmak için başvuru sayımı kullanır.

### <a name="construction"></a>İnşaat

|||
|-|-|
|[_bstr_t](../cpp/bstr-t-bstr-t.md)|`_bstr_t` nesnesi oluşturur.|

### <a name="operations"></a>İşlemler

|||
|-|-|
|[Assign](../cpp/bstr-t-assign.md)|Bir `BSTR`, `_bstr_t`kaydırılan `BSTR` kopyalar.|
|[Attach](../cpp/bstr-t-attach.md)|`_bstr_t` sarmalayıcısı bir `BSTR`bağlar.|
|[kopya](../cpp/bstr-t-copy.md)|Encapsulated `BSTR`bir kopyasını oluşturur.|
|[Detach](../cpp/bstr-t-detach.md)|Bir `_bstr_t` kaydırılan `BSTR` döndürür ve `BSTR` `_bstr_t`ayırır.|
|[GetAddress](../cpp/bstr-t-getaddress.md)|Bir `_bstr_t`kaydırılan `BSTR` işaret eder.|
|[GetBSTR](../cpp/bstr-t-getbstr.md)|`_bstr_t`kaydırılan `BSTR` başlangıcını işaret eder.|
|[uzunluklu](../cpp/bstr-t-length.md)|`_bstr_t`karakter sayısını döndürür.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işleç =](../cpp/bstr-t-operator-equal.md)|Varolan bir `_bstr_t` nesnesine yeni bir değer atar.|
|[işleç + =](../cpp/bstr-t-operator-add-equal-plus.md)|`_bstr_t` nesnesinin sonuna karakter ekler.|
|[işleç +](../cpp/bstr-t-operator-add-equal-plus.md)|İki dizeyi birleştirir.|
|[işleç !](../cpp/bstr-t-operator-logical-not.md)|Encapsulated `BSTR` boş bir dize olup olmadığını denetler.|
|[operator = =,! =, \<, >, \<=, > =](../cpp/bstr-t-relational-operators.md)|İki `_bstr_t` nesnesini karşılaştırır.|
|[işleç wchar_t * &#124; char\*](../cpp/bstr-t-wchar-t-star-bstr-t-char-star.md)|Encapsulated Unicode veya çok baytlı `BSTR` nesnesine işaretçileri ayıklayın.|

**SON Microsoft 'a özgü**

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<comutil. h >

**Lib:** comsuppw. lib veya comsuppwd. lib (daha fazla bilgi için bkz. [/zc: wchar_t (wchar_t yerel tür)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) )

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici COM Desteği Sınıfları](../cpp/compiler-com-support-classes.md)
