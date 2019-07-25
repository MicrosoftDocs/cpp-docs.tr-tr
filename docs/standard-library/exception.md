---
title: '&lt;duruma&gt;'
ms.date: 11/04/2016
f1_keywords:
- <exception>
helpviewer_keywords:
- exception header
ms.assetid: 28900768-5dd7-4834-b907-5e37ab3407db
ms.openlocfilehash: 681baee5ac5d19e8b3ffdf37c37599c9cb68f253
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457910"
---
# <a name="ltexceptiongt"></a>&lt;duruma&gt;

Özel durumların işlenmesiyle ilgili çeşitli türleri ve işlevleri tanımlar. Özel durum işleme, sistemin bir hatadan kurtarılması durumlarında kullanılır. Bir işlevden programa döndürülecek denetim için bir yol sağlar. Özel durum işleme birleştirmesinin amacı düzenli bir şekilde bir hatadan kurtarılmasına olanak sağlayarak programın sağlamlığını artırmaktır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<özel durum >

**Ad alanı:** std

## <a name="members"></a>Üyeler

### <a name="typedefs"></a>Tür tanımları

|||
|-|-|
|[exception_ptr](../standard-library/exception-typedefs.md#exception_ptr)|Bir özel duruma bir işaretçi tanımlayan tür.|
|[terminate_handler](../standard-library/exception-typedefs.md#terminate_handler)|Olarak kullanılmak üzere uygun bir işleve yönelik bir işaretçi tanımlayan tür `terminate_handler`.|
|[unexpected_handler](../standard-library/exception-typedefs.md#unexpected_handler)|Olarak kullanılmak üzere uygun bir işleve yönelik bir işaretçi tanımlayan tür `unexpected_handler`.|

### <a name="functions"></a>İşlevler

|||
|-|-|
|[current_exception](../standard-library/exception-functions.md#current_exception)|Geçerli özel durum için bir işaretçi alır.|
|[get_terminate](../standard-library/exception-functions.md#get_terminate)|Geçerli `terminate_handler` işlevi alır.|
|[get_unexpected](../standard-library/exception-functions.md#get_unexpected)|Geçerli `unexpected_handler` işlevi alır.|
|[make_exception_ptr](../standard-library/exception-functions.md#make_exception_ptr)|Bir özel `exception_ptr` durumun kopyasını tutan bir nesne oluşturur.|
|[rethrow_exception](../standard-library/exception-functions.md#rethrow_exception)|Bir parametre olarak geçirilen bir özel durum oluşturur.|
|[rethrow_if_nested](../standard-library/exception-functions.md#rethrow_if_nested)|İç içe ise özel durum atar ve oluşturur.|
|[set_terminate](../standard-library/exception-functions.md#set_terminate)|Programın sonlandırılması sırasında `terminate_handler` çağrılması için yeni bir oluşturur.|
|[set_unexpected](../standard-library/exception-functions.md#set_unexpected)|Beklenmeyen bir özel `unexpected_handler` durumla karşılaşıldığında yeni bir oluşturur.|
|[sonlandırmayı](../standard-library/exception-functions.md#terminate)|Bir sonlandırıcı işleyici çağırır.|
|[throw_with_nested](../standard-library/exception-functions.md#throw_with_nested)|İç içe ise özel durum oluşturur.|
|[uncaught_exception](../standard-library/exception-functions.md#uncaught_exception)|Yalnızca oluşturulan bir özel durum şu anda işleniyorsa **true** değerini döndürür.|
|[bek](../standard-library/exception-functions.md#unexpected)|Beklenmeyen bir işleyici çağırır.|

### <a name="classes"></a>Sınıflar

|||
|-|-|
|[bad_exception Sınıfı](../standard-library/bad-exception-class.md)|Sınıfı, bir `unexpected_handler`öğesinden oluşturulabilecek bir özel durumu açıklar.|
|[exception Sınıfı](../standard-library/exception-class.md)|Sınıfı, belirli ifadeler ve C++ standart kitaplık tarafından oluşturulan tüm özel durumlar için temel sınıf olarak hizmet verir.|
|[nested_exception sınıfı](../standard-library/nested-exception-class.md)|Sınıfı, daha sonra kullanılmak üzere yakalanabilecek ve depolanabilecek bir özel durumu açıklar.|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
