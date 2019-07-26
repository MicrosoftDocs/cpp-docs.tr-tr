---
title: slice_array Sınıfı
ms.date: 11/04/2016
f1_keywords:
- valarray/std::slice_array
helpviewer_keywords:
- slice_array class
ms.assetid: a182d5f7-f35c-4e76-86f2-b5ac64ddc846
ms.openlocfilehash: cf33c5f627a88698c84947f9b803edaebccf5566
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68450411"
---
# <a name="slicearray-class"></a>slice_array Sınıfı

Bir valarray dilimi tarafından tanımlanan alt küme dizileri arasında işlemler sağlayarak dilim nesnelerini destekleyen dahili, yardımcı şablon sınıfı.

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

Sınıfı, [valarray](../standard-library/valarray-class.md) **\<> türündeki**bir nesneye başvuru depolayan bir nesneyi tanımlar, bu, [](../standard-library/slice-class.md) **valarray\<'denseçileceköğelerindizisiniaçıklayansınıfdiliminesnesiylebirlikte.> Nesne yazın** .

Şablon sınıfı belirli valarray işlemleri tarafından dolaylı olarak oluşturulur ve programda doğrudan kullanılamaz. Dilim alt simge işleci tarafından kullanılan bir iç, yardımcı şablon sınıfı:

`slice_array`\<**Tür** >  **Şunu yazın**: :`operator[]` ( )`slice`. `valarray` < 

Yalnızca bir valarray `slice_array<Type>` dilimiiçin`sl` [VA&#91;SL&#93;](../standard-library/valarray-class.md#op_at)biçiminde bir ifade yazarak bir nesne oluşturursunuz. `va` Slice_array sınıfının üye işlevleri, için `valarray<Type>`tanımlanan karşılık gelen işlev imzaları gibi davranır, ancak yalnızca seçili öğelerin sırası etkilenir. Slice_array tarafından denetlenen sıra, dilim oluşturucusunun üç parametresi, dilimin içindeki ilk öğenin dizini, öğe sayısı ve öğeler arasındaki mesafe tarafından tanımlanır. `va` **VA**[ `va`(2, 5, 3)] tarafından belirtilen valarray 'den kesilen bir slice_array kes, dizin 2, 5, 8, 11 ve 14 olan öğeleri seçer. `slice` Yordamın geçerli olması için dizinlerin geçerli olması gerekir.

## <a name="example"></a>Örnek

Bir slice_array nasıl bildirilemeyeceğini ve kullanacağınızı gösteren bir örnek için [Slice:: Slice](../standard-library/slice-class.md#slice) örneğine bakın.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<valarray >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
