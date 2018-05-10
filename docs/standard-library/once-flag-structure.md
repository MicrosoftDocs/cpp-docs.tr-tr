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
ms.openlocfilehash: f8a8d28f19e32988bfa179642a87e880413bb0ff
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="onceflag-structure"></a>once_flag Yapısı

Temsil eden bir `struct` şablonu işleviyle kullanılan [call_once](../standard-library/mutex-functions.md#call_once) başlatmanın emin olmak için kod bile birden çok iş parçacığı yürütme varlığında yalnızca bir kez çağrılır.

## <a name="syntax"></a>Sözdizimi

Yapı once_flag {constexpr once_flag() noexcept; once_flag(const once_flag&); once_flag & işleci =(const once_flag&);};

## <a name="remarks"></a>Açıklamalar

`once_flag` `struct` Yalnızca bir varsayılan oluşturucusu vardır.

Nesne türü `once_flag` oluşturulabilir, ancak bunlar kopyalanamaz.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<mutex >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<Mutex >](../standard-library/mutex.md)<br/>
