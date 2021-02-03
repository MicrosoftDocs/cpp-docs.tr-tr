---
title: _bstr_t sınıfı
description: 'Hakkında daha fazla bilgi edinin: _bstr_t sınıfı'
ms.date: 02/02/2021
f1_keywords:
- _bstr_t
helpviewer_keywords:
- BSTR object
- _bstr_t class
- BSTR object [C++], COM encapsulation
ms.openlocfilehash: 71f5f0a27989b416cf4f13873254890db09ce334
ms.sourcegitcommit: c20734f18d3d49bb38b1628c68b53b54b3eeeb03
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2021
ms.locfileid: "99522878"
---
# <a name="_bstr_t-class"></a>`_bstr_t` sınıfı

**Microsoft'a Özgü**

Bir `_bstr_t` nesne [BSTR veri türünü](/previous-versions/windows/desktop/automat/bstr)kapsüller. Sınıfı, [`SysAllocString`](/windows/win32/api/oleauto/nf-oleauto-sysallocstring) [`SysFreeString`](/windows/win32/api/oleauto/nf-oleauto-sysfreestring) uygun olduğunda, ve diğer API 'ler için işlev çağrıları aracılığıyla kaynak ayırmayı ve ayırmayı yönetir `BSTR` . `_bstr_t`Sınıf aşırı yükten kaçınmak için başvuru sayımını kullanır.

## <a name="members"></a>Üyeler

### <a name="construction"></a>İnşaat

| Oluşturucu | Description |
|--|--|
| [`_bstr_t`](../cpp/bstr-t-bstr-t.md) | Bir `_bstr_t` nesnesi oluşturur. |

### <a name="operations"></a>Operations

| İşlev | Açıklama |
|--|--|
| [`Assign`](../cpp/bstr-t-assign.md) | Bir `BSTR` `BSTR` ile sarmalanmış içine kopyalar `_bstr_t` . |
| [`Attach`](../cpp/bstr-t-attach.md) | Bir `_bstr_t` sarmalayıcısı öğesine bağlar `BSTR` . |
| [`copy`](../cpp/bstr-t-copy.md) | Encapsulated öğesinin bir kopyasını oluşturur `BSTR` . |
| [`Detach`](../cpp/bstr-t-detach.md) | `BSTR`Tarafından Sarmalanan bir döndürür `_bstr_t` ve öğesinden ayırır `BSTR` `_bstr_t` . |
| [`GetAddress`](../cpp/bstr-t-getaddress.md) | `BSTR`Tarafından Sarmalanan öğesine işaret eder `_bstr_t` . |
| [`GetBSTR`](../cpp/bstr-t-getbstr.md) | Tarafından Sarmalanan başlangıcını işaret eder `BSTR` `_bstr_t` . |
| [`length`](../cpp/bstr-t-length.md) | İçindeki karakter sayısını döndürür `_bstr_t` . |

### <a name="operators"></a>İşleçler

| İşleç | Açıklama |
|--|--|
| [`operator =`](../cpp/bstr-t-operator-equal.md) | Varolan bir nesneye yeni bir değer atar `_bstr_t` . |
| [`operator +=`](../cpp/bstr-t-operator-add-equal-plus.md) | Nesnenin sonuna karakter ekler `_bstr_t` . |
| [`operator +`](../cpp/bstr-t-operator-add-equal-plus.md) | İki dizeyi birleştirir. |
| [`operator !`](../cpp/bstr-t-operator-logical-not.md) | Encapsulated `BSTR` 'ın null bir dize olup olmadığını denetler. |
| [`operator ==`](../cpp/bstr-t-relational-operators.md)<br/>[`operator !=`](../cpp/bstr-t-relational-operators.md)<br/>[`operator <`](../cpp/bstr-t-relational-operators.md)<br/>[`operator >`](../cpp/bstr-t-relational-operators.md)<br/>[`operator <=`](../cpp/bstr-t-relational-operators.md)<br/>[`operator >=`](../cpp/bstr-t-relational-operators.md) | İki `_bstr_t` nesneyi karşılaştırır. |
| [`operator wchar_t*`](../cpp/bstr-t-wchar-t-star-bstr-t-char-star.md)<br/>[`operator char*`](../cpp/bstr-t-wchar-t-star-bstr-t-char-star.md)  | Kapsüllenmiş Unicode veya çok baytlı nesnesine işaretçileri ayıklayın `BSTR` . |

**SON Microsoft 'a özgü**

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<comutil.h>

**LIB:** *`comsuppw.lib`* veya *`comsuppwd.lib`* daha fazla bilgi için bkz. [ `/Zc:wchar_t` (wchar_t yerel tür)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md))

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici COM desteği sınıfları](../cpp/compiler-com-support-classes.md)
