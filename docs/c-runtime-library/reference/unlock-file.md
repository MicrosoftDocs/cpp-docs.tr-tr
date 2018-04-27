---
title: _unlock_file | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _unlock_file
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _unlock_file
- unlock_file
dev_langs:
- C++
helpviewer_keywords:
- files [C++], unlocking
- unlock_file function
- _unlock_file function
- unlocking files
ms.assetid: cf380a51-6d3a-4f38-bd64-2d4fb57b4369
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 503087d84e65e556fa610efbf0054c66ee774d48
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="unlockfile"></a>_unlock_file

Dosyaya erişmek için diğer işlemlere izin verme, bir dosya kilidini açar.

## <a name="syntax"></a>Sözdizimi

```C
void _unlock_file(
   FILE* file
);
```

### <a name="parameters"></a>Parametreler

*Dosya* dosya tanıtıcısı.

## <a name="remarks"></a>Açıklamalar

**_Unlock_file** işlevi tarafından belirtilen dosyanın kilidini açarak *dosya*. Bir dosya kilidini başka işlemler tarafından dosyaya erişim sağlar. Bu işlev sürece çağrılmamalıdır **_lock_file** üzerinde önceden çağrıldı *dosya* işaretçi. Çağırma **_unlock_file** kilitli olmayan bir dosyada bir kilitlenmeye neden olabilir. Bir örnek için bkz: [_lock_file](lock-file.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_unlock_file**|\<stdio.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_lock_file](lock-file.md)<br/>
