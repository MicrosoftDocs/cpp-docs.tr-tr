---
title: pointer_to_unary_function sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- xfunctional/std::pointer_to_unary
dev_langs:
- C++
helpviewer_keywords:
- pointer_to_unary_function function
- pointer_to_unary_function class
ms.assetid: 05600207-b916-4759-beca-6b6facd2d6f6
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5cbcad162304a4eb7750c543deac5c8e00127b2a
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="pointertounaryfunction-class"></a>pointer_to_unary_function Sınıfı

Birli işlev işaretçisi uyarlanabilir birli işlevdeki dönüştürür.

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

`pfunc` Dönüştürülecek ikili işlev.

`left` Nesne,  *\*pfunc* üzerinde çağrılır.

## <a name="return-value"></a>Dönüş Değeri

Şablon sınıfı, bir kopyasını depolar **pfunc**. Üye işlevini tanımlar `operator()` döndürme olarak (\* **pfunc**) (_ *sol*).

## <a name="remarks"></a>Açıklamalar

Birli işlev işaretçisi bir işlev nesnesi ve birli işlevi parametre olarak bekleniyor tüm C++ Standart Kitaplığı algoritmalar için geçirilen, ancak uyarlanabilir değil. Bir değer için bağlama veya bir negator ile kullanarak gibi bir bağdaştırıcı ile kullanmak için iç içe geçmiş türler ile sağlanan **argument_type** ve **result_type** olduğundan olun böyle bir uyarlama mümkün. Dönüştürme `pointer_to_unary_function` ikili işlev işaretçileri ile çalışmak işlevi bağdaştırıcıları sağlar.

## <a name="example"></a>Örnek

Oluşturucusunun `pointer_to_unary_function` nadiren doğrudan kullanılır. Yardımcı işlevini bkz [ptr_fun](../standard-library/functional-functions.md#ptr_fun) bildirme ve kullanma konusunda bir örnek için `pointer_to_unary_function` bağdaştırıcısı koşulu.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<işlevsel >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
