---
title: noexcept (C++)
ms.date: 01/12/2018
f1_keywords:
- noexcept_cpp
ms.assetid: df24edb9-c6a6-4e37-9914-fd5c0c3716a8
ms.openlocfilehash: cf53aca918e36d18ab7f8aa14b01caaf0e55627c
ms.sourcegitcommit: ace42fa67e704d56d03c03745b0b17d2a5afeba4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69975895"
---
# <a name="noexcept-c"></a>noexcept (C++)

**C++ 11:** Bir işlevin özel durum oluşturması gerekip gerekmediğini belirtir.

## <a name="syntax"></a>Sözdizimi

> *noexcept-ifadesi*: &nbsp; &nbsp; &nbsp; **noexcept** noexcept (Sabitifadesi&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  **)**

### <a name="parameters"></a>Parametreler

*constant-expression*<br/>
**Bool** türünde bir sabit ifade, olası özel durum türleri kümesinin boş olup olmadığını temsil eder. Koşulsuz sürüm ile `noexcept(true)`eşdeğerdir.

## <a name="remarks"></a>Açıklamalar

*Noexcept ifadesi* bir tür *özel durum belirtimi*, bir işlevin dışında bir özel durum işleyicisi tarafından eşleştirilebilen bir tür kümesini temsil eden bir işlev bildirimine bir sonek. Birli koşullu operatör `noexcept(` *constant_expression* `)` , *constant_expression* **true**, ve koşulsuz eş anlamlı **noexcept**, bir işlevden çıkabilir boş olabilir. Diğer bir deyişle, işlev hiçbir şekilde özel durum oluşturmaz ve bir özel durumun kapsam dışına yayılmasın. `noexcept(` Constant_expressionişleci`)` , constant_expression **false**olarak ya da bir özel durum belirtiminin (yıkıcı veya ayırmayı kaldırma işlevi dışında) yokluğunda olduğunu gösterir. işlevin çıkabileceği olası özel durumlar kümesi, tüm türlerin kümesidir.

Bir işlevi yalnızca, çağrı yaptığı tüm işlevlerin (doğrudan veya dolaylı olarak) **noexcept** ya da **const**olması durumunda **noexcept** olarak işaretleyin. Derleyici, **noexcept** işlevine kadar kabarcık olabilecek özel durumlar için her kod yolunu denetlemez. Bir özel durum işaretli `noexcept`bir işlevin dış kapsamından çıktıklarında, [std:: Terminate](../standard-library/exception-functions.md#terminate) hemen çağrılır ve kapsam içi nesnelerin yok edicilerin çağrılacağını garanti etmez. Artık standart olarak kullanım dışı olan dinamik özel durum `throw()`tanımlayıcısı yerine **noexcept** kullanın. Çağrı yığınını yaymaya `noexcept` özel bir duruma izin veren herhangi bir işlev için uygulamanızı öneririz. Bir işlev **noexcept**olarak bildirildiğinde, derleyicinin birkaç farklı bağlamda daha verimli kod oluşturmasını sağlar. Daha fazla bilgi için bkz. [özel durum belirtimleri](exception-specifications-throw-cpp.md).

## <a name="example"></a>Örnek

Bağımsız değişkenini kopyalayan bir şablon işlevi, kopyalandığı nesnenin düz bir eski veri türü (POD) olduğu koşul **dışında noexcept** olarak bildirilemez. Böyle bir işlev şöyle bildirilebilecek:

```cpp
#include <type_traits>

template <typename T>
T copy_object(const T& obj) noexcept(std::is_pod<T>)
{
   // ...
}
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ Özel Durum İşleme](cpp-exception-handling.md)<br/>
[Özel durum belirtimleri (throw, noexcept)](exception-specifications-throw-cpp.md)