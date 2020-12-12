---
description: 'Hakkında daha fazla bilgi edinin: _bstr_t sınıfı'
title: _bstr_t Sınıfı
ms.date: 11/04/2016
f1_keywords:
- _bstr_t
helpviewer_keywords:
- BSTR object
- _bstr_t class
- BSTR object [C++], COM encapsulation
ms.assetid: 58841fef-fe21-4a84-aab9-780262b5201f
ms.openlocfilehash: 562b8eb871ddcd63e7df70c84e61e80a5bf934b5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229411"
---
# <a name="_bstr_t-class"></a>_bstr_t Sınıfı

**Microsoft'a Özgü**

Bir `_bstr_t` nesne [BSTR veri türünü](/previous-versions/windows/desktop/automat/bstr)kapsüller. Sınıfı, `SysAllocString` `SysFreeString` uygun olduğunda, ve diğer API 'ler için işlev çağrıları aracılığıyla kaynak ayırmayı ve ayırmayı yönetir `BSTR` . **_Bstr_t** sınıfı aşırı yükten kaçınmak için başvuru sayımı kullanır.

### <a name="construction"></a>İnşaat

| Oluşturucu | Açıklama |
|--|--|
| [_bstr_t](../cpp/bstr-t-bstr-t.md) | Bir `_bstr_t` nesnesi oluşturur. |

### <a name="operations"></a>İşlemler

| İşlev | Açıklama |
|--|--|
| [Ata](../cpp/bstr-t-assign.md) | Bir `BSTR` `BSTR` ile sarmalanmış içine kopyalar `_bstr_t` . |
| [İliştir](../cpp/bstr-t-attach.md) | Bir `_bstr_t` sarmalayıcısı öğesine bağlar `BSTR` . |
| [kopya](../cpp/bstr-t-copy.md) | Encapsulated öğesinin bir kopyasını oluşturur `BSTR` . |
| [Ayır](../cpp/bstr-t-detach.md) | `BSTR`Tarafından Sarmalanan bir döndürür `_bstr_t` ve öğesinden ayırır `BSTR` `_bstr_t` . |
| [GetAddress](../cpp/bstr-t-getaddress.md) | `BSTR`Tarafından Sarmalanan öğesine işaret eder `_bstr_t` . |
| [GetBSTR](../cpp/bstr-t-getbstr.md) | Tarafından Sarmalanan başlangıcını işaret eder `BSTR` `_bstr_t` . |
| [length](../cpp/bstr-t-length.md) | İçindeki karakter sayısını döndürür `_bstr_t` . |

### <a name="operators"></a>İşleçler

| İşleç | Açıklama |
|--|--|
| [işleç =](../cpp/bstr-t-operator-equal.md) | Varolan bir nesneye yeni bir değer atar `_bstr_t` . |
| [işleç + =](../cpp/bstr-t-operator-add-equal-plus.md) | Nesnenin sonuna karakter ekler `_bstr_t` . |
| [işleç +](../cpp/bstr-t-operator-add-equal-plus.md) | İki dizeyi birleştirir. |
| [işlecinde!](../cpp/bstr-t-operator-logical-not.md) | Encapsulated `BSTR` 'ın null bir dize olup olmadığını denetler. |
| [işleç = =,! =, \<, > , \<=, >=](../cpp/bstr-t-relational-operators.md) | İki `_bstr_t` nesneyi karşılaştırır. |
| [işleç wchar_t * &#124; karakteri\*](../cpp/bstr-t-wchar-t-star-bstr-t-char-star.md) | Kapsüllenmiş Unicode veya çok baytlı nesnesine işaretçileri ayıklayın `BSTR` . |

**SON Microsoft 'a özgü**

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<comutil.h>

**Lib:** comsuppw. lib veya comsuppwd. lib (daha fazla bilgi için bkz. [/zc: wchar_t (wchar_t yerel tür)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) )

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici COM desteği sınıfları](../cpp/compiler-com-support-classes.md)
