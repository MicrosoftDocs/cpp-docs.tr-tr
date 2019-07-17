---
title: pointer_to_binary_function Sınıfı
ms.date: 02/21/2019
f1_keywords:
- functional/std::pointer_to_binary
helpviewer_keywords:
- pointer_to_binary_function function
- pointer_to_binary_function class
ms.assetid: fb50599f-bcb3-4076-a669-6dcc3eb189a5
ms.openlocfilehash: fcc643d7569bd4f71b11249babdb49ef1362dc8b
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68240487"
---
# <a name="pointertobinaryfunction-class"></a>pointer_to_binary_function Sınıfı

Bir ikili fonksiyon işaretçi ikili uyarlanabilir bir işleve dönüştürür. C ++ 17 sürümünde kaldırılmıştır C ++ 11'de kullanım dışı.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Arg1, class Arg2, class Result>
class pointer_to_binary_function
    : public binary_function <Arg1, Arg2, Result>
{
    explicit pointer_to_binary_function(
        Result(*pfunc)(Arg1, Arg2));
    Result operator()(Arg1 left, Arg2 right) const;
};
```

### <a name="parameters"></a>Parametreler

*pfunc*\
Dönüştürülecek ikili fonksiyon.

*Sol*\
Sol nesne  *\*pfunc* üzerinde çağrılır.

*sağ*\
Sağa nesne  *\*pfunc* üzerinde çağrılır.

## <a name="return-value"></a>Dönüş Değeri

Şablon sınıfı bir kopyasını depolar `pfunc`. Onun üye işlevini tanımlar `operator()` döndüren olarak `(* pfunc)(Left, right)`.

## <a name="remarks"></a>Açıklamalar

Bir ikili fonksiyon işaretçi bir işlev nesnesi ve ikili bir işlev bir parametre olarak bekleniyor herhangi bir C++ Standart Kitaplığı algoritma geçirilebilir, ancak uyarlanabilir değil. Bir değer için bağlama veya bir negator ile kullanarak bir bağdaştırıcı ile kullanmak için iç içe geçmiş türler ile sağlanan `first_argument_type`, `second_argument_type`, ve `result_type` oluşturan bir tür uyarlama mümkün. Dönüştürme `pointer_to_binary_function` ikili fonksiyon işaretçiler ile çalışmak işlev bağdaştırıcıları sağlar.

## <a name="example"></a>Örnek

Oluşturucusuna `pointer_to_binary_function` doğrudan nadiren kullanılır. Yardımcı işlevini bkz [ptr_fun](../standard-library/functional-functions.md#ptr_fun) bildirme ve kullanma konusunda bir örnek için `pointer_to_binary_function` bağdaştırıcısı koşul.
