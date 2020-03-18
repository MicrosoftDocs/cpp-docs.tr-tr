---
title: '&lt;özel durum&gt; tür tanımları'
ms.date: 11/04/2016
f1_keywords:
- exception/std::exception_ptr
- exception/std::terminate_handler
- exception/std::unexpected_handler
ms.assetid: 2a338480-35e2-46f7-b223-52d4e84a5768
ms.openlocfilehash: aba17b7bf052b6974bf849f60ff895b8e84a1092
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79421851"
---
# <a name="ltexceptiongt-typedefs"></a>&lt;özel durum&gt; tür tanımları

## <a name="exception_ptr"></a>exception_ptr

Bir özel duruma bir işaretçi tanımlayan tür.

```cpp
typedef unspecified exception_ptr;
```

### <a name="remarks"></a>Açıklamalar

`exception_ptr` türünü uygulamak için kullanılan belirtilmemiş bir iç sınıf.

Geçerli özel duruma veya Kullanıcı tarafından belirtilen özel durum örneğine başvurmak için bir `exception_ptr` nesnesi kullanın. Microsoft uygulamasında bir özel durum [EXCEPTION_RECORD](/windows/win32/api/winnt/ns-winnt-exception_record) yapısıyla temsil edilir. Her `exception_ptr` nesnesi, özel durumu temsil eden `EXCEPTION_RECORD` yapısının bir kopyasına işaret eden bir özel durum başvurusu alanı içerir.

Bir `exception_ptr` değişkeni bildirdiğinizde, değişken herhangi bir özel durumla ilişkili değildir. Diğer bir deyişle, özel durum başvuru alanı NULL olur. Böyle bir `exception_ptr` nesnesine *null exception_ptr*denir.

Bir `exception_ptr` nesnesine özel durum atamak için `current_exception` veya `make_exception_ptr` işlevini kullanın. Bir `exception_ptr` değişkenine bir özel durum atadığınızda, değişkenin özel durum başvuru alanı özel durumun bir kopyasına işaret eder. Özel durumu kopyalamak için yeterli bellek yoksa, özel durum başvuru alanı bir [std:: bad_alloc](../standard-library/bad-alloc-class.md) özel durumunun kopyasına işaret eder. `current_exception` veya `make_exception_ptr` işlevi başka bir nedenle özel durumu kopyalayamayacağı takdirde, işlev geçerli işlemden çıkmak için `terminate` CRT işlevini çağırır.

Adına rağmen, bir `exception_ptr` nesnesi kendisi bir işaretçi değildir. İşaretçi semantiğini etkilemez ve işaretçi üye erişimi (`->`) veya yöneltme (*) işleçleri ile kullanılamaz. `exception_ptr` nesnenin ortak veri üyeleri veya üye işlevleri yok.

**Karşılaştırmalar**

İki `exception_ptr` nesnesini karşılaştırmak için eşittir (`==`) ve Not-eşit (`!=`) işleçlerini kullanabilirsiniz. İşleçler, özel durumları temsil eden `EXCEPTION_RECORD` yapılarının ikili değerini (bit düzeniyle) karşılaştırmaz. Bunun yerine, işleçler `exception_ptr` nesnelerinin özel durum başvurusu alanındaki adresleri karşılaştırır. Sonuç olarak, null `exception_ptr` ve NULL değeri eşit olarak karşılaştırılmaktadır.

## <a name="terminate_handler"></a>terminate_handler

Tür, `terminate_handler`olarak kullanım için uygun bir işleve yönelik bir işaretçi tanımlar.

```cpp
typedef void (*terminate_handler)();
```

### <a name="remarks"></a>Açıklamalar

Sonlandırıcı işleyici olarak kullanım için bir işleve işaretçi tanımlayan tür.

### <a name="example"></a>Örnek

`terminate_handler`kullanımına ilişkin bir örnek için bkz. [set_terminate](../standard-library/exception-functions.md#set_terminate) .

## <a name="unexpected_handler"></a>unexpected_handler

Tür, `unexpected_handler`olarak kullanım için uygun bir işleve yönelik bir işaretçi tanımlar.

```cpp
typedef void (*unexpected_handler)();
```

### <a name="example"></a>Örnek

`unexpected_handler`kullanımına ilişkin bir örnek için bkz. [set_unexpected](../standard-library/exception-functions.md#set_unexpected) .
