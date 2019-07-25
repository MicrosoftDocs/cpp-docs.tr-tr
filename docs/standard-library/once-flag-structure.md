---
title: once_flag Yapısı
ms.date: 09/17/2018
f1_keywords:
- mutex/std::once_flag
ms.assetid: 71bfb88d-ca8c-4082-a6e1-ff52151e8629
ms.openlocfilehash: fb85bd48f9b1ac10ec2fefbc6738aae777f67bcf
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455203"
---
# <a name="onceflag-structure"></a>once_flag Yapısı

Başlatma kodunun, yürütmenin birden çok iş parçacığı olması durumunda bile yalnızca bir kez çağrıldığından emin olmak için [call_once](../standard-library/mutex-functions.md#call_once) şablon işleviyle birlikte kullanılan bir **yapıyı** temsil eder.

## <a name="syntax"></a>Sözdizimi

struct once_flag {constexpr once_flag () noexcept;};

## <a name="remarks"></a>Açıklamalar

Yapının yalnızca bir varsayılan Oluşturucusu vardır.  `once_flag`

Türündeki `once_flag` nesneler oluşturulabilir, ancak bunlar kopyalanamazlar.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<mutex >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<mutex >](../standard-library/mutex.md)
