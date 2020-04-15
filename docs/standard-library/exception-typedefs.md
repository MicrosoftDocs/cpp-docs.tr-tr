---
title: '&lt;özel&gt; durum typedefs'
ms.date: 11/04/2016
f1_keywords:
- exception/std::exception_ptr
- exception/std::terminate_handler
- exception/std::unexpected_handler
ms.assetid: 2a338480-35e2-46f7-b223-52d4e84a5768
ms.openlocfilehash: f71c03e0c0a2e7ea4f37a85e85628ccf630ea317
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368730"
---
# <a name="ltexceptiongt-typedefs"></a>&lt;özel&gt; durum typedefs

## <a name="exception_ptr"></a><a name="exception_ptr"></a>exception_ptr

Bir özel duruma bir işaretçi tanımlayan tür.

```cpp
typedef unspecified exception_ptr;
```

### <a name="remarks"></a>Açıklamalar

`exception_ptr` Türü uygulamak için kullanılan belirtilmemiş bir iç sınıf.

Geçerli `exception_ptr` özel durum veya kullanıcı tarafından belirtilen özel durum örneğine başvurmak için bir nesne kullanın. Microsoft uygulamasında, bir özel durum [EXCEPTION_RECORD](/windows/win32/api/winnt/ns-winnt-exception_record) bir yapı tarafından temsil edilir. Her `exception_ptr` nesne, özel durumu temsil eden yapının `EXCEPTION_RECORD` bir kopyasını işaret eden bir özel durum başvuru alanı içerir.

Bir değişkenil `exception_ptr` olarak beyan ettiğinizde, değişken herhangi bir özel durumla ilişkili değildir. Diğer bir deyişle, özel durum başvuru alanı NULL olur. Böyle `exception_ptr` bir nesneye *null exception_ptr*denir.

Bir `exception_ptr` `current_exception` nesneye özel durum atamak için veya `make_exception_ptr` işlevi kullanın. Bir `exception_ptr` değişkene bir özel durum atadığınızda, değişkenin özel durum başvuru alanı özel durum bir kopyasını gösterir. Özel durumu kopyalamak için yeterli bellek yoksa, özel durum başvuru alanı std bir kopyasını [işaret::bad_alloc](../standard-library/bad-alloc-class.md) özel durum. İşlev `current_exception` `make_exception_ptr` başka bir nedenle özel durumu kopyalayamıyorsa, işlev geçerli işlemden çıkmak için `terminate` CRT işlevini çağırır.

Adına rağmen, `exception_ptr` bir nesnenin kendisi bir işaretçi değildir. İşaretçi semantikine uymaz ve işaretçi üye `->`erişimi ( ) veya indirection (*) işleçleri ile kullanılamaz. Nesnenin `exception_ptr` ortak veri üyesi veya üye işlevi yoktur.

**Karşılaştırma:**

İki `exception_ptr` nesneyi karşılaştırmak için eşit `!=`( ) `==`ve eşit olmayan ( ) işleçleri kullanabilirsiniz. İşleçler, özel durumları temsil eden `EXCEPTION_RECORD` yapıların ikili değerini (bit deseni) karşılaştırmaz. Bunun yerine, işleçler nesnelerin özel durum `exception_ptr` başvuru alanında adresleri karşılaştırın. Sonuç olarak, `exception_ptr` null ve NULL değeri eşit olarak karşılaştırın.

## <a name="terminate_handler"></a><a name="terminate_handler"></a>terminate_handler

Tür, bir işleviçin bir işaretçi `terminate_handler`açıklar .

```cpp
typedef void (*terminate_handler)();
```

### <a name="remarks"></a>Açıklamalar

Sonlandırıcı işleyici olarak kullanım için bir işleve işaretçi tanımlayan tür.

### <a name="example"></a>Örnek

Bkz. [set_terminate.](../standard-library/exception-functions.md#set_terminate) `terminate_handler`

## <a name="unexpected_handler"></a><a name="unexpected_handler"></a>unexpected_handler

Tür, bir işleviçin işaretçi olarak `unexpected_handler`kullanılmak üzere uygun açıklar.

```cpp
typedef void (*unexpected_handler)();
```

### <a name="example"></a>Örnek

Kullanımı [set_unexpected](../standard-library/exception-functions.md#set_unexpected) nın bir örneği için `unexpected_handler`set_unexpected bakın.
