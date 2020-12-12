---
description: 'Hakkında daha fazla bilgi edinin: value_compare sınıfı ( &lt; eşleme &gt; )'
title: value_compare sınıfı ( &lt; eşleme &gt; )
ms.date: 11/04/2016
f1_keywords:
- std::value_compare
- std.value_compare
- map/std::value_compare
helpviewer_keywords:
- std::value_compare
ms.assetid: ea97c1d0-04b2-4d42-8d96-23522c04cc41
ms.openlocfilehash: c5b7ba865606e0bc5a5c8238de72824f9061c1b5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97312819"
---
# <a name="value_compare-class-ltmapgt"></a>value_compare sınıfı ( &lt; eşleme &gt; )

Haritadaki göreli sıralarını tespit etmek için anahtarlarının değerlerini karşılaştırarak bir haritanın öğelerini karşılaştırabilen bir işlev nesnesi sağlar.

## <a name="syntax"></a>Syntax

```cpp
class value_compare : public binary_function<value_type, value_type, bool>
{
public:
    bool operator()(const value_type& left, const value_type& right) const;
    value_compare(key_compare pred) : comp(pred);
protected:
    key_compare comp;
};
```

## <a name="remarks"></a>Açıklamalar

`value_compare` `value_types` Bir harita tarafından içerilen tüm öğelerin arasına verilen karşılaştırma ölçütü, yardımcı sınıf oluşturma işlemi tarafından ilgili öğelerin anahtarları arasındaki bir karşılaştırmadan alınmış olur. Üye işlevi işleci, `comp` `key_compare` `value_compare` iki öğenin sıralama anahtarı bileşenlerini karşılaştırmak için tarafından belirtilen işlev nesnesinde depolanan tür nesnesini kullanır.

Anahtar değerlerinin öğe değerleriyle özdeş olduğu basit kapsayıcılar olan kümeler ve çoklu kümeler için, `value_compare` `key_compare` tür `pair` öğelerinin değeri öğe anahtarının değeri ile aynı olmadığından, bunlar için değildir; bu değerler, eşleme ve çoklu haritalar için.

## <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir örnek için bkz. [value_comp](../standard-library/map-class.md#value_comp) örneği `value_compare` .

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<map>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[binary_function yapısı](../standard-library/binary-function-struct.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)
