---
title: pointer_to_binary_function sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- xfunctional/std::pointer_to_binary
dev_langs:
- C++
helpviewer_keywords:
- pointer_to_binary_function function
- pointer_to_binary_function class
ms.assetid: fb50599f-bcb3-4076-a669-6dcc3eb189a5
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3e43c5f906aa68480120df504b95152bbd346348
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="pointertobinaryfunction-class"></a>pointer_to_binary_function Sınıfı

Bir ikili işlev işaretçisi uyarlanabilir ikili işlevdeki dönüştürür.

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

`pfunc` Dönüştürülecek ikili işlev.

`left` Sol nesne  *\*pfunc* üzerinde çağrılır.

`right` Sağa nesne  *\*pfunc* üzerinde çağrılır.

## <a name="return-value"></a>Dönüş Değeri

Şablon sınıfı, bir kopyasını depolar **pfunc**. Üye işlevini tanımlar `operator()` döndürme olarak (\* **pfunc**) (_ *sol*, \_ *sağ*).

## <a name="remarks"></a>Açıklamalar

Bir ikili işlev işaretçisi bir işlev nesnesi ve ikili işlevi parametre olarak bekleniyor tüm C++ Standart Kitaplığı algoritmalar için geçirilen, ancak uyarlanabilir değil. Bir değer için bağlama veya bir negator ile kullanarak gibi bir bağdaştırıcı ile kullanmak için iç içe geçmiş türler ile sağlanan **first_argument_type**, **second_argument_type**, ve **result_type**  olduğundan olun böyle bir uyarlama mümkün. Dönüştürme `pointer_to_binary_function` ikili işlev işaretçileri ile çalışmak işlevi bağdaştırıcıları sağlar.

## <a name="example"></a>Örnek

Oluşturucusunun `pointer_to_binary_function` nadiren doğrudan kullanılır. Yardımcı işlevini bkz [ptr_fun](../standard-library/functional-functions.md#ptr_fun) bildirme ve kullanma konusunda bir örnek için `pointer_to_binary_function` bağdaştırıcısı koşulu.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<işlevsel >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
