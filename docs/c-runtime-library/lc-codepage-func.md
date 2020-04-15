---
title: ___lc_codepage_func
ms.date: 4/2/2020
api_name:
- ___lc_codepage_func
- _o____lc_codepage_func
api_location:
- msvcr120.dll
- msvcr110_clr0400.dll
- msvcr80.dll
- msvcr100.dll
- msvcr90.dll
- msvcr110.dll
- msvcrt.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- lc_codepage_func
- ___lc_codepage_func
helpviewer_keywords:
- ___lc_codepage_func
ms.assetid: 6a663bd0-5a63-4a2f-9507-872ec1582aae
ms.openlocfilehash: 2f3eeb4611a0a41ff1782e0b162cd65d86d3ef65
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81351230"
---
# <a name="___lc_codepage_func"></a>___lc_codepage_func

Dahili CRT fonksiyonu. İş parçacığının geçerli kod sayfasını alır.

## <a name="syntax"></a>Sözdizimi

```cpp
UINT ___lc_codepage_func(void);
```

## <a name="return-value"></a>Dönüş Değeri

İş parçacığının geçerli kod sayfası.

## <a name="remarks"></a>Açıklamalar

`___lc_codepage_func`crt verileri için iş parçacığı yerel depolama geçerli kod sayfasını almak için diğer CRT işlevleri tarafından kullanılan bir iç CRT işlevidir. Bu [bilgiler, _get_current_locale](../c-runtime-library/reference/get-current-locale.md) işlevini kullanarak da kullanılabilir.

*Kod sayfası,* tek bayt veya çift bayt kodlarının tek tek karakterlere eşlenemesidir. Farklı kod sayfaları, genellikle bir dil veya bir dil grubu için özelleştirilmiş farklı özel karakterler içerir. Kod sayfaları hakkında daha fazla bilgi için [Kod Sayfaları'na](../c-runtime-library/code-pages.md)bakın.

Dahili CRT işlevleri uygulamaya özgüdir ve her sürümde değiştirilebilir. Kodunuzda kullanılmasını önermiyoruz.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`___lc_codepage_func`|crt\src\setlocal.h|

## <a name="see-also"></a>Ayrıca bkz.

[_get_current_locale](../c-runtime-library/reference/get-current-locale.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)<br/>
[_free_locale](../c-runtime-library/reference/free-locale.md)
