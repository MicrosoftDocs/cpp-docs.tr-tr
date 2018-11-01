---
title: slice_array Sınıfı
ms.date: 11/04/2016
f1_keywords:
- valarray/std::slice_array
helpviewer_keywords:
- slice_array class
ms.assetid: a182d5f7-f35c-4e76-86f2-b5ac64ddc846
ms.openlocfilehash: 9577447b2201c1c9e53192b99abad1979f45d15f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50467225"
---
# <a name="slicearray-class"></a>slice_array Sınıfı

Dilim nesneleri bir valarray dilim tarafından tanımlanan alt diziler arasındaki işlemleri sağlayarak destekleyen bir iç, yardımcı Şablon sınıfı.

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

Sınıf bir başvuru sınıfının bir nesnesi depolayan bir nesneyi tanımlayan [valarray](../standard-library/valarray-class.md)**\<türü >**, sınıfın bir nesnesi birlikte [dilim](../standard-library/slice-class.md), hangi aralarından seçim yapabileceğiniz öğelerin sıralamasını açıklar **valarray\<türü >** nesne.

Şablon sınıfı, belirli valarray işlemleri tarafından dolaylı olarak oluşturulur ve programda doğrudan kullanılamaz. Dilim alt simge işleci tarafından kullanılan bir iç, ikincil bir şablon sınıfı:

`slice_array`\< **Tür**> `valarray`< **türü**:: `operator[]` ( `slice`).

Oluşturmak bir `slice_array<Type>` biçiminde bir ifade yazarak yalnızca nesne [va&#91;sl&#93;](../standard-library/valarray-class.md#op_at), bir dilimin `sl` valarray, `va`. Slice_array sınıfı üye işlevleri sonra karşılık gelen işlev imzası için tanımlanan gibi davranmasını `valarray<Type>`dışında yalnızca seçilen öğelerin sırası etkilenmez. Slice_array tarafından denetlenen dizinin dilim, öğelerin sayısını ve öğeler arasındaki uzaklık ilk öğenin dizinini dilim oluşturucunun üç parametreyle tanımlanır. Valarray bir slice_array Kes `va` tarafından bildirilen **va**[ `slice`(2, 5, 3)] ile dizin 2, 5, 8, 11 ve 14'öğeleri seçer `va`. Dizinleri yordamın geçerli olması için geçerli olmalıdır.

## <a name="example"></a>Örnek

Örneğin bakın [slice::slice](../standard-library/slice-class.md#slice) bildirme ve bir slice_array kullanma konusunda bir örnek.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<valarray >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
