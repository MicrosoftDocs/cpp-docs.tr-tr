---
title: gslice_array Sınıfı
ms.date: 11/04/2016
f1_keywords:
- valarray/std::gslice_array
helpviewer_keywords:
- gslice_array class
ms.assetid: ad1b4514-b14a-4baf-a293-d5a8e8674c75
ms.openlocfilehash: 37c54d09fdfe920c832c4baa7984fee4e090d04a
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448929"
---
# <a name="gslicearray-class"></a>gslice_array Sınıfı

Bir valarray genel dilimi tarafından tanımlanan alt küme dizileri arasında işlemler sağlayarak genel dilim nesnelerini destekleyen iç, yardımcı şablon sınıfı.

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

Sınıfı, `va` [valarray](../standard-library/valarray-class.md) `gs` [](../standard-library/gslice-class.md) **Type>sınıfınınbirnesnesinebirbaşvurudepolayanbirnesnetanımlarvebirgslicesınıfınınarasındanseçilecek\<** öğelerin dizisini açıklayan bir nesneyle birlikte `valarray<Type>` nesnesi.

Yalnızca form `gslice_array<Type>` [VA&#91;GS&#93;](../standard-library/valarray-class.md#op_at)ifadesi yazarak bir nesne oluşturursunuz. Gslice_array sınıfının üye işlevleri, için `valarray<Type>`tanımlanan karşılık gelen işlev imzaları gibi davranır, ancak yalnızca seçili öğelerin sırası etkilenir.

Şablon sınıfı belirli valarray işlemleri tarafından dolaylı olarak oluşturulur ve programda doğrudan kullanılamaz. Bunun yerine iç yardımcı şablon sınıfı, dilim alt simge işleci tarafından kullanılır:

`gslice_array`\<**Tür** >   >: :`operator[]` (Constgslice &) yazın. `valarray` \<

Bir `gslice_array<Type>` nesnesi, bir valarray `va[gsl]` `gsl` dilimi`va`için yalnızca formun bir ifadesini yazarak oluşturursunuz. Gslice_array sınıfının üye işlevleri, için `valarray<Type>`tanımlanan karşılık gelen işlev imzaları gibi davranır, ancak yalnızca seçili öğelerin sırası etkilenir. Gslice_array tarafından denetlenen sıra, dilim oluşturucusunun üç parametresi, ilk dilimdeki ilk öğenin dizini, her bir dilimdeki öğelerin sayısı ve her bir dilimdeki öğeler arasındaki mesafe tarafından tanımlanır.

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
