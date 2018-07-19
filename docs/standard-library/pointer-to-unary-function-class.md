---
title: pointer_to_unary_function sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xfunctional/std::pointer_to_unary
dev_langs:
- C++
helpviewer_keywords:
- pointer_to_unary_function function
- pointer_to_unary_function class
ms.assetid: 05600207-b916-4759-beca-6b6facd2d6f6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 33161d622bf43b79b33c91a5abc6f703c48c4f2e
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953068"
---
# <a name="pointertounaryfunction-class"></a>pointer_to_unary_function Sınıfı

Birli işlevi işaretçisi uyarlanabilir birli bir işleve dönüştürür.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Arg, class Result>
class pointer_to_unary_function
    : public unary_function<Arg, Result>
{
public:
    explicit pointer_to_unary_function(Result(*pfunc)(Arg));
    Result operator()(Arg left) const;
};
```

### <a name="parameters"></a>Parametreler

*pfunc* dönüştürülecek ikili fonksiyon.

*Sol* nesne,  *\*pfunc* üzerinde çağrılır.

## <a name="return-value"></a>Dönüş Değeri

Şablon sınıfı bir kopyasını depolar `pfunc`. Onun üye işlevini tanımlar `operator()` döndüren olarak (\* **pfunc**) (_ *sol*).

## <a name="remarks"></a>Açıklamalar

Birli işlev işaretçisi işlev nesnesi ve bir birli işlevi parametre olarak bekleniyor herhangi bir C++ Standart Kitaplığı algoritma geçirilebilir, ancak uyarlanabilir değil. Bir değer için bağlama veya bir negator ile kullanarak bir bağdaştırıcı ile kullanmak için iç içe geçmiş türler ile sağlanan `argument_type` ve `result_type` oluşturan bir tür uyarlama mümkün. Dönüştürme `pointer_to_unary_function` ikili fonksiyon işaretçiler ile çalışmak işlev bağdaştırıcıları sağlar.

## <a name="example"></a>Örnek

Oluşturucusuna `pointer_to_unary_function` doğrudan nadiren kullanılır. Yardımcı işlevini bkz [ptr_fun](../standard-library/functional-functions.md#ptr_fun) bildirme ve kullanma konusunda bir örnek için `pointer_to_unary_function` bağdaştırıcısı koşul.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<işlev >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
