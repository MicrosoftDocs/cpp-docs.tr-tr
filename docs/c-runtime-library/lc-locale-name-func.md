---
title: ___lc_locale_name_func
ms.date: 11/04/2016
api_name:
- ___lc_locale_name_func
api_location:
- msvcrt.dll
- msvcr110.dll
- msvcr100.dll
- msvcr90.dll
- msvcr120.dll
- msvcr80.dll
- msvcr110_clr0400.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- ___lc_locale_name_func
helpviewer_keywords:
- ___lc_locale_name_func
ms.assetid: ef858308-872e-43de-95e0-9b1b4084343e
ms.openlocfilehash: abc1ade393538586ad07f57e6838591833c9948b
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70944238"
---
# <a name="___lc_locale_name_func"></a>___lc_locale_name_func

İç CRT işlevi. İş parçacığının geçerli yerel ayar adını alır.

## <a name="syntax"></a>Sözdizimi

```cpp
wchar_t** ___lc_locale_name_func(void);
```

## <a name="return-value"></a>Dönüş Değeri

İş parçacığının geçerli yerel ayar adını içeren bir dize işaretçisi.

## <a name="remarks"></a>Açıklamalar

`___lc_locale_name_func`, CRT verileri için iş parçacığı yerel depolama alanından geçerli yerel ayar adını almak için diğer CRT işlevleri tarafından kullanılan bir iç CRT işlevidir. Bu bilgiler, [_get_current_locale](../c-runtime-library/reference/get-current-locale.md) işlevi veya [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) işlevleri kullanılarak da kullanılabilir.

İç CRT işlevleri uygulamaya özgüdür ve her sürümde değiştirilebilir. Kodunuzda kullanımını önermiyoruz.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`___lc_locale_name_func`|crt\src\setlocal.h|

## <a name="see-also"></a>Ayrıca bkz.

[_get_current_locale](../c-runtime-library/reference/get-current-locale.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)<br/>
[_free_locale](../c-runtime-library/reference/free-locale.md)
