---
title: pointer_to_binary_function Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xfunctional/std::pointer_to_binary
helpviewer_keywords:
- pointer_to_binary_function function
- pointer_to_binary_function class
ms.assetid: fb50599f-bcb3-4076-a669-6dcc3eb189a5
ms.openlocfilehash: 42e57c9fd5dafb60a866b24a7a5b8496643d1c76
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50487093"
---
# <a name="pointertobinaryfunction-class"></a>pointer_to_binary_function Sınıfı

Bir ikili fonksiyon işaretçi ikili uyarlanabilir bir işleve dönüştürür.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Arg1, class Arg2, class Result>
class pointer_to_binary_function
    : public binary_function <Arg1, Arg2, Result>
{
public:
    explicit pointer_to_binary_function(
        Result(*pfunc)(Arg1, Arg2));
    Result operator()(Arg1 left, Arg2 right) const;
};
```

### <a name="parameters"></a>Parametreler

*pfunc*<br/>
Dönüştürülecek ikili fonksiyon.

*Sol*<br/>
Sol nesne  *\*pfunc* üzerinde çağrılır.

*sağ*<br/>
Sağa nesne  *\*pfunc* üzerinde çağrılır.

## <a name="return-value"></a>Dönüş Değeri

Şablon sınıfı bir kopyasını depolar `pfunc`. Onun üye işlevini tanımlar `operator()` döndüren olarak (\* **pfunc**) (_ *sol*, \_ *sağ*).

## <a name="remarks"></a>Açıklamalar

Bir ikili fonksiyon işaretçi bir işlev nesnesi ve ikili bir işlev bir parametre olarak bekleniyor herhangi bir C++ Standart Kitaplığı algoritma geçirilebilir, ancak uyarlanabilir değil. Bir değer için bağlama veya bir negator ile kullanarak bir bağdaştırıcı ile kullanmak için iç içe geçmiş türler ile sağlanan `first_argument_type`, `second_argument_type`, ve `result_type` oluşturan bir tür uyarlama mümkün. Dönüştürme `pointer_to_binary_function` ikili fonksiyon işaretçiler ile çalışmak işlev bağdaştırıcıları sağlar.

## <a name="example"></a>Örnek

Oluşturucusuna `pointer_to_binary_function` doğrudan nadiren kullanılır. Yardımcı işlevini bkz [ptr_fun](../standard-library/functional-functions.md#ptr_fun) bildirme ve kullanma konusunda bir örnek için `pointer_to_binary_function` bağdaştırıcısı koşul.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<işlev >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
