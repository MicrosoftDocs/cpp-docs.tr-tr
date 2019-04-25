---
title: gslice_array Sınıfı
ms.date: 11/04/2016
f1_keywords:
- valarray/std::gslice_array
helpviewer_keywords:
- gslice_array class
ms.assetid: ad1b4514-b14a-4baf-a293-d5a8e8674c75
ms.openlocfilehash: 1485b68f29651c0c42048fea02a8320ced8748aa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62159567"
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
