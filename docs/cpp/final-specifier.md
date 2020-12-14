---
description: 'Daha fazla bilgi edinin: son tanımlayıcı'
title: final Tanımlayıcısı
ms.date: 11/04/2016
f1_keywords:
- final_CPP
helpviewer_keywords:
- final Identifier
ms.assetid: 649866d0-79d4-449f-ab74-f84b911b79a3
ms.openlocfilehash: 5fd6ee3c23a455c4316593cc089c26c34477709d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242619"
---
# <a name="final-specifier"></a>final Tanımlayıcısı

Türetilmiş bir sınıfta geçersiz kılınamayan sanal işlevleri belirlemek için **final** anahtar sözcüğünü kullanabilirsiniz. Ayrıca devralınamaz sınıflar aramak için de onu kullanabilirsiniz.

## <a name="syntax"></a>Syntax

```
function-declaration final;
class class-name final base-classes
```

## <a name="remarks"></a>Açıklamalar

**final** , bağlama duyarlıdır ve yalnızca bir işlev bildirimi veya sınıf adından sonra kullanıldığında özel anlamı vardır; Aksi takdirde, ayrılmış bir anahtar sözcük değildir.

Sınıf bildirimlerinde **final** kullanıldığında, `base-classes` bildirimin isteğe bağlı bir parçasıdır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir sanal işlevin geçersiz kılınamadığını belirtmek için **final** anahtar sözcüğünü kullanır.

```cpp
class BaseClass
{
    virtual void func() final;
};

class DerivedClass: public BaseClass
{
    virtual void func(); // compiler error: attempting to
                         // override a final function
};
```

Üye işlevlerinin geçersiz kılınabileceğini belirtme hakkında bilgi için bkz. [geçersiz kılma belirticisi](../cpp/override-specifier.md).

Sonraki örnek, bir sınıfın devralınamayacağını belirtmek için **final** anahtar sözcüğünü kullanır.

```cpp
class BaseClass final
{
};

class DerivedClass: public BaseClass // compiler error: BaseClass is
                                     // marked as non-inheritable
{
};
```

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[geçersiz kılma belirticisi](../cpp/override-specifier.md)
