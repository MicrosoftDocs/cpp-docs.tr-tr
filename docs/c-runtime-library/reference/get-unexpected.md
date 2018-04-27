---
title: _get_unexpected | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _get_unexpected
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
apitype: DLLExport
f1_keywords:
- __get_unexpected
- _get_unexpected
- get_unexpected
dev_langs:
- C++
helpviewer_keywords:
- __get_unexpected function
- get_unexpected function
- _get_unexpected function
ms.assetid: a5f7a7a0-18e0-485e-953d-db291068a1e8
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dd09620868f4a8a1c4f1511124dce9c871253e13
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="getunexpected"></a>_get_unexpected

Çağrılacak sonlandırma yordamı döndürür **beklenmeyen**.

## <a name="syntax"></a>Sözdizimi

```C
unexpected_function _get_unexpected( void );
```

## <a name="return-value"></a>Dönüş Değeri

Tarafından kaydedilen işlevi için bir işaretçi döndüren [set_unexpected](set-unexpected-crt.md). Hiçbir işlev ayarlarsanız dönüş değerini varsayılan davranışını geri yüklemek için kullanılabilir; Bu değer NULL olabilir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_unexpected**|\<EH.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme Rutinleri](../../c-runtime-library/exception-handling-routines.md)<br/>
[abort](abort.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[Sonlandırma](terminate-crt.md)<br/>
[beklenmeyen](unexpected-crt.md)<br/>
