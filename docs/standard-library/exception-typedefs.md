---
description: 'Daha fazla bilgi edinin: &lt; özel durum &gt; tür tanımları'
title: '&lt;özel durum &gt; tür tanımları'
ms.date: 11/04/2016
f1_keywords:
- exception/std::exception_ptr
- exception/std::terminate_handler
- exception/std::unexpected_handler
ms.assetid: 2a338480-35e2-46f7-b223-52d4e84a5768
ms.openlocfilehash: 5df3f49a66cced171d96c2dedad7b239535519a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324535"
---
# <a name="ltexceptiongt-typedefs"></a>&lt;özel durum &gt; tür tanımları

## <a name="exception_ptr"></a><a name="exception_ptr"></a> exception_ptr

Bir özel duruma bir işaretçi tanımlayan tür.

```cpp
typedef unspecified exception_ptr;
```

### <a name="remarks"></a>Açıklamalar

Türü uygulamak için kullanılan belirtilmemiş bir iç sınıf `exception_ptr` .

`exception_ptr`Geçerli özel duruma veya Kullanıcı tarafından belirtilen özel durum örneğine başvurmak için bir nesne kullanın. Microsoft uygulamasında bir özel durum [EXCEPTION_RECORD](/windows/win32/api/winnt/ns-winnt-exception_record) yapısıyla temsil edilir. Her `exception_ptr` nesne `EXCEPTION_RECORD` , özel durumu temsil eden yapının bir kopyasına işaret eden bir özel durum başvurusu alanı içerir.

Bir `exception_ptr` değişken bildirdiğinizde, değişken herhangi bir özel durumla ilişkili değildir. Diğer bir deyişle, özel durum başvuru alanı NULL olur. Böyle bir `exception_ptr` nesne *null exception_ptr* olarak adlandırılır.

`current_exception` `make_exception_ptr` Bir nesneye özel durum atamak için or işlevini kullanın `exception_ptr` . Bir değişkene bir özel durum atadığınızda `exception_ptr` , değişkenin özel durum başvuru alanı özel durumun bir kopyasına işaret eder. Özel durumu kopyalamak için yeterli bellek yoksa, özel durum başvuru alanı bir [std:: bad_alloc](../standard-library/bad-alloc-class.md) özel durumunun kopyasına işaret eder. `current_exception`Or `make_exception_ptr` işlevi başka bir nedenle özel durumu kopyalayamayacağı takdirde, işlev `terminate` geçerli işlemden çıkmak için CRT işlevini çağırır.

Adına rağmen bir `exception_ptr` nesne bir işaretçi değildir. İşaretçi semantiğini etkilemez ve işaretçi üye erişimi ( `->` ) veya yöneltme (*) işleçleri ile kullanılamaz. `exception_ptr`Nesnenin ortak veri üyeleri veya üye işlevleri yok.

**Karşılaştırmalar**

`==`İki nesneyi karşılaştırmak için eşittir () ve Not-eşit ( `!=` ) işleçlerini kullanabilirsiniz `exception_ptr` . İşleçler, `EXCEPTION_RECORD` özel durumları temsil eden yapıların ikili değerini (bit düzeniyle) karşılaştırmaz. Bunun yerine, işleçler, nesnelerin özel durum başvurusu alanındaki adresleri karşılaştırır `exception_ptr` . Sonuç olarak, null `exception_ptr` ve null değeri eşit olarak karşılaştırılır.

## <a name="terminate_handler"></a><a name="terminate_handler"></a> terminate_handler

Türü, olarak kullanım için uygun bir işleve yönelik bir işaretçi tanımlar `terminate_handler` .

```cpp
typedef void (*terminate_handler)();
```

### <a name="remarks"></a>Açıklamalar

Sonlandırıcı işleyici olarak kullanım için bir işleve işaretçi tanımlayan tür.

### <a name="example"></a>Örnek

Öğesinin [](../standard-library/exception-functions.md#set_terminate) kullanımına ilişkin bir örnek için bkz. set_terminate `terminate_handler` .

## <a name="unexpected_handler"></a><a name="unexpected_handler"></a> unexpected_handler

Türü, olarak kullanım için uygun bir işleve yönelik bir işaretçi tanımlar `unexpected_handler` .

```cpp
typedef void (*unexpected_handler)();
```

### <a name="example"></a>Örnek

Öğesinin [](../standard-library/exception-functions.md#set_unexpected) kullanımına ilişkin bir örnek için bkz. set_unexpected `unexpected_handler` .
