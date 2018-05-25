---
title: _get_terminate | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _get_terminate
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
- get_terminate
- _get_terminate
- __get_terminate
dev_langs:
- C++
helpviewer_keywords:
- __get_terminate function
- get_terminate function
- _get_terminate function
ms.assetid: c8f168c4-0ad5-4832-a522-dd1ef383c208
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 82caa4c8516b9d6ccf813240668692bb54d16eda
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2018
---
# <a name="getterminate"></a>_get_terminate

Çağrılacak sonlandırma yordamı döndürür **sonlandırmak**.

## <a name="syntax"></a>Sözdizimi

```C
terminate_function _get_terminate( void );
```

## <a name="return-value"></a>Dönüş Değeri

Tarafından kaydedilen işlevi için bir işaretçi döndüren [set_terminate](set-terminate-crt.md). Hiçbir işlev ayarlarsanız dönüş değerini varsayılan davranışını geri yüklemek için kullanılabilir; Bu değer olabilir **NULL**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_terminate**|\<EH.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme Rutinleri](../../c-runtime-library/exception-handling-routines.md)<br/>
[abort](abort.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[Sonlandırma](terminate-crt.md)<br/>
[beklenmeyen](unexpected-crt.md)<br/>
