---
title: value_compare sınıfı (&lt;eşleme&gt;)
ms.date: 11/04/2016
f1_keywords:
- std::value_compare
- std.value_compare
- map/std::value_compare
- value_compare
helpviewer_keywords:
- std::value_compare
ms.assetid: ea97c1d0-04b2-4d42-8d96-23522c04cc41
ms.openlocfilehash: d098e947aec1ea543f29c168a632d1f4c9412e82
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448319"
---
# <a name="valuecompare-class-ltmapgt"></a>value_compare sınıfı (&lt;eşleme&gt;)

Haritadaki göreli sıralarını tespit etmek için anahtarlarının değerlerini karşılaştırarak bir haritanın öğelerini karşılaştırabilen bir işlev nesnesi sağlar.

## <a name="syntax"></a>Sözdizimi

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

Bir harita tarafından içerilen tüm `value_compare` öğelerin `value_types` arasına verilen karşılaştırma ölçütü, yardımcı sınıf oluşturma işlemi tarafından ilgili öğelerin anahtarları arasındaki bir karşılaştırmadan alınmış olur. Üye işlevi işleci, iki öğenin sıralama `comp` anahtarı bileşenlerini `key_compare` karşılaştırmak için tarafından `value_compare` belirtilen işlev nesnesinde depolanan tür nesnesini kullanır.

Anahtar değerlerinin öğe değerleriyle `value_compare` `key_compare`özdeş olduğu basit kapsayıcılar olan kümeler ve çoklu kümeler için, tür `pair` öğelerinin değeri ile aynı olmadığı için, ' nin eşit olduğu, eşlemeler ve çoklu haritalar için. öğe anahtarının değeri.

## <a name="example"></a>Örnek

Bildirme ve kullanma [](../standard-library/map-class.md#value_comp) `value_compare`hakkında bir örnek için bkz. value_comp.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<eşleme >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[binary_function yapısı](../standard-library/binary-function-struct.md)\
[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)
