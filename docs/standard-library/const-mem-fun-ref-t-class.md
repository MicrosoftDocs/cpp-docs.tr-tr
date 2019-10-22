---
title: const_mem_fun_ref_t Sınıfı
ms.date: 02/21/2019
f1_keywords:
- functional/std::const_mem_fun_ref_t
helpviewer_keywords:
- const_mem_fun_ref_t class
ms.assetid: 316ddbaa-9f46-4931-8eba-ea4ca66360ef
ms.openlocfilehash: 8ce29eb0d2122dbd95fea34fa59f3fa11b9b388e
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689767"
---
# <a name="const_mem_fun_ref_t-class"></a>const_mem_fun_ref_t Sınıfı

Bir başvuru bağımsız değişkeniyle başlatıldığında birli işlev nesnesi olarak çağrılması için bağımsız değişken alan bir **const** üye işlevine izin veren bir bağdaştırıcı sınıfı. C++ 11 ' de kullanım dışı bırakılmıştır ve C++ 17 ' de kaldırılmıştır.

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

*Pm* \
İşlev nesnesine dönüştürülecek `Type` sınıfının üye işlevine yönelik bir işaretçi.

*sol* \
*PM* üye işlevinin çağrıldığı nesne.

## <a name="return-value"></a>Dönüş Değeri

Uyarlanabilir bir birli işlev.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, bir özel üye nesnesinde `Type` sınıfının üye işlevine bir işaretçi olması gereken *PM*kopyasını depolar. @No__t_0 üye işlevini, döndüren (**Left**. \* `Pm`) () **const**olarak tanımlar.

## <a name="example"></a>Örnek

@No__t_0 Oluşturucusu genellikle doğrudan kullanılmaz; `mem_fun_ref` yardımcı işlevi, üye işlevlerini uyarlamak için kullanılır. Üye işlev bağdaştırıcılarını nasıl kullanacağınızı gösteren bir örnek için bkz. [mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref) .
