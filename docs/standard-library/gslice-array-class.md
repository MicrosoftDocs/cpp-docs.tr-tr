---
description: 'Hakkında daha fazla bilgi edinin: gslice_array sınıfı'
title: gslice_array Sınıfı
ms.date: 11/04/2016
f1_keywords:
- valarray/std::gslice_array
helpviewer_keywords:
- gslice_array class
ms.assetid: ad1b4514-b14a-4baf-a293-d5a8e8674c75
ms.openlocfilehash: 2c3cf29cd80d874265ec86d5c31a10e5c8359b8e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97232037"
---
# <a name="gslice_array-class"></a>gslice_array Sınıfı

Bir valarray genel dilimi tarafından tanımlanan alt küme dizileri arasında işlemler sağlayarak genel dilim nesnelerini destekleyen iç, yardımcı sınıf şablonu.

## <a name="syntax"></a>Syntax

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

Sınıfı, valarray sınıfının bir nesnesine bir başvuru depolayan bir nesneyi tanımlar `va` [](../standard-library/valarray-class.md) **\<Type>** , `gs` Bu, nesneden seçilecek öğelerin dizisini açıklayan [gslice](../standard-library/gslice-class.md) sınıfının bir nesnesidir `valarray<Type>` .

`gslice_array<Type>`Yalnızca [VA&#91;GS&#93;](../standard-library/valarray-class.md#op_at)bir ifade yazarak bir nesne oluşturursunuz. Gslice_array sınıfının üye işlevleri, için tanımlanan karşılık gelen işlev imzaları gibi davranır, ancak `valarray<Type>` yalnızca seçili öğelerin sırası etkilenir.

Sınıf şablonu belirli valarray işlemleri tarafından dolaylı olarak oluşturulur ve programda doğrudan kullanılamaz. Bunun yerine iç yardımcı sınıf şablonu, dilim alt simge işleci tarafından kullanılır:

`gslice_array`\< **Type**>`valarray` \< **Type**> :: `operator[]` ( **constgslice&**).

Bir `gslice_array<Type>` nesnesi `va[gsl]` , bir valarray dilimi için yalnızca formun bir ifadesini yazarak oluşturursunuz `gsl` `va` . Gslice_array sınıfının üye işlevleri, için tanımlanan karşılık gelen işlev imzaları gibi davranır, ancak `valarray<Type>` yalnızca seçili öğelerin sırası etkilenir. Gslice_array tarafından denetlenen sıra, dilim oluşturucusunun üç parametresi, ilk dilimdeki ilk öğenin dizini, her bir dilimdeki öğelerin sayısı ve her bir dilimdeki öğeler arasındaki mesafe tarafından tanımlanır.

Aşağıdaki örnekte:

```cpp
const size_t lv[] = {2, 3};
const size_t dv[] = {7, 2};
const valarray<size_t> len(lv, 2), str(dv, 2);

// va[gslice(3, len, str)] selects elements with
//   indices 3, 5, 7, 10, 12, 14
```

Yordamın geçerli olması için dizinlerin geçerli olması gerekir.

## <a name="example"></a>Örnek

Slice_array bildirme ve kullanma hakkında bir örnek için [gslice:: gslice](../standard-library/gslice-class.md#gslice) örneğine bakın.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<valarray>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
