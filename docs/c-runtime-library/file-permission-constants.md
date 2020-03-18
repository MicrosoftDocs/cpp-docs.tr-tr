---
title: Dosya İzin Sabitleri
ms.date: 11/04/2016
helpviewer_keywords:
- S_IWRITE constant
- constants [C++], file attributes
- S_IREAD constant
- file permissions [C++]
- _S_IWRITE constant
- _S_IREAD constant
ms.assetid: 593cad33-31d1-44d2-8941-8af7d210c88c
ms.openlocfilehash: 9f6126b867e29ca37468c6ff383224a483639c78
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79443281"
---
# <a name="file-permission-constants"></a>Dosya İzin Sabitleri

## <a name="syntax"></a>Sözdizimi

```
#include <sys/stat.h>
```

## <a name="remarks"></a>Açıklamalar

`_O_CREAT` (`_open`, `_sopen`) belirtildiğinde Bu sabitlerden biri gereklidir.

`pmode` bağımsız değişkeni, dosyanın izin ayarlarını aşağıda gösterildiği gibi belirtir.

|Sabit|Anlamı|
|--------------|-------------|
|`_S_IREAD`|Okuma izni verildi|
|`_S_IWRITE`|İzin verilen yazma|
|`_S_IREAD` &#124; `_S_IWRITE`|Okuma ve yazma izni verildi|

`_umask`için `pmode` bağımsız değişkeni olarak kullanıldığında, bildirim sabiti, izin ayarını aşağıdaki şekilde ayarlar.

|Sabit|Anlamı|
|--------------|-------------|
|`_S_IREAD`|Yazmaya izin verilmiyor (dosya salt okunurdur)|
|`_S_IWRITE`|Okumaya izin verilmiyor (dosya salt yazılır)|
|`_S_IREAD` &#124; `_S_IWRITE`|Ne okumadan ne de yazmadan izin verilmez|

## <a name="see-also"></a>Ayrıca bkz.

[_open, _wopen](../c-runtime-library/reference/open-wopen.md)<br/>
[_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md)<br/>
[_umask](../c-runtime-library/reference/umask.md)<br/>
[Standart Türler](../c-runtime-library/standard-types.md)<br/>
[Global Sabitler](../c-runtime-library/global-constants.md)
