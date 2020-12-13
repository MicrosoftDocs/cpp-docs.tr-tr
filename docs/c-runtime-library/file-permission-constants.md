---
description: 'Daha fazla bilgi edinin: dosya Izni sabitleri'
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
ms.openlocfilehash: a220ec404202b1f962a4c0bf51d20b7eea2720ee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331082"
---
# <a name="file-permission-constants"></a>Dosya İzin Sabitleri

## <a name="syntax"></a>Syntax

```
#include <sys/stat.h>
```

## <a name="remarks"></a>Açıklamalar

`_O_CREAT`( `_open` ,) Belirtildiğinde Bu sabitlerden biri gereklidir `_sopen` .

`pmode`Bağımsız değişkeni, dosyanın izin ayarlarını aşağıda gösterildiği gibi belirtir.

|Sabit|Anlamı|
|--------------|-------------|
|`_S_IREAD`|Okuma izni verildi|
|`_S_IWRITE`|İzin verilen yazma|
|`_S_IREAD` &#124; `_S_IWRITE`|Okuma ve yazma izni verildi|

`pmode`İçin bağımsız değişken olarak kullanıldığında `_umask` , bildirim sabiti, izin ayarını aşağıdaki gibi ayarlar.

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
[Global sabitler](../c-runtime-library/global-constants.md)
