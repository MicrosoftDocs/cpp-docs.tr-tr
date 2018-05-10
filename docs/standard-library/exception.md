---
title: '&lt;özel durum&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <exception>
dev_langs:
- C++
helpviewer_keywords:
- exception header
ms.assetid: 28900768-5dd7-4834-b907-5e37ab3407db
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bbd57085225bb21b9f7ce8bd34c537d3bc414797
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="ltexceptiongt"></a>&lt;Özel durumu&gt;

Özel durumların işlenmesiyle ilgili çeşitli türleri ve işlevleri tanımlar. Özel durum işleme, sistemin bir hatadan kurtarılması durumlarında kullanılır. Bir işlevden programa döndürülecek denetim için bir yol sağlar. Özel durum işleme birleştirmesinin amacı düzenli bir şekilde bir hatadan kurtarılmasına olanak sağlayarak programın sağlamlığını artırmaktır.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <exception>

```

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[exception_ptr](../standard-library/exception-typedefs.md#exception_ptr)|Bir özel duruma bir işaretçi tanımlayan tür.|
|[terminate_handler](../standard-library/exception-typedefs.md#terminate_handler)|Bir işlevi olarak kullanım için uygun bir işaretçi açıklayan türü bir `terminate_handler`.|
|[unexpected_handler](../standard-library/exception-typedefs.md#unexpected_handler)|Bir işlevi olarak kullanım için uygun bir işaretçi açıklayan türü bir `unexpected_handler`.|

### <a name="functions"></a>İşlevler

|İşlev|Açıklama|
|-|-|
|[current_exception](../standard-library/exception-functions.md#current_exception)|Geçerli özel durum için bir işaretçi alır.|
|[get_terminate](../standard-library/exception-functions.md#get_terminate)|Geçerli edinir `terminate_handler` işlevi.|
|[get_unexpected](../standard-library/exception-functions.md#get_unexpected)|Geçerli edinir `unexpected_handler` işlevi.|
|[make_exception_ptr](../standard-library/exception-functions.md#make_exception_ptr)|Oluşturur bir `exception_ptr` bir özel durum bir kopyasını içeren nesne.|
|[rethrow_exception](../standard-library/exception-functions.md#rethrow_exception)|Bir parametre olarak geçirilen bir özel durum oluşturur.|
|[set_terminate](../standard-library/exception-functions.md#set_terminate)|Yeni bir kurar `terminate_handler` program sonlandırma sırasında çağrılabilir.|
|[set_unexpected](../standard-library/exception-functions.md#set_unexpected)|Yeni bir kurar `unexpected_handler` olması için ne zaman beklenmeyen bir özel durum karşılaştı.|
|[Sonlandırma](../standard-library/exception-functions.md#terminate)|Bir sonlandırıcı işleyici çağırır.|
|[uncaught_exception](../standard-library/exception-functions.md#uncaught_exception)|Döndürür **doğru** yalnızca oluşturulan bir özel durum şu anda işleniyorsa.|
|[beklenmeyen](../standard-library/exception-functions.md#unexpected)|Beklenmeyen bir işleyici çağırır.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[bad_exception Sınıfı](../standard-library/bad-exception-class.md)|Sınıfı öğesinden atılan bir özel durumu açıklayan bir `unexpected_handler`.|
|[exception Sınıfı](../standard-library/exception-class.md)|Sınıfı, belirli ifadeleri ve C++ Standart Kitaplığı tarafından oluşturulan tüm özel durumlar için temel sınıf olarak görev yapar.|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
