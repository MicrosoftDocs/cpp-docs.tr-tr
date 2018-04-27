---
title: _getmbcp | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _getmbcp
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
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _getmbcp
- getmbcp
dev_langs:
- C++
helpviewer_keywords:
- code pages, determining current
- _getmbcp function
- getmbcp function
ms.assetid: 2db202d4-5c3d-4871-a0b8-ceb0b79ee7bb
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3a8d20b510a94ee5cd773dca66a82b4cb553e7b5
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="getmbcp"></a>_getmbcp

Geçerli kod sayfası alır.

## <a name="syntax"></a>Sözdizimi

```C
int _getmbcp( void );
```

## <a name="return-value"></a>Dönüş Değeri

Geçerli birden çok baytlı kod sayfasını döndürür. Dönüş değerinin 0 tek baytlı kod sayfası kullanımda olduğunu gösterir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_getmbcp**|\<Mbctype.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[_setmbcp](setmbcp.md)<br/>
