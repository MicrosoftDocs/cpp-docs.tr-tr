---
title: slice_array Sınıfı
ms.date: 11/04/2016
f1_keywords:
- valarray/std::slice_array
helpviewer_keywords:
- slice_array class
ms.assetid: a182d5f7-f35c-4e76-86f2-b5ac64ddc846
ms.openlocfilehash: 358348a57b823fcea82cd296967c83778819361d
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688956"
---
# <a name="slice_array-class"></a>slice_array Sınıfı

Bir valarray dilimi tarafından tanımlanan alt küme dizileri arasında işlemler sağlayarak dilim nesnelerini destekleyen dahili, yardımcı bir sınıf şablonu.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type>
class slice_array : public slice {
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

Sınıfı [,](../standard-library/slice-class.md)valarray \<Type arasından seçilecek öğelerin dizisini açıklayan [valarray](../standard-library/valarray-class.md)  **\<Type >** sınıfının bir nesnesi için bir başvuru depolayan bir nesne tanımlar **>** nesne.

Sınıf şablonu belirli valarray işlemleri tarafından dolaylı olarak oluşturulur ve programda doğrudan kullanılamaz. Dilim alt simge işleci tarafından kullanılan bir iç, yardımcı sınıf şablonu:

`slice_array` \< **türü** >  `valarray` < **type**:: `operator[]` (`slice`).

Yalnızca bir valarray `va` dilim `sl` için [VA&#91;SL&#93;](../standard-library/valarray-class.md#op_at)biçiminde bir ifade yazarak `slice_array<Type>` nesnesi oluşturursunuz. Slice_array sınıfının üye işlevleri, `valarray<Type>` için tanımlanan karşılık gelen işlev imzaları gibi davranır, ancak yalnızca seçili öğelerin sırası etkilenir. Slice_array tarafından denetlenen sıra, dilim oluşturucusunun üç parametresi, dilimin içindeki ilk öğenin dizini, öğe sayısı ve öğeler arasındaki mesafe tarafından tanımlanır. **VA**[`slice` (2, 5, 3)] tarafından belirtilen valarray `va` kesilen bir slice_array cut, `va` dizin 2, 5, 8, 11 ve 14 olan öğeleri seçer. Yordamın geçerli olması için dizinlerin geçerli olması gerekir.

## <a name="example"></a>Örnek

Bir slice_array nasıl bildirilemeyeceğini ve kullanacağınızı gösteren bir örnek için [Slice:: Slice](../standard-library/slice-class.md#slice) örneğine bakın.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<valarray >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
