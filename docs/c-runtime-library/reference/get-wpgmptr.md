---
title: _get_wpgmptr
ms.date: 11/04/2016
apiname:
- _get_wpgmptr
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- get_wpgmptr
- _get_wpgmptr
helpviewer_keywords:
- _wpgmptr global variable
- get_wpgmptr function
- wpgmptr global variable
- _get_wpgmptr function
ms.assetid: a77cdd13-2303-4b7c-9a60-8debdbef2011
ms.openlocfilehash: 0e49bc35f43ed6ed5a5f86e6c76c51854ab71add
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50436341"
---
# <a name="getwpgmptr"></a>_get_wpgmptr

Geçerli değeri alır **_wpgmptr** genel değişkeni.

## <a name="syntax"></a>Sözdizimi

```C
errno_t _get_wpgmptr( 
   wchar_t **pValue 
);
```

### <a name="parameters"></a>Parametreler

*pValue*<br/>
Geçerli değeri ile doldurulacak bir dizeye bir işaretçi **_wpgmptr** değişkeni.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır döndürür; bir hata kodu. Varsa *pValue* olduğu **NULL**, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse, bu işlev ayarlar **errno** için **EINVAL** ve döndürür **EINVAL**.

## <a name="remarks"></a>Açıklamalar

Yalnızca çağrı **_get_wpgmptr** programınızı geniş giriş noktası varsa, ister **wmain()** veya **wWinMain()**. **_Wpgmptr** genel değişkeninin geniş karakterli dize olarak işlemiyle ilişkili yürütülebilir dosyanın tam yolunu içerir. Daha fazla bilgi için [_pgmptr, _wpgmptr](../../c-runtime-library/pgmptr-wpgmptr.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_wpgmptr**|\<stdlib.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[_get_pgmptr](get-pgmptr.md)<br/>
