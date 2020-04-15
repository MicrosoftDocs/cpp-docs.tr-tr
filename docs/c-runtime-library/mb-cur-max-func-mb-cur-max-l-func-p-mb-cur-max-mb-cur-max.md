---
title: ___mb_cur_max_func, ___mb_cur_max_l_func, __p___mb_cur_max, __mb_cur_max
ms.date: 4/2/2020
api_name:
- ___mb_cur_max_l_func
- __p___mb_cur_max
- ___mb_cur_max_func
- __mb_cur_max
- _o____mb_cur_max_func
api_location:
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr80.dll
- msvcr100.dll
- msvcrt.dll
- msvcr90.dll
- msvcr120.dll
- api-ms-win-crt-locale-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- ___mb_cur_max_func
- ___mb_cur_max_l_func
- __p___mb_cur_max
- __mb_cur_max
helpviewer_keywords:
- __mb_cur_max
- ___mb_cur_max_func
- ___mb_cur_max_l_func
- __p___mb_cur_max
ms.assetid: 60d36108-1ca7-45a6-8ce7-68a91f13e3a1
ms.openlocfilehash: f9b9e2d903bb05f5b1b653b4fb51c57b354d4126
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81351075"
---
# <a name="___mb_cur_max_func-___mb_cur_max_l_func-__p___mb_cur_max-__mb_cur_max"></a>___mb_cur_max_func, ___mb_cur_max_l_func, __p___mb_cur_max, __mb_cur_max

Dahili CRT fonksiyonu. Geçerli veya belirtilen yerel bölge için çok bayt karakterdeki maksimum bayt sayısını alır.

## <a name="syntax"></a>Sözdizimi

```cpp
int ___mb_cur_max_func(void);
int ___mb_cur_max_l_func(_locale_t locale);
int * __p___mb_cur_max(void);
#define __mb_cur_max (___mb_cur_max_func())
```

#### <a name="parameters"></a>Parametreler

yerelleştirmek Sonucu almak için yerel yapı. Bu değer null ise, geçerli iş parçacığı yerel kullanılır.

## <a name="return-value"></a>Dönüş Değeri

Geçerli iş parçacığı yerel durumu veya belirtilen yerel bölge için çok bayt karakterindeki maksimum bayt sayısı.

## <a name="remarks"></a>Açıklamalar

Bu, CRT'nin iş parçacığı yerel depolamadan [MB_CUR_MAX](../c-runtime-library/mb-cur-max.md) makronun geçerli değerini almak için kullandığı bir iç işlevdir. Taşınabilirlik için kodunuzdamakrokullanmanızı `MB_CUR_MAX` öneririz.

Makro `__mb_cur_max` `___mb_cur_max_func()` işlevi aramak için kullanışlı bir yoldur. İşlev Visual `__p___mb_cur_max` C++ 5.0 ve önceki sürümlerle uyumluluk için tanımlanır.

Dahili CRT işlevleri uygulamaya özgüdir ve her sürümde değiştirilebilir. Kodunuzda kullanılmasını önermiyoruz.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`___mb_cur_max_func`, `___mb_cur_max_l_func`, `__p___mb_cur_max`|\<ctype.h>, \<stdlib.h>|

## <a name="see-also"></a>Ayrıca bkz.

[MB_CUR_MAX](../c-runtime-library/mb-cur-max.md)
