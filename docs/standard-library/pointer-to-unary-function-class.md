---
title: pointer_to_unary_function Sınıfı
ms.date: 02/21/2019
f1_keywords:
- functional/std::pointer_to_unary
helpviewer_keywords:
- pointer_to_unary_function function
- pointer_to_unary_function class
ms.assetid: 05600207-b916-4759-beca-6b6facd2d6f6
ms.openlocfilehash: 710453711e60f4607a20eb3e71b65127c8dd5316
ms.sourcegitcommit: 4299caac2dc9e806c74ac833d856a3838b0f52a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2019
ms.locfileid: "57006662"
---
# <a name="pointertounaryfunction-class"></a>pointer_to_unary_function Sınıfı

Birli işlevi işaretçisi uyarlanabilir birli bir işleve dönüştürür. C ++ 17 sürümünde kaldırılmıştır C ++ 11'de kullanım dışı.

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

*pfunc*<br/>
Dönüştürülecek ikili fonksiyon.

*Sol*<br/>
Nesne,  *\*pfunc* üzerinde çağrılır.

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
