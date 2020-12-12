---
description: 'Hakkında daha fazla bilgi edinin: ___lc_codepage_func'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: b59443b8b448eb91e54548700ba7171fc0c00fd9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97246545"
---
# <a name="___lc_codepage_func"></a>___lc_codepage_func

İç CRT işlevi. İş parçacığının geçerli kod sayfasını alır.

## <a name="syntax"></a>Syntax

```cpp
UINT ___lc_codepage_func(void);
```

## <a name="return-value"></a>Dönüş Değeri

İş parçacığının geçerli kod sayfası.

## <a name="remarks"></a>Açıklamalar

`___lc_codepage_func` , diğer CRT işlevleri tarafından, CRT verileri için iş parçacığı yerel depolama alanından geçerli kod sayfasını almak üzere kullanılan bir iç CRT işlevidir. Bu bilgiler [_get_current_locale](../c-runtime-library/reference/get-current-locale.md) işlevi kullanılarak da kullanılabilir.

*Kod sayfası* , tek baytlık veya çift baytlık kodların ayrı karakterlere eşlenmesinin. Farklı kod sayfaları, genellikle bir dil veya dil grubu için özelleştirilen, farklı özel karakterler içerir. Kod sayfaları hakkında daha fazla bilgi için bkz. [kod sayfaları](../c-runtime-library/code-pages.md).

İç CRT işlevleri uygulamaya özgüdür ve her sürümde değiştirilebilir. Kodunuzda kullanımını önermiyoruz.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`___lc_codepage_func`|crt\src\setlocal.h|

## <a name="see-also"></a>Ayrıca bkz.

[_get_current_locale](../c-runtime-library/reference/get-current-locale.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)<br/>
[_free_locale](../c-runtime-library/reference/free-locale.md)
