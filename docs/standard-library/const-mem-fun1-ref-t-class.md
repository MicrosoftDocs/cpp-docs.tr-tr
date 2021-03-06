---
description: 'Hakkında daha fazla bilgi edinin: const_mem_fun1_ref_t sınıfı'
title: const_mem_fun1_ref_t Sınıfı
ms.date: 02/21/2019
f1_keywords:
- functional/std::const_mem_fun1_ref_t
helpviewer_keywords:
- const_mem_fun1_ref_t class
ms.assetid: 8220d373-fa1c-44be-a21d-96d49b3ea6bb
ms.openlocfilehash: f2d8b96c3888e3b7b07b5cccef8ce58cdedb6732
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324951"
---
# <a name="const_mem_fun1_ref_t-class"></a>const_mem_fun1_ref_t Sınıfı

**`const`** Bir başvuru bağımsız değişkeniyle başlatıldığında bir ikili işlev nesnesi olarak çağrılması için tek bir bağımsız değişken alan bir üye işlevine izin veren bir bağdaştırıcı sınıfı. C++ 11 ' de kullanım dışı bırakılmıştır ve C++ 17 ' de kaldırılmıştır.

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

*9*\
İşlev nesnesine dönüştürülecek sınıfın üye işlevine yönelik bir işaretçi `Type` .

*tarafta*\
**`const`** *PM* üye işlevinin çağrıldığı nesne.

*Right*\
*PM*'ye verilen bağımsız değişken.

## <a name="return-value"></a>Dönüş Değeri

Uyarlanabilir bir ikili işlev.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, bir  `Type` özel üye nesnesinde, sınıfının üye işlevine bir Işaretçi olması gereken PM kopyasını depolar. Üye işlevini `operator()` döndüren ( `left` . \* *PM*) () olarak tanımlar `right` **`const`** .

## <a name="example"></a>Örnek

Oluşturucusu `const_mem_fun1_ref_t` genellikle doğrudan kullanılmaz; yardımcı işlevi `mem_fun_ref` üye işlevlerini uyarlamak için kullanılır. Üye işlev bağdaştırıcılarını kullanma örnekleri için bkz. [mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref) .
