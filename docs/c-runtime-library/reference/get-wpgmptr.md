---
title: _get_wpgmptr
ms.date: 11/04/2016
api_name:
- _get_wpgmptr
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
- get_wpgmptr
- _get_wpgmptr
helpviewer_keywords:
- _wpgmptr global variable
- get_wpgmptr function
- wpgmptr global variable
- _get_wpgmptr function
ms.assetid: a77cdd13-2303-4b7c-9a60-8debdbef2011
ms.openlocfilehash: 0cd2dc9c2f82d3dc49a17dc438157233c50b3261
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70955567"
---
# <a name="_get_wpgmptr"></a>_get_wpgmptr

**_Wpgmptr** genel değişkeninin geçerli değerini alır.

## <a name="syntax"></a>Sözdizimi

```C
errno_t _get_wpgmptr(
   wchar_t **pValue
);
```

### <a name="parameters"></a>Parametreler

*pValue*<br/>
**_Wpgmptr** değişkeninin geçerli değeriyle doldurulacak bir dizeye yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır döndürür; hatada hata kodu. *PValue* **null**ise, geçersiz parametre işleyicisi [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlev **errno** ' ı **EINVAL** olarak ayarlar ve **EINVAL**döndürür.

## <a name="remarks"></a>Açıklamalar

Yalnızca, **wmain ()** veya **wWinMain ()** gibi geniş bir giriş noktası varsa, yalnızca **_get_wpgmptr** çağrısı yapın. **_Wpgmptr** genel değişkeni, işlemle ilişkili yürütülebilir dosyanın tam yolunu geniş karakterli bir dize olarak içerir. Daha fazla bilgi için bkz. [_pgmptr, _wpgmptr](../../c-runtime-library/pgmptr-wpgmptr.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_wpgmptr**|\<Stdlib. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[_get_pgmptr](get-pgmptr.md)<br/>
