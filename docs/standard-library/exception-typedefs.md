---
title: '&lt;özel durum&gt; tür tanımları'
ms.date: 11/04/2016
f1_keywords:
- exception/std::exception_ptr
- exception/std::terminate_handler
- exception/std::unexpected_handler
ms.assetid: 2a338480-35e2-46f7-b223-52d4e84a5768
ms.openlocfilehash: e3904393096422a8986414a253d515342c7382f0
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68246039"
---
# <a name="ltexceptiongt-typedefs"></a>&lt;özel durum&gt; tür tanımları

## <a name="exception_ptr"></a>  exception_ptr

Bir özel duruma bir işaretçi tanımlayan tür.

```cpp
typedef unspecified exception_ptr;
```

### <a name="remarks"></a>Açıklamalar

Uygulamak için kullanılan belirtilmemiş bir iç sınıf `exception_ptr` türü.

Kullanım bir `exception_ptr` geçerli özel durumu veya bir kullanıcı tarafından belirtilen özel durum örneği başvurmak için nesne. Microsoft uygulamasında, bir özel durum tarafından temsil edilen bir [exceptıon_record](/windows/desktop/api/winnt/ns-winnt-_exception_record) yapısı. Her `exception_ptr` nesne içeren bir kopyasına işaret eden bir özel durum başvuru alanı `EXCEPTION_RECORD` özel durumu temsil eden yapısı.

Bildirdiğinizde bir `exception_ptr` değişken, değişken herhangi bir özel durumla ilişkili değil. Diğer bir deyişle, özel durum başvuru alanı NULL olur. Böyle bir `exception_ptr` nesnesinin bir *null exception_ptr*.

Kullanım `current_exception` veya `make_exception_ptr` işlevi için bir özel durum atamak için bir `exception_ptr` nesne. Bir özel durum atadığınızda bir `exception_ptr` değişken, değişkenin özel durum başvuru alanı özel durumun kopyasını gösterir. Özel durum başvuru alanı özel durumu kopyalamak için yeterli bellek varsa, bir kopyasına işaret eden bir [std::bad_alloc](../standard-library/bad-alloc-class.md) özel durum. Varsa `current_exception` veya `make_exception_ptr` işlevi, özel durumun başka bir nedenle, işlev çağrıları kopyalayamıyor `terminate` CRT işlevini geçerli işlemden çıkmak için.

Adına rağmen bir `exception_ptr` nesnesinin kendisi bir işaretçi değildir. İşaretçi semantiğine uymaz ve işaretçi üye erişimi ile birlikte kullanılamaz ( `->`) veya yöneltme (*) işleçleri. `exception_ptr` Nesnenin ortak veri üyeleri ya da üye işlevleri vardır.

**Karşılaştırma:**

Eşit kullanabilirsiniz ( `==`) ve eşit değil ( `!=`) karşılaştırmak için işleçleri `exception_ptr` nesneleri. İşleçler ikili değerini (bit deseni) karşılaştırın değil `EXCEPTION_RECORD` özel durumları temsil eden yapılar. Bunun yerine, işleçler özel durum başvuru alanlarındaki adresleri karşılaştırır `exception_ptr` nesneleri. Sonuç olarak, bir null `exception_ptr` ve NULL değeri eşit olarak karşılaştırılır.

## <a name="terminate_handler"></a> terminate_handler

Türü olarak kullanmak için uygun bir işleve işaretçi tanımlayan bir `terminate_handler`.

```cpp
typedef void (*terminate_handler)();
```

### <a name="remarks"></a>Açıklamalar

Sonlandırıcı işleyici olarak kullanım için bir işleve işaretçi tanımlayan tür.

### <a name="example"></a>Örnek

Bkz: [set_terminate](../standard-library/exception-functions.md#set_terminate) kullanımına ilişkin bir örnek `terminate_handler`.

## <a name="unexpected_handler"></a> unexpected_handler

Türü olarak kullanmak için uygun bir işleve işaretçi tanımlayan bir `unexpected_handler`.

```cpp
typedef void (*unexpected_handler)();
```

### <a name="example"></a>Örnek

Bkz: [set_unexpected](../standard-library/exception-functions.md#set_unexpected) kullanımına ilişkin bir örnek `unexpected_handler`.
