---
title: '&lt;özel&gt; durum tür tanımları'
ms.date: 11/04/2016
f1_keywords:
- exception/std::exception_ptr
- exception/std::terminate_handler
- exception/std::unexpected_handler
ms.assetid: 2a338480-35e2-46f7-b223-52d4e84a5768
ms.openlocfilehash: 58fc19b7cdf9656a4c2978a43a5c77092cc6716d
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68917002"
---
# <a name="ltexceptiongt-typedefs"></a>&lt;özel&gt; durum tür tanımları

## <a name="exception_ptr"></a>exception_ptr

Bir özel duruma bir işaretçi tanımlayan tür.

```cpp
typedef unspecified exception_ptr;
```

### <a name="remarks"></a>Açıklamalar

`exception_ptr` Türü uygulamak için kullanılan belirtilmemiş bir iç sınıf.

Geçerli özel `exception_ptr` duruma veya Kullanıcı tarafından belirtilen özel durum örneğine başvurmak için bir nesne kullanın. Microsoft uygulamasında bir özel durum, bir [EXCEPTION_RECORD](/windows/desktop/api/winnt/ns-winnt-exception_record) yapısı tarafından temsil edilir. Her `exception_ptr` nesne, özel durumu temsil eden `EXCEPTION_RECORD` yapının bir kopyasına işaret eden bir özel durum başvurusu alanı içerir.

Bir `exception_ptr` değişken bildirdiğinizde, değişken herhangi bir özel durumla ilişkili değildir. Diğer bir deyişle, özel durum başvuru alanı NULL olur. Böyle bir nesne null exception_ptr olarak adlandırılır. `exception_ptr`

`current_exception` Bir `make_exception_ptr` nesneye özel durumatamakiçinorişlevinikullanın.`exception_ptr` Bir `exception_ptr` değişkene bir özel durum atadığınızda, değişkenin özel durum başvuru alanı özel durumun bir kopyasına işaret eder. Özel durumu kopyalamak için yeterli bellek yoksa, özel durum başvuru alanı bir [std:: bad_alloc](../standard-library/bad-alloc-class.md) özel durumunun kopyasına işaret eder. OR işlevi başka bir nedenle özel durumu kopyalayamayacağı takdirde `terminate` , işlev geçerli işlemden çıkmak için CRT işlevini çağırır. `make_exception_ptr` `current_exception`

Adına rağmen bir `exception_ptr` nesne bir işaretçi değildir. İşaretçi semantiğini etkilemez ve işaretçi üye erişimi ( `->`) veya yöneltme (*) işleçleri ile kullanılamaz. `exception_ptr` Nesnenin ortak veri üyeleri veya üye işlevleri yok.

**Karşılaştırmalar**

İki `!=` `==` nesneyikarşılaştırmakiçineşittir()veNot-eşit()işleçlerinikullanabilirsiniz.`exception_ptr` İşleçler, özel durumları temsil eden `EXCEPTION_RECORD` yapıların ikili değerini (bit düzeniyle) karşılaştırmaz. Bunun yerine, işleçler, `exception_ptr` nesnelerin özel durum başvurusu alanındaki adresleri karşılaştırır. Sonuç olarak, null `exception_ptr` ve null değeri eşit olarak karşılaştırılır.

## <a name="terminate_handler"></a>terminate_handler

Türü, olarak `terminate_handler`kullanım için uygun bir işleve yönelik bir işaretçi tanımlar.

```cpp
typedef void (*terminate_handler)();
```

### <a name="remarks"></a>Açıklamalar

Sonlandırıcı işleyici olarak kullanım için bir işleve işaretçi tanımlayan tür.

### <a name="example"></a>Örnek

Öğesinin`terminate_handler`kullanımına ilişkin bir örnek için bkz. [set_terminate](../standard-library/exception-functions.md#set_terminate) .

## <a name="unexpected_handler"></a>unexpected_handler

Türü, olarak `unexpected_handler`kullanım için uygun bir işleve yönelik bir işaretçi tanımlar.

```cpp
typedef void (*unexpected_handler)();
```

### <a name="example"></a>Örnek

Öğesinin`unexpected_handler`kullanımına ilişkin bir örnek için bkz. [set_unexpected](../standard-library/exception-functions.md#set_unexpected) .
