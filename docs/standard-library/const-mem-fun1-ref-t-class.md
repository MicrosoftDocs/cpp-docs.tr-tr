---
title: const_mem_fun1_ref_t sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- xfunctional/std::const_mem_fun1_ref_t
dev_langs:
- C++
helpviewer_keywords:
- const_mem_fun1_ref_t class
ms.assetid: 8220d373-fa1c-44be-a21d-96d49b3ea6bb
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4236f510ad942dc0ab8cbe64a34670623ea3aaf2
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="constmemfun1reft-class"></a>const_mem_fun1_ref_t Sınıfı

Sağlayan bir bağdaştırıcı sınıfı bir **const** bir başvuru bağımsız değişkeni ile hazırlarken ikili işlevi nesnesi olarak çağrılacak tek bir bağımsız değişken üye işlevi.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Result, class Type, class Arg>
class const_mem_fun1_ref_t
 : public binary_function<Type, Arg, Result>
 {
    explicit const_mem_fun1_ref_t(Result (Type::* Pm)(Arg) const);
    Result operator()(const Type& left, Arg right) const;
 };
```

### <a name="parameters"></a>Parametreler

`Pm` Sınıfının üye işlevini gösteren bir işaretçi **türü** işlevi nesnesine dönüştürülecek.

`left` **Const** nesnesinin `Pm` üye işlevi çağrılır.

`right` İçin belirtilen bağımsız değişken `Pm`.

## <a name="return-value"></a>Dönüş Değeri

Uyarlanabilir bir ikili işlevi.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı, bir kopyasını depolar `Pm`, sınıfının üye işlevi için bir işaretçi olmalıdır **türü**, bir özel üye nesnesinde. Üye işlevini tanımlar `operator()` döndürme olarak ( `left`.\* *PM*) ( `right`) **const**.

## <a name="example"></a>Örnek

Oluşturucusunun `const_mem_fun1_ref_t` genellikle kullanılmaz doğrudan; yardımcı işlevini `mem_fun_ref` üye işlevleri uyarlamak için kullanılır. Bkz: [mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref) üye fonksiyonu bağdaştırıcıları kullanma örnekleri için.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<işlevsel >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
