---
title: const_mem_fun_ref_t sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xfunctional/std::const_mem_fun_ref_t
dev_langs:
- C++
helpviewer_keywords:
- const_mem_fun_ref_t class
ms.assetid: 316ddbaa-9f46-4931-8eba-ea4ca66360ef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 29c86f71912c5fe4cf3f5d2fc0df37c8530a8517
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="constmemfunreft-class"></a>const_mem_fun_ref_t Sınıfı

Sağlayan bir bağdaştırıcı sınıfı bir **const** bir başvuru bağımsız değişkeni ile hazırlarken birli işlevi nesnesi olarak çağrılacak bağımsız değişken almayan üye işlevi.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Result, class Type>
class const_mem_fun_ref_t
 : public unary_function<Type, Result>
{
    explicit const_mem_fun_t(Result (Type::* Pm)() const);
    Result operator()(const Type& left) const;
 };
```

### <a name="parameters"></a>Parametreler

`Pm` Sınıfının üye işlevini gösteren bir işaretçi **türü** işlevi nesnesine dönüştürülecek.

`left` Nesne, `Pm` üye işlevi çağrılır.

## <a name="return-value"></a>Dönüş Değeri

Bir uyarlanabilir birli işlevi.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı, bir kopyasını depolar `Pm`, sınıfının üye işlevi için bir işaretçi olmalıdır **türü**, bir özel üye nesnesinde. Üye işlevini tanımlar `operator()` döndürme olarak ( **sol**.\* `Pm`) () **const**.

## <a name="example"></a>Örnek

Oluşturucusunun `const_mem_fun_ref_t` genellikle kullanılmaz doğrudan; yardımcı işlevini `mem_fun_ref` üye işlevleri uyarlamak için kullanılır. Bkz: [mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref) üye fonksiyonu bağdaştırıcıları kullanma örneği.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<işlevsel >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
