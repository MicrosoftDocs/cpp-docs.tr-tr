---
title: _get_pgmptr
ms.date: 11/04/2016
api_name:
- _get_pgmptr
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
ms.openlocfilehash: 4f9a3b19cc7eb1870b87ec46b7923987ec646e32
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70955758"
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

Yalnızca, programınızın **Main ()** veya **WinMain ()** gibi bir dar giriş noktası varsa, **_get_pgmptr** çağırın. **_Pgmptr** genel değişkeni işlemle ilişkili yürütülebilir dosyanın tam yolunu içerir. Daha fazla bilgi için bkz. [_pgmptr, _wpgmptr](../../c-runtime-library/pgmptr-wpgmptr.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_pgmptr**|\<Stdlib. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[_get_wpgmptr](get-wpgmptr.md)<br/>
