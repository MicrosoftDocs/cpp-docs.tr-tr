---
title: ___lc_codepage_func | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- ___lc_codepage_func
apilocation:
- msvcr120.dll
- msvcr110_clr0400.dll
- msvcr80.dll
- msvcr100.dll
- msvcr90.dll
- msvcr110.dll
- msvcrt.dll
apitype: DLLExport
f1_keywords:
- lc_codepage_func
- ___lc_codepage_func
dev_langs:
- C++
helpviewer_keywords:
- ___lc_codepage_func
ms.assetid: 6a663bd0-5a63-4a2f-9507-872ec1582aae
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a35486b271822cb9c7d0dc1bed1e885c13f1dd12
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46087675"
---
# <a name="lccodepagefunc"></a>___lc_codepage_func

İç CRT işlevi. İş parçacığının geçerli kod sayfası alır.

## <a name="syntax"></a>Sözdizimi

```cpp
UINT ___lc_codepage_func(void);
```

## <a name="return-value"></a>Dönüş Değeri

İş parçacığının geçerli kod sayfası.

## <a name="remarks"></a>Açıklamalar

`___lc_codepage_func` diğer CRT işlevleri tarafından mevcut kod sayfasında iş parçacığı yerel depolama alanından CRT verilerini almak için kullanılan bir iç CRT işlevdir. Bu bilgiler ayrıca kullanılarak kullanılabilir [_get_current_locale](../c-runtime-library/reference/get-current-locale.md) işlevi.

A *kod sayfası* karakterlerin tek tek tek veya çift bayt kod eşlemesini. Farklı kod sayfaları genellikle bir dil veya dillerde bir grup için özelleştirilmiş farklı özel karakterler içerir. Kod sayfaları hakkında daha fazla bilgi için bkz. [kod sayfaları](../c-runtime-library/code-pages.md).

İç CRT işlevleri uygulamasına özgüdür ve her değişebilir bırakın. Kodunuzda bunların kullanılması önerilmemektedir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`___lc_codepage_func`|crt\src\setlocal.h|

## <a name="see-also"></a>Ayrıca Bkz.

[_get_current_locale](../c-runtime-library/reference/get-current-locale.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)<br/>
[_free_locale](../c-runtime-library/reference/free-locale.md)