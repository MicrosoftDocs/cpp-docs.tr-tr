---
title: pointer_to_unary_function Sınıfı
ms.date: 02/21/2019
f1_keywords:
- functional/std::pointer_to_unary
helpviewer_keywords:
- pointer_to_unary_function function
- pointer_to_unary_function class
ms.assetid: 05600207-b916-4759-beca-6b6facd2d6f6
ms.openlocfilehash: cff84f1f15eea34c60162f702dfe05350d1383d1
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68240464"
---
# <a name="pointertounaryfunction-class"></a>pointer_to_unary_function Sınıfı

Birli işlevi işaretçisi uyarlanabilir birli bir işleve dönüştürür. C ++ 17 sürümünde kaldırılmıştır C ++ 11'de kullanım dışı.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Arg, class Result>
class pointer_to_unary_function
    : public unary_function<Arg, Result>
{
    explicit pointer_to_unary_function(Result(*pfunc)(Arg));
    Result operator()(Arg left) const;
};
```

### <a name="parameters"></a>Parametreler

*pfunc*\
Dönüştürülecek ikili fonksiyon.

*Sol*\
Nesne,  *\*pfunc* üzerinde çağrılır.

## <a name="return-value"></a>Dönüş Değeri

Şablon sınıfı bir kopyasını depolar `pfunc`. Onun üye işlevini tanımlar `operator()` döndüren olarak (\* **pfunc**) (_ *sol*).

## <a name="remarks"></a>Açıklamalar

Birli işlev işaretçisi işlev nesnesi ve bir birli işlevi parametre olarak bekleniyor herhangi bir C++ Standart Kitaplığı algoritma geçirilebilir, ancak uyarlanabilir değil. Bir değer için bağlama veya bir negator ile kullanarak bir bağdaştırıcı ile kullanmak için iç içe geçmiş türler ile sağlanan `argument_type` ve `result_type` oluşturan bir tür uyarlama mümkün. Dönüştürme `pointer_to_unary_function` ikili fonksiyon işaretçiler ile çalışmak işlev bağdaştırıcıları sağlar.

## <a name="example"></a>Örnek

Oluşturucusuna `pointer_to_unary_function` doğrudan nadiren kullanılır. Yardımcı işlevini bkz [ptr_fun](../standard-library/functional-functions.md#ptr_fun) bildirme ve kullanma konusunda bir örnek için `pointer_to_unary_function` bağdaştırıcısı koşul.
