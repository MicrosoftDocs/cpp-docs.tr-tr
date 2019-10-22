---
title: const_mem_fun_t Sınıfı
ms.date: 02/21/2019
f1_keywords:
- functional/std::const_mem_fun_t
helpviewer_keywords:
- const_mem_fun_t class
ms.assetid: f169d381-019b-4a0e-a9a3-54da6d948270
ms.openlocfilehash: 5263612a26b2bcb606ad712a2a8e0a521ce9437a
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688201"
---
# <a name="const_mem_fun_t-class"></a>const_mem_fun_t Sınıfı

Bir başvuru bağımsız değişkeniyle başlatıldığında birli işlev nesnesi olarak çağrılması için bağımsız değişken alan bir const üye işlevine izin veren bir bağdaştırıcı sınıfı. C++ 11 ' de kullanım dışı bırakılmıştır ve C++ 17 ' de kaldırılmıştır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Result, class Type>
class const_mem_fun_t : public unary_function <Type *, Result>
{
    explicit const_mem_fun_t(Result (Type::* Pm)() const);
    Result operator()(const Type* Pleft) const;
};
```

### <a name="parameters"></a>Parametreler

*Pm* \
İşlev nesnesine dönüştürülecek `Type` sınıfının üye işlevine yönelik bir işaretçi.

*Pleft* \
*PM* üye işlevinin çağrıldığı nesne.

## <a name="return-value"></a>Dönüş Değeri

Uyarlanabilir bir birli işlev.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, bir özel üye nesnesinde `Type` sınıfının üye işlevine bir işaretçi olması gereken *PM*kopyasını depolar. @No__t_0 üye işlevini, döndüren (`Pleft` -> \* `Pm`) () **const**olarak tanımlar.

## <a name="example"></a>Örnek

@No__t_0 Oluşturucusu genellikle doğrudan kullanılmaz; `mem_fun` yardımcı işlevi, üye işlevlerini uyarlamak için kullanılır. Üye işlev bağdaştırıcılarını nasıl kullanacağınızı gösteren bir örnek için bkz. [mem_fun](../standard-library/functional-functions.md#mem_fun) .
