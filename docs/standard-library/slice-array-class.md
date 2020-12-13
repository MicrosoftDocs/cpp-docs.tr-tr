---
description: 'Hakkında daha fazla bilgi edinin: slice_array sınıfı'
title: slice_array Sınıfı
ms.date: 11/04/2016
f1_keywords:
- valarray/std::slice_array
helpviewer_keywords:
- slice_array class
ms.assetid: a182d5f7-f35c-4e76-86f2-b5ac64ddc846
ms.openlocfilehash: 580a09d99b08bc563c64571247d74a980eb229f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153986"
---
# <a name="slice_array-class"></a>slice_array Sınıfı

Bir valarray dilimi tarafından tanımlanan alt küme dizileri arasında işlemler sağlayarak dilim nesnelerini destekleyen dahili, yardımcı bir sınıf şablonu.

## <a name="syntax"></a>Syntax

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

Sınıfı, [](../standard-library/valarray-class.md) **\<Type>** **valarray \<Type>** nesnesinden seçilecek öğelerin dizisini açıklayan sınıf [diliminin](../standard-library/slice-class.md)bir nesnesiyle birlikte valarray sınıfının bir nesnesine başvuru depolayan bir nesneyi tanımlar.

Sınıf şablonu belirli valarray işlemleri tarafından dolaylı olarak oluşturulur ve programda doğrudan kullanılamaz. Dilim alt simge işleci tarafından kullanılan bir iç, yardımcı sınıf şablonu:

`slice_array`\< **Type**>`valarray` <  **Şunu yazın**:: `operator[]` ( `slice` ).

`slice_array<Type>`Yalnızca bir valarray dilimi için [VA&#91;SL&#93;](../standard-library/valarray-class.md#op_at)bir ifade yazarak bir nesne oluşturursunuz `sl` `va` . Slice_array sınıfının üye işlevleri, için tanımlanan karşılık gelen işlev imzaları gibi davranır, ancak `valarray<Type>` yalnızca seçili öğelerin sırası etkilenir. Slice_array tarafından denetlenen sıra, dilim oluşturucusunun üç parametresi, dilimin içindeki ilk öğenin dizini, öğe sayısı ve öğeler arasındaki mesafe tarafından tanımlanır. `va` **VA**[ `slice` (2, 5, 3)] tarafından belirtilen valarray öğesinden kesilen bir slice_array kesilmiş, dizin 2, 5, 8, 11 ve 14 olan öğeleri seçer `va` . Yordamın geçerli olması için dizinlerin geçerli olması gerekir.

## <a name="example"></a>Örnek

Slice_array bildirme ve kullanma hakkında bir örnek için [Slice:: Slice](../standard-library/slice-class.md#slice) örneğine bakın.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<valarray>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
