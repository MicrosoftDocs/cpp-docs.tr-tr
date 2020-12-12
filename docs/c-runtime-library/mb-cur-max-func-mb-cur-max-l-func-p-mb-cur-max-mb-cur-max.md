---
description: 'Hakkında daha fazla bilgi edinin: ___mb_cur_max_func, ___mb_cur_max_l_func, __p___mb_cur_max, __mb_cur_max'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 1308dbe969f8b6638835f52ec1e7a2cdcd63bb7f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321168"
---
# <a name="___mb_cur_max_func-___mb_cur_max_l_func-__p___mb_cur_max-__mb_cur_max"></a>___mb_cur_max_func, ___mb_cur_max_l_func, __p___mb_cur_max, __mb_cur_max

İç CRT işlevi. Geçerli veya belirtilen yerel ayar için çok baytlı bir karakter içindeki en fazla bayt sayısını alır.

## <a name="syntax"></a>Sözdizimi

```cpp
int ___mb_cur_max_func(void);
int ___mb_cur_max_l_func(_locale_t locale);
int * __p___mb_cur_max(void);
#define __mb_cur_max (___mb_cur_max_func())
```

#### <a name="parameters"></a>Parametreler

yerel ayarın sonucu almak için yerel ayar yapısı. Bu değer null ise, geçerli iş parçacığı yerel ayarı kullanılır.

## <a name="return-value"></a>Dönüş Değeri

Geçerli iş parçacığı yerel ayarı veya belirtilen yerel ayar için çok baytlı bir karakter içindeki en fazla bayt sayısı.

## <a name="remarks"></a>Açıklamalar

Bu, CRT 'ın, iş parçacığı yerel depolama alanından [MB_CUR_MAX](../c-runtime-library/mb-cur-max.md) makrosunun geçerli değerini almak için kullandığı bir iç işlevdir. `MB_CUR_MAX`Taşınabilirlik için kodunuzda makroyu kullanmanızı öneririz.

`__mb_cur_max`Makro, işlevi çağırmak için kullanışlı bir yoldur `___mb_cur_max_func()` . `__p___mb_cur_max`İşlev, Visual C++ 5,0 ve önceki sürümlerle uyumluluk için tanımlanmıştır.

İç CRT işlevleri uygulamaya özgüdür ve her sürümde değiştirilebilir. Kodunuzda kullanımını önermiyoruz.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`___mb_cur_max_func`, `___mb_cur_max_l_func`, `__p___mb_cur_max`|\<ctype.h>, \<stdlib.h>|

## <a name="see-also"></a>Ayrıca bkz.

[MB_CUR_MAX](../c-runtime-library/mb-cur-max.md)
