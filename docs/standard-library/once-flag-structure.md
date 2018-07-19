---
title: once_flag yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 4275b99ada0dbfe1c974446d21862f7fa73aab38
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38964502"
---
# <a name="onceflag-structure"></a>once_flag Yapısı

Temsil eden bir **yapı** şablon işlevi ile kullanılan [call_once](../standard-library/mutex-functions.md#call_once) başlatmanın emin olmak için kodu bile birden çok yürütme iş parçacığının varlığında yalnızca bir kez çağrılır.

## <a name="syntax"></a>Sözdizimi

once_flag yapısı {constexpr once_flag() noexcept; once_flag(const once_flag&); once_flag & işleci =(const once_flag&);};

## <a name="remarks"></a>Açıklamalar

`once_flag` **Yapı** yalnızca bir varsayılan oluşturucusu vardır.

Türündeki nesneler `once_flag` oluşturulabilir, ancak bunlar kopyalanamıyor.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<mutex >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<Mutex >](../standard-library/mutex.md)<br/>
