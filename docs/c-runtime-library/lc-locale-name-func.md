---
title: ___lc_locale_name_func
ms.date: 11/04/2016
apiname:
- ___lc_locale_name_func
apilocation:
- msvcrt.dll
- msvcr110.dll
- msvcr100.dll
- msvcr90.dll
- msvcr120.dll
- msvcr80.dll
- msvcr110_clr0400.dll
apitype: DLLExport
f1_keywords:
- ___lc_locale_name_func
helpviewer_keywords:
- ___lc_locale_name_func
ms.assetid: ef858308-872e-43de-95e0-9b1b4084343e
ms.openlocfilehash: 88ce07ca3fece558c23f4fcd9a12949f184b7532
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57741059"
---
# <a name="lclocalenamefunc"></a>___lc_locale_name_func

İç CRT işlevi. İş parçacığının geçerli yerel ayar adını alır.

## <a name="syntax"></a>Sözdizimi

```cpp
wchar_t** ___lc_locale_name_func(void);
```

## <a name="return-value"></a>Dönüş Değeri

İş parçacığının geçerli yerel ayar adını içeren bir dize işaretçisi.

## <a name="remarks"></a>Açıklamalar

`___lc_locale_name_func` diğer CRT işlevleri tarafından geçerli yerel ayar adı, iş parçacığı yerel depolama alanından CRT verilerini almak için kullanılan bir iç CRT işlevdir. Bu bilgiler ayrıca kullanılarak kullanılabilir [_get_current_locale](../c-runtime-library/reference/get-current-locale.md) işlevi veya [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) işlevleri.

İç CRT işlevleri uygulamasına özgüdür ve her değişebilir bırakın. Kodunuzda bunların kullanılması önerilmemektedir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`___lc_locale_name_func`|crt\src\setlocal.h|

## <a name="see-also"></a>Ayrıca bkz.

[_get_current_locale](../c-runtime-library/reference/get-current-locale.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)<br/>
[_free_locale](../c-runtime-library/reference/free-locale.md)
