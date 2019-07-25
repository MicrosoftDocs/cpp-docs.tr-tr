---
title: value_compare Sınıfı
ms.date: 11/04/2016
f1_keywords:
- value_compare
helpviewer_keywords:
- value_compare class
ms.assetid: c306c5b9-3505-4357-aa6b-216451b951ed
ms.openlocfilehash: 0e057a6229c903402a51b34a8f4e844e80ace187
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68452369"
---
# <a name="valuecompare-class"></a>value_compare Sınıfı

, Hash_map içindeki göreli sıralarını belirleyebilmek için anahtarlarının değerlerini karşılaştırarak bir hash_map öğelerini karşılaştırabilen bir işlev nesnesi sağlar.

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

Bir hash_map tarafından içerilen tüm öğeler arasında `value_types` value_compare tarafından verilen karşılaştırma ölçütleri, yardımcı sınıf oluşturma tarafından ilgili öğelerin anahtarları arasındaki bir karşılaştırmadan elde edilir. Üye işlevi işleci, iki öğenin sıralama `comp` anahtarı bileşenlerini `key_compare` karşılaştırmak için value_compare tarafından sunulan Function nesnesinde depolanan nesne türünü kullanır.

Anahtar değerlerinin öğe değerleriyle özdeş olduğu basit kapsayıcılar olan hash_sets ve hash_multisets için, value_compare eşdeğerdir `key_compare`; hash_maps ve hash_multimaps için, türün değeri `pair` öğeler, öğe anahtarının değeriyle aynı değil.

## <a name="example"></a>Örnek

[Hash_map:: value_comp](../standard-library/hash-map-class.md#value_comp) için bkz. value_compare nasıl bildirilemeyeceğini ve kullanacağınızı gösteren bir örnek.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<hash_map >

**Ad alanı:** stdext

## <a name="see-also"></a>Ayrıca bkz.

[binary_function yapısı](../standard-library/binary-function-struct.md)\
[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)
