---
title: ___lc_collate_cp_func | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- ___lc_collate_cp_func
apilocation:
- msvcr120.dll
- msvcrt.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr90.dll
apitype: DLLExport
f1_keywords:
- ___lc_collate_cp_func
dev_langs:
- C++
helpviewer_keywords:
- ___lc_collate_cp_func
ms.assetid: 46ccc084-7ac9-4e5d-9138-e12cb5845615
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d239820221c696dbb8d27e2824ed871a7e2d5ad8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46063063"
---
# <a name="lccollatecpfunc"></a>___lc_collate_cp_func

İç CRT işlevi. İş parçacığının geçerli harmanlama kod sayfası alır.

## <a name="syntax"></a>Sözdizimi

```cpp
UINT ___lc_codepage_func(void);
```

## <a name="return-value"></a>Dönüş Değeri

İş parçacığının geçerli harmanlama kod sayfası.

## <a name="remarks"></a>Açıklamalar

`___lc_collate_cp_func` diğer CRT işlevleri tarafından geçerli harmanlama kod sayfasını bir iş parçacığı yerel depolama alanından CRT verileri almak için kullanılan bir iç CRT işlevdir. Bu bilgiler ayrıca kullanılarak kullanılabilir [_get_current_locale](../c-runtime-library/reference/get-current-locale.md) işlevi.

İç CRT işlevleri uygulamasına özgüdür ve her değişebilir bırakın. Kodunuzda bunların kullanılması önerilmemektedir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`___lc_collate_cp_func`|crt\src\setlocal.h|

## <a name="see-also"></a>Ayrıca Bkz.

[_get_current_locale](../c-runtime-library/reference/get-current-locale.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)<br/>
[_free_locale](../c-runtime-library/reference/free-locale.md)