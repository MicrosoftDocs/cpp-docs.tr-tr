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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: a4a9bddfa861727e174325dc639868e3529162cd
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82918210"
---
# <a name="_get_pgmptr"></a>_get_pgmptr

**_Pgmptr** genel değişkeninin geçerli değerini alır.

## <a name="syntax"></a>Sözdizimi

```C
errno_t _get_pgmptr(
   char **pValue
);
```

### <a name="parameters"></a>Parametreler

*pValue*<br/>
**_Pgmptr** değişkeninin geçerli değeriyle doldurulacak bir dizeye yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır döndürür; hatada hata kodu. *PValue* **null**ise, geçersiz parametre işleyicisi [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlev **errno** ' ı **EINVAL** olarak ayarlar ve **EINVAL**döndürür.

## <a name="remarks"></a>Açıklamalar

Yalnızca, programınızın **Main ()** veya **WinMain ()** gibi bir dar giriş noktası varsa **_get_pgmptr** çağırın. **_Pgmptr** genel değişkeni, işlemle ilişkili yürütülebilir dosyanın tam yolunu içerir. Daha fazla bilgi için bkz. [_pgmptr, _wpgmptr](../../c-runtime-library/pgmptr-wpgmptr.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_pgmptr**|\<Stdlib. h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[_get_wpgmptr](get-wpgmptr.md)<br/>
