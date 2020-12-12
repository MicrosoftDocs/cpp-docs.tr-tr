---
description: 'Daha fazla bilgi edinin: fseek, _lseek sabitleri'
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
ms.openlocfilehash: be12597682074f610b0a69395146b400fed4d6b2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319823"
---
# <a name="fseek-_lseek-constants"></a>fseek, _lseek Sabitleri

## <a name="syntax"></a>Syntax

```
#include <stdio.h>
```

## <a name="remarks"></a>Açıklamalar

*Kaynak* bağımsız değişkeni başlangıç konumunu belirtir ve aşağıdaki bildirim sabitlerinden biri olabilir:

|Sabit|Anlamı|
|--------------|-------------|
|`SEEK_END`|Dosya sonu|
|`SEEK_CUR`|Dosya işaretçisinin geçerli konumu|
|`SEEK_SET`|Dosya başlangıcı|

## <a name="see-also"></a>Ayrıca bkz.

[fseek, _fseeki64](../c-runtime-library/reference/fseek-fseeki64.md)<br/>
[_lseek, _lseeki64](../c-runtime-library/reference/lseek-lseeki64.md)<br/>
[Global sabitler](../c-runtime-library/global-constants.md)
