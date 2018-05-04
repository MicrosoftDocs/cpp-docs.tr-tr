---
title: _get_printf_count_output | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- '%n format'
- get_printf_count_output function
- _get_printf_count_output function
ms.assetid: 850f9f33-8319-433e-98d8-6a694200d994
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 216df8d973f391db2b6114d9bbcb50dcf509c5b5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="getprintfcountoutput"></a>_get_printf_count_output

Gösterir olup olmadığını [printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)-ailesi işlevleri Destek **%n** biçimi.

## <a name="syntax"></a>Sözdizimi

```C
int _get_printf_count_output();
```

## <a name="return-value"></a>Dönüş Değeri

Sıfır dışı IF **%n** desteklenir, 0 ise **%n** desteklenmiyor.

## <a name="remarks"></a>Açıklamalar

Varsa **%n** olduğunu (varsayılan), desteklenmeyen karşılaşmadan **%n** herhangi bir dize biçiminde **printf** açıklandığı gibi işlevleri geçersiz parametre işleyicisi çağırma [Parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Varsa **%n** desteği etkin (bkz [_set_printf_count_output](set-printf-count-output.md)) sonra **%n** açıklandığı gibi davranacak [biçim belirtim Sözdizimi: printf ve wprintf İşlevler](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_printf_count_output**|\<stdio.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bkz [_set_printf_count_output](set-printf-count-output.md).

## <a name="see-also"></a>Ayrıca bkz.

[_set_printf_count_output](set-printf-count-output.md)<br/>
