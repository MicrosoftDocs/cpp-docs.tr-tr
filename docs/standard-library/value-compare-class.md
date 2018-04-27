---
title: value_compare sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- value_compare
dev_langs:
- C++
helpviewer_keywords:
- value_compare class
ms.assetid: c306c5b9-3505-4357-aa6b-216451b951ed
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9019b39ff9df7137a1de6723a6fbb64e595ce678
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="valuecompare-class"></a>value_compare Sınıfı

Hash_map içindeki göreli sıralarına belirlemek için kendi anahtarları değerlerinin karşılaştırılmasıyla bir hash_map öğelerini karşılaştırabilirsiniz bir işlev nesnesi sağlar.

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

Value_compare arasında tarafından sağlanan karşılaştırma ölçütü **value_types** hash_map tarafından bulunan tüm öğelerin yardımcı sınıf oluşturma ile ilgili öğelerin anahtarları arasında bir karşılaştırma gelen kopyaladığınızda. Üye işlevi işleci nesnesini kullanan **comp** türü `key_compare` iki öğeleri sıralama anahtarı bileşenlerinin Karşılaştırılacak value_compare tarafından sağlanan işlev nesnesi depolanır.

Value_compare hash_sets ve anahtar değerlerinin olduğu öğesi değerlerin aynı basit kapsayıcılar olan, hash_multisets için eşdeğer olan `key_compare`; hash_maps ve bunlar değildir, çünkü hash_multimaps türü değeri `pair` öğeleri öğenin anahtarı değeriyle aynı değil.

## <a name="example"></a>Örnek

Örneğin bkz [hash_map::value_comp](../standard-library/hash-map-class.md#value_comp) value_compare bildirme ve nasıl kullanılacağını gösteren bir örnek.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<hash_map >

**Namespace:** stdext

## <a name="see-also"></a>Ayrıca bkz.

[binary_function Yapısı](../standard-library/binary-function-struct.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
