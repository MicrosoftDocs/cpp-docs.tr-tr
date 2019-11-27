---
title: noexcept (C++)
ms.date: 11/19/2019
f1_keywords:
- noexcept_cpp
ms.assetid: df24edb9-c6a6-4e37-9914-fd5c0c3716a8
ms.openlocfilehash: 5e8d58ed246b0143dc3d3be545cd796a4c3d60ed
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74245623"
---
# <a name="noexcept-c"></a>noexcept (C++)

**C++ 11:** Bir işlevin özel durum oluşturması gerekip gerekmediğini belirtir.

## <a name="syntax"></a>Sözdizimi

> *noexcept-ifadesi*: &nbsp;&nbsp;&nbsp;&nbsp;**noexcept** &nbsp;&nbsp;&nbsp;&nbsp;**noexcept (** *sabit ifade* **)**

### <a name="parameters"></a>Parametreler

*Sabit ifadesi*<br/>
**Bool** türünde bir sabit ifade, olası özel durum türleri kümesinin boş olup olmadığını temsil eder. Koşulsuz sürüm `noexcept(true)`eşdeğerdir.

## <a name="remarks"></a>Açıklamalar

*Noexcept ifadesi* bir tür *özel durum belirtimi*, bir işlevin dışında bir özel durum işleyicisi tarafından eşleştirilebilen bir tür kümesini temsil eden bir işlev bildirimine bir sonek. Birli koşullu işleç `noexcept(`*constant_expression*`)` *constant_expression* **doğru**ve koşulsuz eş anlamlı **noexcept**, bir işlevden çıkabileceği olası özel durum türleri kümesinin boş olduğunu belirtir. Diğer bir deyişle, işlev hiçbir şekilde özel durum oluşturmaz ve bir özel durumun kapsam dışına yayılmasın. `noexcept(`işleci, *constant_expression* **false değeri**veren veya bir özel durum belirtiminin (yıkıcı veya ayırmayı kaldırma işlevi dışında) yokluğunun`)` *constant_expression* , işlevden çıkabileceği olası özel durumların kümesinin tüm türler kümesidir.

Bir işlevi yalnızca, çağrı yaptığı tüm işlevlerin (doğrudan veya dolaylı olarak) **noexcept** ya da **const**olması durumunda **noexcept** olarak işaretleyin. Derleyici, **noexcept** işlevine kadar kabarcık olabilecek özel durumlar için her kod yolunu denetlemez. Bir özel durum `noexcept`işaretli bir işlevin dış kapsamından çıktıklarında, [std:: Terminate](../standard-library/exception-functions.md#terminate) hemen çağrılır ve kapsam içi nesnelerin yok edicilerin çağrılacağını garanti etmez. Standart olarak kullanım dışı olan dinamik özel durum tanımlayıcısı `throw()`yerine **noexcept** kullanın. Çağrı yığınını yaymak için bir özel duruma izin vermebir işleve `noexcept` uygulamanızı öneririz. Bir işlev **noexcept**olarak bildirildiğinde, derleyicinin birkaç farklı bağlamda daha verimli kod oluşturmasını sağlar. Daha fazla bilgi için bkz. [özel durum belirtimleri](exception-specifications-throw-cpp.md).

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

[Özel C++ durumlar ve hata işleme için modern en iyi uygulamalar](errors-and-exception-handling-modern-cpp.md)<br/>
[Özel durum belirtimleri (throw, noexcept)](exception-specifications-throw-cpp.md)