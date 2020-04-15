---
title: ___lc_collate_cp_func
ms.date: 4/2/2020
api_name:
- ___lc_collate_cp_func
- _o____lc_collate_cp_func
api_location:
- msvcr120.dll
- msvcrt.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr90.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- ___lc_collate_cp_func
helpviewer_keywords:
- ___lc_collate_cp_func
ms.assetid: 46ccc084-7ac9-4e5d-9138-e12cb5845615
ms.openlocfilehash: 241292f22beea0cbf4e14d1b4480f6621ef6ccca
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81351128"
---
# <a name="___lc_collate_cp_func"></a>___lc_collate_cp_func

Dahili CRT fonksiyonu. İş parçacığının geçerli harmanlama kodu sayfasını alır.

## <a name="syntax"></a>Sözdizimi

```cpp
UINT ___lc_codepage_func(void);
```

## <a name="return-value"></a>Dönüş Değeri

İş parçacığının geçerli harmanlama kodu sayfası.

## <a name="remarks"></a>Açıklamalar

`___lc_collate_cp_func`crt verileri için iş parçacığı yerel depolama geçerli harmanlama kodu sayfasını almak için diğer CRT işlevleri tarafından kullanılan bir iç CRT işlevidir. Bu [bilgiler, _get_current_locale](../c-runtime-library/reference/get-current-locale.md) işlevini kullanarak da kullanılabilir.

Dahili CRT işlevleri uygulamaya özgüdir ve her sürümde değiştirilebilir. Kodunuzda kullanılmasını önermiyoruz.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`___lc_collate_cp_func`|crt\src\setlocal.h|

## <a name="see-also"></a>Ayrıca bkz.

[_get_current_locale](../c-runtime-library/reference/get-current-locale.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)<br/>
[_free_locale](../c-runtime-library/reference/free-locale.md)
