---
title: _amsg_exit | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _amsg_exit
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
- _amsg_exit
dev_langs:
- C++
helpviewer_keywords:
- _amsg_exit
ms.assetid: 146d4faf-d763-43a4-b264-12711196456b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dbb7f46bb4f3c942fd1c9e1a1d45c1ccf48739f7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32392802"
---
# <a name="amsgexit"></a>_amsg_exit

Belirtilen çalışma zamanı hata iletisi gösterir ve hata kodu 255 uygulamanızla çıkar.

## <a name="syntax"></a>Sözdizimi

```cpp
void _amsg_exit ( int rterrnum );
```

### <a name="parameters"></a>Parametreler

*rterrnum*<br/>
Sistem tarafından tanımlanan çalışma zamanı hata iletisi kimliği sayısı.

## <a name="remarks"></a>Açıklamalar

Bu işlev çalışma zamanı hata iletisine yayar **stderr** konsol uygulamaları veya bir ileti ileti kutusu Windows uygulamaları için görüntüler. Hata ayıklama modunda çıkmadan önce hata ayıklayıcısı çağrılacak seçebilirsiniz.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|_amsg_exit|internal.h|