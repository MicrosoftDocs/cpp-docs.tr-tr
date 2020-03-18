---
title: value_compare sınıfı (&lt;eşleme&gt;)
ms.date: 11/04/2016
f1_keywords:
- std::value_compare
- std.value_compare
- map/std::value_compare
helpviewer_keywords:
- std::value_compare
ms.assetid: ea97c1d0-04b2-4d42-8d96-23522c04cc41
ms.openlocfilehash: 1f872edce6f0114be7c90a8108ba248fd793a989
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447574"
---
# <a name="value_compare-class-ltmapgt"></a>value_compare sınıfı (&lt;eşleme&gt;)

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

Bir harita tarafından içerilen tüm öğelerin `value_types` arasında `value_compare` tarafından verilen karşılaştırma ölçütü, yardımcı sınıf oluşturma işlemi tarafından ilgili öğelerin anahtarları arasındaki bir karşılaştırmadan alınmış olur. Üye işlevi işleci, iki öğenin sıralama anahtarı bileşenlerini karşılaştırmak için `value_compare` tarafından sunulan Function nesnesinde depolanan `key_compare` türündeki nesne `comp` kullanır.

Anahtar değerlerinin öğe değerleriyle aynı olduğu basit kapsayıcılar olan kümeler ve çoklu kümeler için, `value_compare` `key_compare`eşdeğerdir; Haritalar ve çoklu haritalar için, tür `pair` öğeleri öğe anahtarının değeriyle aynı olmadığından, bunlar değildir.

## <a name="example"></a>Örnek

`value_compare`bildirme ve kullanma hakkında bir örnek için bkz. [value_comp](../standard-library/map-class.md#value_comp) örneği.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<eşleme >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[Binary_function Struct](../standard-library/binary-function-struct.md)\
[Standart kitaplıkta Iş parçacığı güvenliği\ C++ ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)
