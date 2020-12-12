---
description: 'Daha fazla bilgi edinin: _stat yapısı st_mode alan sabitleri'
title: _stat Yapı st_mode Alanı Sabitleri
ms.date: 11/04/2016
f1_keywords:
- S_IFCHR
- S_IFDIR
- _S_IWRITE
- S_IFMT
- _S_IFDIR
- _S_IREAD
- S_IEXEC
- _S_IEXEC
- _S_IFMT
- S_IWRITE
- S_IFREG
- S_IREAD
- _S_IFCHR
- _S_IFREG
helpviewer_keywords:
- S_IFDIR constant
- stat structure
- S_IWRITE constant
- S_IEXEC constant
- _S_IFREG constant
- S_IREAD constant
- stat structure, constants
- _S_IFMT constant
- st_mode field constants
- S_IFMT constant
- _S_IEXEC constant
- _S_IWRITE constant
- _S_IFDIR constant
- S_IFREG constant
- S_IFCHR constant
- _S_IREAD constant
- _S_IFCHR constant
ms.assetid: fd462004-7563-4766-8443-30b0a86174b6
ms.openlocfilehash: bd304119c705196981342caf5a257cc113fed923
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97235742"
---
# <a name="_stat-structure-st_mode-field-constants"></a>_stat Yapı st_mode Alanı Sabitleri

## <a name="syntax"></a>Syntax

```
#include <sys/stat.h>
```

## <a name="remarks"></a>Açıklamalar

Bu sabitler, [_stat yapısının](../c-runtime-library/standard-types.md) **st_mode** alanındaki dosya türünü belirtmek için kullanılır.

Bit maskesi sabitleri aşağıda açıklanmıştır:

|Sabit|Anlamı|
|--------------|-------------|
|`_S_IFMT`|Dosya türü maskesi|
|`_S_IFDIR`|Dizin|
|`_S_IFCHR`|Özel karakter (ayarlandıysa bir aygıtı belirtir)|
|`_S_IFREG`|Düzenli|
|`_S_IREAD`|Okuma izni, sahip|
|`_S_IWRITE`|Yazma izni, sahip|
|`_S_IEXEC`|Yürütme/arama izni, sahip|

## <a name="see-also"></a>Ayrıca bkz.

[_stat, _wstat Işlevleri](../c-runtime-library/reference/stat-functions.md)<br/>
[_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)<br/>
[Standart Türler](../c-runtime-library/standard-types.md)<br/>
[Global sabitler](../c-runtime-library/global-constants.md)
