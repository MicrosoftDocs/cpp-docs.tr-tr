---
title: _amsg_exit
ms.date: 11/04/2016
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
helpviewer_keywords:
- _amsg_exit
ms.assetid: 146d4faf-d763-43a4-b264-12711196456b
ms.openlocfilehash: 87cd08a6c60a1e29b8a8e15edbfdd69d338d875d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62335626"
---
# <a name="amsgexit"></a>_amsg_exit

Belirtilen çalışma zamanı hata iletisi gösterir ve hata kodu 255 uygulamanızla kapanır.

## <a name="syntax"></a>Sözdizimi

```cpp
void _amsg_exit ( int rterrnum );
```

### <a name="parameters"></a>Parametreler

*rterrnum*<br/>
Sistem tarafından tanımlanan çalışma zamanı hata iletisi kimliği sayısı.

## <a name="remarks"></a>Açıklamalar

Bu işlev çalışma zamanı hata iletisine yayan **stderr** konsol uygulamaları veya Windows uygulamaları için ileti içinde bir ileti kutusunda görüntüler. Hata ayıklama modunda hata ayıklayıcısını çıkmadan önce çağrılacak seçebilirsiniz.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|_amsg_exit|internal.h|