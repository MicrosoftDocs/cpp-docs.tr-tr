---
description: 'Hakkında daha fazla bilgi edinin: mem_fun_ref_t sınıfı'
title: mem_fun_ref_t Sınıfı
ms.date: 02/21/2019
f1_keywords:
- functional/std::mem_fun_ref_t
helpviewer_keywords:
- mem_fun_ref_t class
ms.assetid: 7dadcac3-8d33-4e4b-a792-81bd53d3df39
ms.openlocfilehash: e79d7f3b3271ff699f0dd2ad760753c2162d554a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149181"
---
# <a name="mem_fun_ref_t-class"></a>mem_fun_ref_t Sınıfı

`non_const`Bir başvuru bağımsız değişkeniyle başlatıldığında bir birli işlev nesnesi olarak çağrılması için bağımsız değişken alan bir üye işlevine izin veren bir bağdaştırıcı sınıfı. C++ 11 ' de kullanım dışı bırakılmıştır ve C++ 17 ' de kaldırılmıştır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Result, class Type>
class mem_fun_ref_t : public unary_function<Type, Result> {
    explicit mem_fun_ref_t(
    Result (Type::* _Pm)());

    Result operator()(Type& left) const;
};
```

### <a name="parameters"></a>Parametreler

*_Pm*\
İşlev nesnesine dönüştürülecek sınıfın üye işlevine yönelik bir işaretçi `Type` .

*tarafta*\
*_Pm* member işlevinin çağrıldığı nesne.

## <a name="return-value"></a>Dönüş Değeri

Uyarlanabilir bir birli işlev.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, bir  `Type` özel üye nesnesinde, sınıfının üye işlevine bir işaretçi olması gereken _Pm kopyasını depolar. Üye işlevini `operator()` döndüren (**Left**. * `_Pm` ) () olarak tanımlar.

## <a name="example"></a>Örnek

Oluşturucusu `mem_fun_ref_t` genellikle doğrudan kullanılmaz; yardımcı işlevi `mem_fun_ref` üye işlevlerini uyarlamak için kullanılır. Üye işlev bağdaştırıcılarını nasıl kullanacağınızı gösteren bir örnek için bkz. [mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref) .
