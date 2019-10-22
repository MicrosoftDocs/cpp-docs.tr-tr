---
title: const_mem_fun1_ref_t Sınıfı
ms.date: 02/21/2019
f1_keywords:
- functional/std::const_mem_fun1_ref_t
helpviewer_keywords:
- const_mem_fun1_ref_t class
ms.assetid: 8220d373-fa1c-44be-a21d-96d49b3ea6bb
ms.openlocfilehash: 76fae1ce29cb4c47870e45e8f946f6ff1fea1885
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688184"
---
# <a name="const_mem_fun1_ref_t-class"></a>const_mem_fun1_ref_t Sınıfı

Bir başvuru bağımsız değişkeniyle başlatıldığında bir ikili işlev nesnesi olarak çağrılması için tek bir bağımsız değişken alan bir **const** üye işlevine izin veren bir bağdaştırıcı sınıfı. C++ 11 ' de kullanım dışı bırakılmıştır ve C++ 17 ' de kaldırılmıştır.

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

*Pm* \
İşlev nesnesine dönüştürülecek `Type` sınıfının üye işlevine yönelik bir işaretçi.

*sol* \
*PM* üye işlevinin çağrıldığı **const** nesnesi.

*sağ* \
*PM*'ye verilen bağımsız değişken.

## <a name="return-value"></a>Dönüş Değeri

Uyarlanabilir bir ikili işlev.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, bir özel üye nesnesinde `Type` sınıfının üye işlevine bir işaretçi olması gereken *PM*kopyasını depolar. @No__t_0 üye işlevini, döndüren (`left`. \* *PM*) (`right`) **const**olarak tanımlar.

## <a name="example"></a>Örnek

@No__t_0 Oluşturucusu genellikle doğrudan kullanılmaz; `mem_fun_ref` yardımcı işlevi, üye işlevlerini uyarlamak için kullanılır. Üye işlev bağdaştırıcılarını kullanma örnekleri için bkz. [mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref) .
