---
description: 'Hakkında daha fazla bilgi edinin: value_compare sınıfı'
title: value_compare Sınıfı
ms.date: 11/04/2016
f1_keywords:
- hash_map/std::value_compare
helpviewer_keywords:
- value_compare class
ms.assetid: c306c5b9-3505-4357-aa6b-216451b951ed
ms.openlocfilehash: d77412b2d979ef4db84621df1b0c94191f3d2a5f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97211719"
---
# <a name="value_compare-class"></a>value_compare Sınıfı

Hash_map öğelerini, hash_map göreli sıralarını belirleyerek kendi anahtar değerlerini karşılaştırarak karşılaştırabilen bir işlev nesnesi sağlar.

## <a name="syntax"></a>Syntax

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

Bir hash_map içindeki tüm öğeler arasında value_compare tarafından verilen karşılaştırma ölçütleri, `value_types` yardımcı sınıf oluşturma tarafından ilgili öğelerin anahtarları arasındaki bir karşılaştırmadan elde edilir. Üye işlevi işleci, `comp` `key_compare` iki öğenin sıralama anahtarı bileşenlerini karşılaştırmak için value_compare tarafından belirtilen işlev nesnesinde depolanan nesne türünü kullanır.

Hash_sets ve hash_multisets için, anahtar değerlerinin öğe değerleriyle özdeş olduğu basit kapsayıcılar olan value_compare eşdeğerdir `key_compare` ; hash_maps ve hash_multimaps, çünkü Type `pair` öğelerinin değeri öğe anahtarının değeriyle aynı değil.

## <a name="example"></a>Örnek

Value_compare bildirme ve kullanma hakkında bir örnek için [hash_map:: value_comp](../standard-library/hash-map-class.md#value_comp) örneğe bakın.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<hash_map>

**Ad alanı:** stdext

## <a name="see-also"></a>Ayrıca bkz.

[binary_function yapısı](../standard-library/binary-function-struct.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)
