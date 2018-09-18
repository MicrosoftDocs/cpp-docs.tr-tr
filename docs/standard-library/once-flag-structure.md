---
title: once_flag yapısı | Microsoft Docs
ms.custom: ''
ms.date: 09/17/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- mutex/std::once_flag
dev_langs:
- C++
ms.assetid: 71bfb88d-ca8c-4082-a6e1-ff52151e8629
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 67cfbe06461598fbd04e124629399baa63fdd5d9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46104341"
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
