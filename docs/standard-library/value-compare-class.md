---
title: value_compare Sınıfı
ms.date: 11/04/2016
f1_keywords:
- hash_map/std::value_compare
helpviewer_keywords:
- value_compare class
ms.assetid: c306c5b9-3505-4357-aa6b-216451b951ed
ms.openlocfilehash: d64d51869ca8db1ed42e9d33691f59da4473d8d0
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447571"
---
# <a name="value_compare-class"></a>value_compare Sınıfı

Hash_map öğelerini, hash_map göreli sıralarını belirleyerek kendi anahtar değerlerini karşılaştırarak karşılaştırabilen bir işlev nesnesi sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
class value_compare
    : std::public binary_function<value_type, value_type, bool>
{
public:
    bool operator()(
        const value_type& left,
        const value_type& right) const
    {
        return (comp(left.first, right.first));
    }

protected:
    value_compare(const key_compare& c) : comp (c) { }
    key_compare comp;
};
```

## <a name="remarks"></a>Açıklamalar

Bir hash_map içeren tüm öğelerin `value_types` arasında value_compare tarafından verilen karşılaştırma ölçütleri, yardımcı sınıf oluşturma tarafından ilgili öğelerin anahtarları arasındaki bir karşılaştırmadan elde edilir. Üye işlevi işleci, iki öğenin sıralama anahtarı bileşenlerini karşılaştırmak için value_compare tarafından sunulan Function nesnesinde depolanan `key_compare` türündeki nesne `comp` kullanır.

Hash_sets ve hash_multisets için, anahtar değerlerinin öğe değerleriyle özdeş olduğu basit kapsayıcılar olan value_compare `key_compare`eşdeğerdir; hash_maps için hash_multimaps ve bu tür `pair` öğelerin değeri öğe anahtarının değeriyle aynı olmadığından, bunlar değildir.

## <a name="example"></a>Örnek

Value_compare bildirme ve kullanma hakkında bir örnek için [hash_map:: value_comp](../standard-library/hash-map-class.md#value_comp) örneğe bakın.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<hash_map >

**Ad alanı:** stdext

## <a name="see-also"></a>Ayrıca bkz.

[Binary_function Struct](../standard-library/binary-function-struct.md)\
[Standart kitaplıkta Iş parçacığı güvenliği\ C++ ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)
