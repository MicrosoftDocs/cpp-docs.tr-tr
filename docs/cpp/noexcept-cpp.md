---
title: noexcept (C++)
ms.date: 11/19/2019
f1_keywords:
- noexcept_cpp
ms.assetid: df24edb9-c6a6-4e37-9914-fd5c0c3716a8
ms.openlocfilehash: efb5ad272c8857e7a0dbd2c75885b826f2b8b9f8
ms.sourcegitcommit: 6b749db14b4cf3a2b8d581fda6fdd8cb98bc3207
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82825370"
---
# <a name="noexcept-c"></a>noexcept (C++)

**C++ 11:** Bir işlevin özel durum oluşturması gerekip gerekmediğini belirtir.

## <a name="syntax"></a>Sözdizimi

> *noexcept-ifadesi*: \
> &nbsp;&nbsp;&nbsp;&nbsp;**noexcept**\
> &nbsp;&nbsp;&nbsp;&nbsp;**noexcept (** *sabit ifadesi* **)**

### <a name="parameters"></a>Parametreler

*Sabit ifadesi*<br/>
**Bool** türünde bir sabit ifade, olası özel durum türleri kümesinin boş olup olmadığını temsil eder. Koşulsuz sürüm ile `noexcept(true)`eşdeğerdir.

## <a name="remarks"></a>Açıklamalar

*Noexcept ifadesi* bir tür *özel durum belirtimi*, bir işlevin dışında bir özel durum işleyicisi tarafından eşleştirilebilen bir tür kümesini temsil eden bir işlev bildirimine bir sonek. Birli koşullu operatör `noexcept(`, *constant_expression* **doğru**bir şekilde oluşturulduğu ve koşulsuz eş anlamlı **noexcept** *constant_expression* `)` , bir işlevden çıkabileceği olası özel durum türleri kümesinin boş olduğunu belirtir. Diğer bir deyişle, işlev hiçbir şekilde özel durum oluşturmaz ve bir özel durumun kapsam dışına yayılmasın. `noexcept(`İşleci, *constant_expression* **yanlış**veya bir özel durum belirtiminin (yıkıcı veya ayırmayı kaldırma işlevi dışında) yokluğunda *constant_expression* `)` , işlevden çıkabileceği olası özel durumların kümesinin tüm türler kümesi olduğunu gösterir.

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

[Özel durumlar ve hata işleme için modern C++ en iyi uygulamaları](errors-and-exception-handling-modern-cpp.md)<br/>
[Özel durum belirtimleri (throw, noexcept)](exception-specifications-throw-cpp.md)
