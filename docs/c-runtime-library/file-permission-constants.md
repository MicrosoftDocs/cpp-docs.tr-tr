---
title: Dosya İzin Sabitleri
ms.date: 11/04/2016
f1_keywords:
- _S_IWRITE
- _S_IREAD
helpviewer_keywords:
- S_IWRITE constant
- constants [C++], file attributes
- S_IREAD constant
- file permissions [C++]
- _S_IWRITE constant
- _S_IREAD constant
ms.assetid: 593cad33-31d1-44d2-8941-8af7d210c88c
ms.openlocfilehash: 7b9d99f8b0fc7daf8f7dc58db999c7f885a3dc8d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50648610"
---
# <a name="file-permission-constants"></a>Dosya İzin Sabitleri

## <a name="syntax"></a>Sözdizimi

```

#include <sys/stat.h>

```

## <a name="remarks"></a>Açıklamalar

Bu sabitlerden birine gereklidir `_O_CREAT` (`_open`, `_sopen`) belirtilir.

`pmode` Bağımsız değişkeni aşağıdaki gibi dosyanın izin ayarlarını belirtir.

|Sabit|Açıklama|
|--------------|-------------|
|`_S_IREAD`|Okuma izin verilir|
|`_S_IWRITE`|İzin verilen yazma|
|`_S_IREAD` &#124; `_S_IWRITE`|Okuma ve yazma izin verilir|

Olarak kullanıldığında `pmode` için bağımsız değişken `_umask`, Bildirim sabiti izin ayarının gibi ayarlar.

|Sabit|Açıklama|
|--------------|-------------|
|`_S_IREAD`|Yazma izin verilmez (salt okunur dosya)|
|`_S_IWRITE`|Okuma izin verilmez (dosya salt yazılır)|
|`_S_IREAD` &#124; `_S_IWRITE`|Okuma ne yazmaya izin verilir|

## <a name="see-also"></a>Ayrıca Bkz.

[_open, _wopen](../c-runtime-library/reference/open-wopen.md)<br/>
[_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md)<br/>
[_umask](../c-runtime-library/reference/umask.md)<br/>
[Standart Türler](../c-runtime-library/standard-types.md)<br/>
[Global Sabitler](../c-runtime-library/global-constants.md)