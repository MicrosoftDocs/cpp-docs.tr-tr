---
description: 'Hakkında daha fazla bilgi edinin: noexcept (C++)'
title: noexcept (C++)
ms.date: 11/19/2019
f1_keywords:
- noexcept_cpp
ms.assetid: df24edb9-c6a6-4e37-9914-fd5c0c3716a8
ms.openlocfilehash: ca4abfc48e3850f014c29cea2fd9108f7b556072
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223730"
---
# <a name="noexcept-c"></a>noexcept (C++)

**C++ 11:** Bir işlevin özel durum oluşturması gerekip gerekmediğini belirtir.

## <a name="syntax"></a>Syntax

> *noexcept-ifadesi*: \
> &nbsp;&nbsp;&nbsp;&nbsp;**`noexcept`**\
> &nbsp;&nbsp;&nbsp;&nbsp;**noexcept (** *sabit ifadesi* **)**

### <a name="parameters"></a>Parametreler

*Sabit ifadesi*<br/>
**`bool`** Olası özel durum türleri kümesinin boş olup olmadığını temsil eden türünün sabit bir ifadesi. Koşulsuz sürüm ile eşdeğerdir `noexcept(true)` .

## <a name="remarks"></a>Açıklamalar

*Noexcept ifadesi* bir tür *özel durum belirtimi*, bir işlevin dışında bir özel durum işleyicisi tarafından eşleştirilebilen bir tür kümesini temsil eden bir işlev bildirimine bir sonek. Birli koşullu operatör `noexcept(`  `)` , *constant_expression* constant_expression **`true`** ve koşulsuz eşanlamlısını, **`noexcept`** bir işlevden çıkabileceği olası özel durum türleri kümesinin boş olduğunu belirtir. Diğer bir deyişle, işlev hiçbir şekilde özel durum oluşturmaz ve bir özel durumun kapsam dışına yayılmasın. İşleci `noexcept(`  `)` *constant_expression* **`false`** veya bir özel durum belirtiminin (yıkıcı veya ayırmayı kaldırma işlevi dışında) yokluğu constant_expression, işlevden çıkabileceği olası özel durumların kümesinin tüm türler kümesi olduğunu gösterir.

Bir işlevi yalnızca, **`noexcept`** çağrı yaptığı tüm işlevler, doğrudan veya dolaylı olarak, ya da olarak işaretleyin **`noexcept`** **`const`** . Derleyici, bir işleve kadar kabarcık olabilecek özel durumlar için her kod yolunu denetlemez **`noexcept`** . Bir özel durum işaretli bir işlevin dış kapsamından çıktıklarında **`noexcept`** , [std:: Terminate](../standard-library/exception-functions.md#terminate) hemen çağrılır ve kapsam içi nesnelerin yok edicilerin çağrılacağını garanti etmez. **`noexcept`** `throw()` Artık standart olarak kullanım dışı olan dinamik özel durum belirleyicisi yerine kullanın. **`noexcept`** Çağrı yığınını yaymaya özel bir duruma izin veren herhangi bir işlev için uygulamanızı öneririz. Bir işlev bildirildiğinde **`noexcept`** derleyicinin birçok farklı bağlamda daha verimli kod oluşturmasını sağlar. Daha fazla bilgi için bkz. [özel durum belirtimleri](exception-specifications-throw-cpp.md).

## <a name="example"></a>Örnek

Bağımsız değişkenini kopyalayan bir şablon işlevi, **`noexcept`** kopyalandığı nesnenin bir düz eski veri türü (pod) olduğu koşulda bildirilemez. Böyle bir işlev şöyle bildirilebilecek:

```cpp
#include <type_traits>

template <typename T>
T copy_object(const T& obj) noexcept(std::is_pod<T>)
{
   // ...
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Özel durumlar ve hata işleme için modern C++ en iyi uygulamaları](errors-and-exception-handling-modern-cpp.md)<br/>
[Özel durum belirtimleri (throw, noexcept)](exception-specifications-throw-cpp.md)
