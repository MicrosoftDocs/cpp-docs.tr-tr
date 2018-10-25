---
title: gslice_array sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- valarray/std::gslice_array
dev_langs:
- C++
helpviewer_keywords:
- gslice_array class
ms.assetid: ad1b4514-b14a-4baf-a293-d5a8e8674c75
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0f88957ac4c9ce14d05a71c266607e499c512541
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50059044"
---
# <a name="gslicearray-class"></a>gslice_array Sınıfı

Genel bir valarray dilim tarafından tanımlanan alt diziler arasındaki işlemleri sağlayarak genel dilimi nesneleri destekleyen bir iç, yardımcı Şablon sınıfı.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type>
class gslice_array : public gsplice {
public:
    typedef Type value_type;
    void operator=(const valarray<Type>& x) const;

    void operator=(const Type& x) const;

    void operator*=(const valarray<Type>& x) const;

    void operator/=(const valarray<Type>& x) const;

    void operator%=(const valarray<Type>& x) const;

    void operator+=(const valarray<Type>& x) const;

    void operator-=(const valarray<Type>& x) const;

    void operator^=(const valarray<Type>& x) const;

    void operator&=(const valarray<Type>& x) const;

    void operator|=(const valarray<Type>& x) const;

    void operator<<=(const valarray<Type>& x) const;

    void operator>>=(const valarray<Type>& x) const;

// The rest is private or implementation defined
}
```

## <a name="remarks"></a>Açıklamalar

Sınıfı bir nesneye bir başvuru depolayan nesneyi tanımlar `va` sınıfın [valarray](../standard-library/valarray-class.md)**\<türü >**, nesneyle birlikte `gs` sınıfın [ gslice](../standard-library/gslice-class.md) seçim yapılacak öğe dizisi açıklayan `valarray<Type>` nesne.

Oluşturmak bir `gslice_array<Type>` biçiminde bir ifade yazarak yalnızca nesne [va&#91;gs&#93;](../standard-library/valarray-class.md#op_at). Gslice_array sınıfı üye işlevleri sonra karşılık gelen işlev imzası için tanımlanan gibi davranmasını `valarray<Type>`dışında yalnızca seçilen öğelerin sırası etkilenmez.

Şablon sınıfı, belirli valarray işlemleri tarafından dolaylı olarak oluşturulur ve programda doğrudan kullanılamaz. Bir iç yardımcı Şablon sınıfı, bunun yerine dilim alt simge işleci tarafından kullanılır:

`gslice_array`\< **Tür** >  `valarray` \< **türü**>:: `operator[]` ( **constgslice &**).

Oluşturmak bir `gslice_array<Type>` biçiminde bir ifade yazarak yalnızca nesne `va[gsl]`, bir dilimin `gsl` valarray, `va`. Gslice_array sınıfı üye işlevleri sonra karşılık gelen işlev imzası için tanımlanan gibi davranmasını `valarray<Type>`dışında yalnızca seçilen öğelerin sırası etkilenmez. Gslice_array tarafından denetlenen dizinin ilk dilim, her bir dilimi ve her öğeler arasındaki uzaklık içindeki öğelerin sayısını ilk öğenin dizinini dilim oluşturucunun üç parametreyle tanımlanır.

Aşağıdaki örnekte:

```cpp
const size_t lv[] = {2, 3};
const size_t dv[] = {7, 2};
const valarray<size_t> len(lv, 2), str(dv, 2);

// va[gslice(3, len, str)] selects elements with
//   indices 3, 5, 7, 10, 12, 14
```

Dizinleri yordamın geçerli olması için geçerli olmalıdır.

## <a name="example"></a>Örnek

Örneğin bakın [gslice::gslice](../standard-library/gslice-class.md#gslice) bildirme ve bir slice_array kullanma konusunda bir örnek.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<valarray >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
