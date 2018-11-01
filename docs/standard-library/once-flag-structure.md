---
title: once_flag Yapısı
ms.date: 09/17/2018
f1_keywords:
- mutex/std::once_flag
ms.assetid: 71bfb88d-ca8c-4082-a6e1-ff52151e8629
ms.openlocfilehash: 004a5545e2eccab83b0846e2ae30b88c8431c99d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50481977"
---
# <a name="onceflag-structure"></a>once_flag Yapısı

Temsil eden bir **yapı** şablon işlevi ile kullanılan [call_once](../standard-library/mutex-functions.md#call_once) başlatmanın emin olmak için kodu bile birden çok yürütme iş parçacığının varlığında yalnızca bir kez çağrılır.

## <a name="syntax"></a>Sözdizimi

Yapı once_flag {constexpr once_flag() noexcept;};

## <a name="remarks"></a>Açıklamalar

`once_flag` **Yapı** yalnızca bir varsayılan oluşturucusu vardır.

Türündeki nesneler `once_flag` oluşturulabilir, ancak bunlar kopyalanamıyor.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<mutex >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<Mutex >](../standard-library/mutex.md)<br/>
