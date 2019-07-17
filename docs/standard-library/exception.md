---
title: '&lt;özel durum&gt;'
ms.date: 11/04/2016
f1_keywords:
- <exception>
helpviewer_keywords:
- exception header
ms.assetid: 28900768-5dd7-4834-b907-5e37ab3407db
ms.openlocfilehash: 5036f2efc782c3b2f385960cd9cbf6935212f720
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68240762"
---
# <a name="ltexceptiongt"></a>&lt;özel durum&gt;

Özel durumların işlenmesiyle ilgili çeşitli türleri ve işlevleri tanımlar. Özel durum işleme, sistemin bir hatadan kurtarılması durumlarında kullanılır. Bir işlevden programa döndürülecek denetim için bir yol sağlar. Özel durum işleme birleştirmesinin amacı düzenli bir şekilde bir hatadan kurtarılmasına olanak sağlayarak programın sağlamlığını artırmaktır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<özel durum >

**Namespace:** std

## <a name="members"></a>Üyeler

### <a name="typedefs"></a>Tür tanımları

|||
|-|-|
|[exception_ptr](../standard-library/exception-typedefs.md#exception_ptr)|Bir özel duruma bir işaretçi tanımlayan tür.|
|[terminate_handler](../standard-library/exception-typedefs.md#terminate_handler)|İçin olarak kullanım için uygun bir işleve işaretçi tanımlayan tür bir `terminate_handler`.|
|[unexpected_handler](../standard-library/exception-typedefs.md#unexpected_handler)|İçin olarak kullanım için uygun bir işleve işaretçi tanımlayan tür bir `unexpected_handler`.|

### <a name="functions"></a>İşlevler

|||
|-|-|
|[current_exception](../standard-library/exception-functions.md#current_exception)|Geçerli özel durum için bir işaretçi alır.|
|[get_terminate](../standard-library/exception-functions.md#get_terminate)|Geçerli alır `terminate_handler` işlevi.|
|[get_unexpected](../standard-library/exception-functions.md#get_unexpected)|Geçerli alır `unexpected_handler` işlevi.|
|[make_exception_ptr](../standard-library/exception-functions.md#make_exception_ptr)|Oluşturur bir `exception_ptr` bir özel durumun kopyasını tutan nesne.|
|[rethrow_exception](../standard-library/exception-functions.md#rethrow_exception)|Bir parametre olarak geçirilen bir özel durum oluşturur.|
|[rethrow_if_nested](../standard-library/exception-functions.md#rethrow_if_nested)|Çevirir ve iç içe geçmiş özel durum oluşturur.|
|[set_terminate](../standard-library/exception-functions.md#set_terminate)|Yeni bir kurar `terminate_handler` program sonlandırıldığında çağrılabilir.|
|[set_unexpected](../standard-library/exception-functions.md#set_unexpected)|Yeni bir kurar `unexpected_handler` olacak şekilde, beklenmeyen bir özel durumla karşılaştı.|
|[sonlandırma](../standard-library/exception-functions.md#terminate)|Bir sonlandırıcı işleyici çağırır.|
|[throw_with_nested](../standard-library/exception-functions.md#throw_with_nested)|İç içe geçmiş özel durum oluşturur.|
|[uncaught_exception](../standard-library/exception-functions.md#uncaught_exception)|Döndürür **true** yalnızca oluşan bir özel durum şu anda işleniyorsa.|
|[beklenmeyen](../standard-library/exception-functions.md#unexpected)|Beklenmeyen bir işleyici çağırır.|

### <a name="classes"></a>Sınıflar

|||
|-|-|
|[bad_exception Sınıfı](../standard-library/bad-exception-class.md)|Öğesinden oluşturulan bir özel durum sınıfı açıklar bir `unexpected_handler`.|
|[exception Sınıfı](../standard-library/exception-class.md)|Sınıfı, belirli ifadeler ve C++ Standart Kitaplığı tarafından oluşturulan tüm özel durumlar için temel sınıf olarak hizmet verir.|
|[nested_exception sınıfı](../standard-library/nested-exception-class.md)|Yakalanan ve daha sonra kullanmak üzere depolanan bir özel durum sınıfı açıklar.|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
