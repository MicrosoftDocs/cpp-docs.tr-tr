---
title: ___lc_codepage_func
ms.date: 11/04/2016
api_name:
- ___lc_codepage_func
api_location:
- msvcr120.dll
- msvcr110_clr0400.dll
- msvcr80.dll
- msvcr100.dll
- msvcr90.dll
- msvcr110.dll
- msvcrt.dll
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
ms.openlocfilehash: dbadf8239652f5c96e7177dedd91d340e545b9fe
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70944920"
---
# <a name="___lc_codepage_func"></a>___lc_codepage_func

İç CRT işlevi. İş parçacığının geçerli kod sayfasını alır.

## <a name="syntax"></a>Sözdizimi

```cpp
UINT ___lc_codepage_func(void);
```

## <a name="return-value"></a>Dönüş Değeri

İş parçacığının geçerli kod sayfası.

## <a name="remarks"></a>Açıklamalar

`___lc_codepage_func`, diğer CRT işlevleri tarafından, CRT verileri için iş parçacığı yerel depolama alanından geçerli kod sayfasını almak üzere kullanılan bir iç CRT işlevidir. Bu bilgiler, [_get_current_locale](../c-runtime-library/reference/get-current-locale.md) işlevi kullanılarak da kullanılabilir.

*Kod sayfası* , tek baytlık veya çift baytlık kodların ayrı karakterlere eşlenmesinin. Farklı kod sayfaları, genellikle bir dil veya dil grubu için özelleştirilen, farklı özel karakterler içerir. Kod sayfaları hakkında daha fazla bilgi için bkz. [kod sayfaları](../c-runtime-library/code-pages.md).

İç CRT işlevleri uygulamaya özgüdür ve her sürümde değiştirilebilir. Kodunuzda kullanımını önermiyoruz.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`___lc_codepage_func`|crt\src\setlocal.h|

## <a name="see-also"></a>Ayrıca bkz.

[_get_current_locale](../c-runtime-library/reference/get-current-locale.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)<br/>
[_free_locale](../c-runtime-library/reference/free-locale.md)
