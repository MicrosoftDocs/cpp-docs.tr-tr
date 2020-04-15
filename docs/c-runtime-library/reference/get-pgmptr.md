---
title: _get_pgmptr
ms.date: 4/2/2020
api_name:
- _get_pgmptr
- _o__get_pgmptr
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
- get_pgmptr
- _get_pgmptr
helpviewer_keywords:
- get_pgmptr function
- _get_pgmptr function
- pgmptr global variable
- _pgmptr global variable
ms.assetid: 29f16a9f-a685-4721-add3-7fad4f67eece
ms.openlocfilehash: efcac6a64c01bee38a3753bdec378dae625db35e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345018"
---
# <a name="_get_pgmptr"></a>_get_pgmptr

**_pgmptr** global değişkenin geçerli değerini alır.

## <a name="syntax"></a>Sözdizimi

```C
errno_t _get_pgmptr(
   char **pValue
);
```

### <a name="parameters"></a>Parametreler

*pDeğer*<br/>
**_pgmptr** değişkeninin geçerli değeriyle doldurulacak bir dize işaretçisi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır döndürür; hata bir hata kodu. *pValue* **NULL**ise, geçersiz parametre işleyicisi [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, bu işlev **EINVAL için errno** ayarlar ve **EINVAL** döndürür. **EINVAL**

## <a name="remarks"></a>Açıklamalar

Yalnızca _get_pgmptr'yi **arayın,** programınızda **main()** veya **WinMain()** gibi dar bir giriş noktası varsa. _pgmptr **_pgmptr** global değişken, işlemle ilişkili yürütülebilir giden tam yolu içerir. Daha fazla bilgi için [_pgmptr _wpgmptr.](../../c-runtime-library/pgmptr-wpgmptr.md)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_pgmptr**|\<stdlib.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[_get_wpgmptr](get-wpgmptr.md)<br/>
