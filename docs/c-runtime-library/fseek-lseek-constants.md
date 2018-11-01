---
title: fseek, _lseek Sabitleri
ms.date: 11/04/2016
f1_keywords:
- SEEK_END
- SEEK_SET
- SEEK_CUR
helpviewer_keywords:
- SEEK_SET constant
- SEEK_END constant
- SEEK_CUR constant
ms.assetid: 9deeb13e-5aa3-4c33-80d8-721c80a4de9d
ms.openlocfilehash: fcf2c7ac6ea6280abdab5279ab67b65656bdeff9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50507694"
---
# <a name="fseek-lseek-constants"></a>fseek, _lseek Sabitleri

## <a name="syntax"></a>Sözdizimi

```

#include <stdio.h>

```

## <a name="remarks"></a>Açıklamalar

*Kaynak* bağımsız değişkeni başlangıç konumunu belirten ve aşağıdaki bildirim sabitleri biri olabilir:

|Sabit|Açıklama|
|--------------|-------------|
|`SEEK_END`|Dosya sonu|
|`SEEK_CUR`|Dosya işaretçisini geçerli konumu|
|`SEEK_SET`|Dosyasının başında|

## <a name="see-also"></a>Ayrıca Bkz.

[fseek, _fseeki64](../c-runtime-library/reference/fseek-fseeki64.md)<br/>
[_lseek, _lseeki64](../c-runtime-library/reference/lseek-lseeki64.md)<br/>
[Global Sabitler](../c-runtime-library/global-constants.md)