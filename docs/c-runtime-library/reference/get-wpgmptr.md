---
title: _get_wpgmptr
ms.date: 4/2/2020
api_name:
- _get_wpgmptr
- _o__get_wpgmptr
api_location:
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- get_wpgmptr
- _get_wpgmptr
helpviewer_keywords:
- _wpgmptr global variable
- get_wpgmptr function
- wpgmptr global variable
- _get_wpgmptr function
ms.assetid: a77cdd13-2303-4b7c-9a60-8debdbef2011
ms.openlocfilehash: 1e54d3dbdc837c491f5b39d33a9b8197094ac60b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344860"
---
# <a name="_get_wpgmptr"></a>_get_wpgmptr

**_wpgmptr** global değişkenin geçerli değerini alır.

## <a name="syntax"></a>Sözdizimi

```C
errno_t _get_wpgmptr(
   wchar_t **pValue
);
```

### <a name="parameters"></a>Parametreler

*pDeğer*<br/>
**_wpgmptr** değişkeninin geçerli değeriyle doldurulacak bir dize işaretçisi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır döndürür; hata bir hata kodu. *pValue* **NULL**ise, geçersiz parametre işleyicisi [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, bu işlev **EINVAL için errno** ayarlar ve **EINVAL** döndürür. **EINVAL**

## <a name="remarks"></a>Açıklamalar

Yalnızca **_get_wpgmptr'ı** arayın, programınızda **wmain() veya wWinMain()** gibi geniş bir giriş noktası varsa. **wWinMain()** **_wpgmptr** genel değişkeni, geniş karakterli bir dize olarak işlemle ilişkili yürütülebilir yol içerir. Daha fazla bilgi için [_pgmptr _wpgmptr.](../../c-runtime-library/pgmptr-wpgmptr.md)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_wpgmptr**|\<stdlib.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[_get_pgmptr](get-pgmptr.md)<br/>
