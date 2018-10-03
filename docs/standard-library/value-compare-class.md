---
title: value_compare sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- value_compare
dev_langs:
- C++
helpviewer_keywords:
- value_compare class
ms.assetid: c306c5b9-3505-4357-aa6b-216451b951ed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7a3be65e867c243bd6a32dd35dd3128872a1f8d1
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48234118"
---
# <a name="valuecompare-class"></a>value_compare Sınıfı

Hash_map kendi göreli sıralarını belirlemek için kendi anahtarını değerlerini karşılaştırarak bir hash_map öğelerini karşılaştıran bir işlev nesnesi sağlar.

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

Value_compare arasında tarafından sağlanan karşılaştırma ölçütleri `value_types` tarafından bir hash_map yer alan tüm öğelerin yardımcı sınıf oluşturma ile ilgili öğelerin anahtarlarını arasında bir karşılaştırma alanından kaynaklanan. Üye işlevi işleci nesnenin kullandığı `comp` türü `key_compare` iki öğeyi sıralama anahtarı bileşenlerinin Karşılaştırılacak value_compare tarafından sağlanan işlev nesnesi depolanır.

Value_compare hash_sets ve basit kapsayıcılar anahtar değerlerinin olduğu öğe değerlerin aynı olan hash_multisets değerine eşdeğer olan `key_compare`; hash_maps ve bunlar değildir, çünkü hash_multimaps türünün değerini `pair` öğeleri değeri öğenin anahtarı olarak aynı değil.

## <a name="example"></a>Örnek

Örneğin bakın [hash_map::value_comp](../standard-library/hash-map-class.md#value_comp) bildirme ve kullanma value_compare ilişkin bir örnek için.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<hash_map >

**Namespace:** stdext

## <a name="see-also"></a>Ayrıca bkz.

[binary_function Yapısı](../standard-library/binary-function-struct.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
