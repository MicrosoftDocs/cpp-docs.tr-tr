---
title: gslice_array Sınıfı
ms.date: 11/04/2016
f1_keywords:
- valarray/std::gslice_array
helpviewer_keywords:
- gslice_array class
ms.assetid: ad1b4514-b14a-4baf-a293-d5a8e8674c75
ms.openlocfilehash: 68ce774128395e941ff80580a02c4ee28a74a4e4
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689592"
---
# <a name="gslice_array-class"></a>gslice_array Sınıfı

Bir valarray genel dilimi tarafından tanımlanan alt küme dizileri arasında işlemler sağlayarak genel dilim nesnelerini destekleyen iç, yardımcı sınıf şablonu.

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

Sınıfı, `valarray<Type>` nesnesinden seçilecek öğelerin dizisini açıklayan [gslice](../standard-library/gslice-class.md) sınıfının bir nesne `gs` birlikte [valarray](../standard-library/valarray-class.md)  **\<Type >** sınıfının bir nesne `va` bir başvurusunu depolayan bir nesne tanımlar.

Yalnızca bir `gslice_array<Type>` nesnesi oluşturarak [&#91;&#93;](../standard-library/valarray-class.md#op_at)bir nesne oluşturun. Gslice_array sınıfının üye işlevleri, `valarray<Type>` için tanımlanan karşılık gelen işlev imzaları gibi davranır, ancak yalnızca seçili öğelerin sırası etkilenir.

Sınıf şablonu belirli valarray işlemleri tarafından dolaylı olarak oluşturulur ve programda doğrudan kullanılamaz. Bunun yerine iç yardımcı sınıf şablonu, dilim alt simge işleci tarafından kullanılır:

`gslice_array` \< **türü** >  `valarray` \< **Type**>:: `operator[]` ( **constgslice &** ).

Bir `gslice_array<Type>` nesnesi, valarray `va` Slice `gsl` için form `va[gsl]` bir ifadesi yazarak oluşturursunuz. Gslice_array sınıfının üye işlevleri, `valarray<Type>` için tanımlanan karşılık gelen işlev imzaları gibi davranır, ancak yalnızca seçili öğelerin sırası etkilenir. Gslice_array tarafından denetlenen sıra, dilim oluşturucusunun üç parametresi, ilk dilimdeki ilk öğenin dizini, her bir dilimdeki öğelerin sayısı ve her bir dilimdeki öğeler arasındaki mesafe tarafından tanımlanır.

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

Bir slice_array nasıl bildirilemeyeceğini ve kullanacağınızı gösteren bir örnek için [gslice:: gslice](../standard-library/gslice-class.md#gslice) örneğine bakın.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<valarray >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
