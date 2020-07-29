---
title: const_mem_fun1_t Sınıfı
ms.date: 02/21/2019
f1_keywords:
- functional/std::const_mem_fun1_t
helpviewer_keywords:
- const_mem_fun1_t class
ms.assetid: 250fac30-9663-4133-9051-6303f76ea259
ms.openlocfilehash: 93d0e7a116c7c7ba7a2ed1cb46fd88585a99120d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228329"
---
# <a name="const_mem_fun1_t-class"></a>const_mem_fun1_t Sınıfı

**`const`** Bir işaretçi bağımsız değişkeniyle başlatıldığında bir ikili işlev nesnesi olarak çağrılması için tek bir bağımsız değişken alan bir üye işlevine izin veren bir bağdaştırıcı sınıfı. C++ 11 ' de kullanım dışı bırakılmıştır ve C++ 17 ' de kaldırılmıştır.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class Result, class Type, class Arg>
class const_mem_fun1_t : public binary_function<const Type *, Arg, Result>
{
    explicit const_mem_fun1_t(Result (Type::* member_ptr)(Arg) const);
    Result operator()(const Type* left, Arg right) const;
};
```

### <a name="parameters"></a>Parametreler

*member_ptr*\
İşlev nesnesine dönüştürülecek sınıfın üye işlevine yönelik bir işaretçi `Type` .

*tarafta*\
**`const`** *Member_ptr* member işlevinin çağrıldığı nesne.

*Right*\
*Member_ptr*için verilen bağımsız değişken.

## <a name="return-value"></a>Dönüş Değeri

Uyarlanabilir bir ikili işlev.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, bir *member_ptr* `Type` özel üye nesnesinde, sınıfının üye işlevine bir işaretçi olması gereken member_ptr kopyasını depolar. Üye işlevini `operator()` iade olarak tanımlar `(left->member_ptr)(right) const` .

## <a name="example"></a>Örnek

Oluşturucusu `const_mem_fun1_t` nadiren doğrudan kullanılır. `mem_fn`üye işlevlerini uyarlamak için kullanılır. Üye işlev bağdaştırıcılarını nasıl kullanacağınızı gösteren bir örnek için bkz. [mem_fn](../standard-library/functional-functions.md#mem_fn) .
