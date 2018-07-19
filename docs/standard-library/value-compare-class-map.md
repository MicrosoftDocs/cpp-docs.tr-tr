---
title: value_compare sınıfı (&lt;harita&gt;) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- std::value_compare
- std.value_compare
- map/std::value_compare
- value_compare
dev_langs:
- C++
helpviewer_keywords:
- std::value_compare
ms.assetid: ea97c1d0-04b2-4d42-8d96-23522c04cc41
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 46f8d00877aa4147e4b3e4ec2a6a23b70d8154c8
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38965854"
---
# <a name="valuecompare-class-ltmapgt"></a>value_compare sınıfı (&lt;harita&gt;)

Bir eşlemin öğelerini haritadaki kendi göreli sıralarını belirlemek için anahtarlarına değerlerini karşılaştırarak karşılaştıran bir işlev nesnesi sağlar.

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

Tarafından sağlanan karşılaştırma ölçütü `value_compare` arasında `value_types` eşlemesi tarafından bulunan tüm öğelerin yardımcı sınıf oluşturma ile ilgili öğelerin anahtarlarını arasında bir karşılaştırma alanından kaynaklanan. Üye işlevi işleci nesnenin kullandığı `comp` türü `key_compare` tarafından sağlanan işlev nesnede depolanan `value_compare` iki öğeyi sıralama anahtarı bileşenlerinin karşılaştırmak için.

Ayarlar ve basit kapsayıcılar anahtar değerlerinin olduğu öğe değerlerin aynı olan multisets `value_compare` eşdeğerdir `key_compare`; Haritalar ve bunlar değil, türü değeri olarak multimaps `pair` öğeleri aynı değil öğenin anahtar değeri.

## <a name="example"></a>Örnek

Örneğin bakın [value_comp](../standard-library/map-class.md#value_comp) bildirme ve kullanma konusunda bir örnek için `value_compare`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<harita >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[binary_function Yapısı](../standard-library/binary-function-struct.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
