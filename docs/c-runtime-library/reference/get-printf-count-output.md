---
title: _get_printf_count_output
ms.date: 11/04/2016
apiname:
- _get_printf_count_output
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- get_printf_count_output
- _get_printf_count_output
helpviewer_keywords:
- '%n format'
- get_printf_count_output function
- _get_printf_count_output function
ms.assetid: 850f9f33-8319-433e-98d8-6a694200d994
ms.openlocfilehash: 477e4a9e987f27bd70b9707e91b9ea9d84b69993
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62332059"
---
# <a name="getprintfcountoutput"></a>_get_printf_count_output

Belirtir olup olmadığını [printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)-ailesi işlevleri Destek **%n** biçimi.

## <a name="syntax"></a>Sözdizimi

```C
int _get_printf_count_output();
```

## <a name="return-value"></a>Dönüş Değeri

Sıfır olmayan if **%n** desteklenir, 0 ise **%n** desteklenmiyor.

## <a name="remarks"></a>Açıklamalar

Varsa **%n** olduğunu (varsayılan), desteklenmeyen karşılaşıldığında **%n** herhangi bir biçim dizesindeki **printf** işlevleri açıklandığı gibi geçersiz parametre işleyicisi çağırılır [Parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Varsa **%n** desteği etkin (bkz [_set_printf_count_output](set-printf-count-output.md)) sonra **%n** açıklandığı gibi davranır [biçim belirtim Sözdizimi: printf ve wprintf İşlevleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_printf_count_output**|\<stdio.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bakın [_set_printf_count_output](set-printf-count-output.md).

## <a name="see-also"></a>Ayrıca bkz.

[_set_printf_count_output](set-printf-count-output.md)<br/>
