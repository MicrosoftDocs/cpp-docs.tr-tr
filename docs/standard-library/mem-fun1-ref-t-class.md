---
title: mem_fun1_ref_t sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xfunctional/std::mem_fun1_ref_t
dev_langs:
- C++
helpviewer_keywords:
- mem_fun1_ref_t class
ms.assetid: 7d6742f6-19ba-4523-b3c8-0e5b8f11464f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8d354e469b6b6a19d51ecedbc7f2106c21e82dab
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33852370"
---
# <a name="memfun1reft-class"></a>mem_fun1_ref_t Sınıfı

Sağlayan bir bağdaştırıcı sınıfı bir **non_const** bir başvuru bağımsız değişkeni ile hazırlarken ikili işlevi nesnesi olarak çağrılacak tek bir bağımsız değişken üye işlevi.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Result, class Type, class Arg>
class mem_fun1_ref_t : public binary_function<Type, Arg, Result> {
    explicit mem_fun1_ref_t(
    Result (Type::* _Pm)(Arg));

    Result operator()(
    Type& left,
    Arg right) const;

};
```

### <a name="parameters"></a>Parametreler

`_Pm` Sınıfının üye işlevini gösteren bir işaretçi **türü** işlevi nesnesine dönüştürülecek.

`left` Nesne, `_Pm` üye işlevi çağrılır.

`right` İçin belirtilen bağımsız değişken `_Pm`.

## <a name="return-value"></a>Dönüş Değeri

Uyarlanabilir bir ikili işlevi.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı, bir kopyasını depolar `_Pm`, sınıfının üye işlevi için bir işaretçi olmalıdır **türü**, bir özel üye nesnesinde. Üye işlevini tanımlar `operator()` döndürme olarak ( **sol**.\* `_Pm`) ( **sağ**).

## <a name="example"></a>Örnek

Oluşturucusunun `mem_fun1_ref_t` genellikle kullanılmaz doğrudan; yardımcı işlevini `mem_fun_ref` üye işlevleri uyarlamak için kullanılır. Bkz: [mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref) üye fonksiyonu bağdaştırıcıları kullanma örneği.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<işlevsel >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
