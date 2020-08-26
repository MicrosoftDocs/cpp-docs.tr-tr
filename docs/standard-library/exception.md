---
title: '&lt;duruma&gt;'
ms.date: 11/04/2016
f1_keywords:
- <exception>
helpviewer_keywords:
- exception header
ms.assetid: 28900768-5dd7-4834-b907-5e37ab3407db
ms.openlocfilehash: 1533e8238b40f6ca5dc6faaef35a65db9020defd
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835975"
---
# <a name="ltexceptiongt"></a>&lt;duruma&gt;

Özel durumların işlenmesiyle ilgili çeşitli türleri ve işlevleri tanımlar. Özel durum işleme, sistemin bir hatadan kurtarılması durumlarında kullanılır. Bir işlevden programa döndürülecek denetim için bir yol sağlar. Özel durum işleme birleştirmesinin amacı düzenli bir şekilde bir hatadan kurtarılmasına olanak sağlayarak programın sağlamlığını artırmaktır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<exception>

**Ad alanı:** std

## <a name="members"></a>Üyeler

### <a name="typedefs"></a>Tür tanımları

|Ad|Açıklama|
|-|-|
|[exception_ptr](../standard-library/exception-typedefs.md#exception_ptr)|Bir özel duruma bir işaretçi tanımlayan tür.|
|[terminate_handler](../standard-library/exception-typedefs.md#terminate_handler)|Olarak kullanılmak üzere uygun bir işleve yönelik bir işaretçi tanımlayan tür `terminate_handler` .|
|[unexpected_handler](../standard-library/exception-typedefs.md#unexpected_handler)|Olarak kullanılmak üzere uygun bir işleve yönelik bir işaretçi tanımlayan tür `unexpected_handler` .|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|-|-|
|[current_exception](../standard-library/exception-functions.md#current_exception)|Geçerli özel durum için bir işaretçi alır.|
|[get_terminate](../standard-library/exception-functions.md#get_terminate)|Geçerli işlevi alır `terminate_handler` .|
|[get_unexpected](../standard-library/exception-functions.md#get_unexpected)|Geçerli işlevi alır `unexpected_handler` .|
|[make_exception_ptr](../standard-library/exception-functions.md#make_exception_ptr)|`exception_ptr`Bir özel durumun kopyasını tutan bir nesne oluşturur.|
|[rethrow_exception](../standard-library/exception-functions.md#rethrow_exception)|Bir parametre olarak geçirilen bir özel durum oluşturur.|
|[rethrow_if_nested](../standard-library/exception-functions.md#rethrow_if_nested)|İç içe ise özel durum atar ve oluşturur.|
|[set_terminate](../standard-library/exception-functions.md#set_terminate)|`terminate_handler`Programın sonlandırılması sırasında çağrılması için yeni bir oluşturur.|
|[set_unexpected](../standard-library/exception-functions.md#set_unexpected)|`unexpected_handler`Beklenmeyen bir özel durumla karşılaşıldığında yeni bir oluşturur.|
|[sonlandırmayı](../standard-library/exception-functions.md#terminate)|Bir sonlandırıcı işleyici çağırır.|
|[throw_with_nested](../standard-library/exception-functions.md#throw_with_nested)|İç içe ise özel durum oluşturur.|
|[uncaught_exception](../standard-library/exception-functions.md#uncaught_exception)|**`true`** Yalnızca oluşturulan bir özel durum şu anda işleniyorsa döndürür.|
|[bek](../standard-library/exception-functions.md#unexpected)|Beklenmeyen bir işleyici çağırır.|

### <a name="classes"></a>Sınıflar

|Ad|Açıklama|
|-|-|
|[bad_exception sınıfı](../standard-library/bad-exception-class.md)|Sınıfı, bir öğesinden oluşturulabilecek bir özel durumu açıklar `unexpected_handler` .|
|[özel durum sınıfı](../standard-library/exception-class.md)|Sınıfı, belirli ifadeler ve C++ standart kitaplığı tarafından oluşturulan tüm özel durumlar için temel sınıf olarak hizmet verir.|
|[nested_exception sınıfı](../standard-library/nested-exception-class.md)|Sınıfı, daha sonra kullanılmak üzere yakalanabilecek ve depolanabilecek bir özel durumu açıklar.|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
