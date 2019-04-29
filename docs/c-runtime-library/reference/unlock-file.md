---
title: _unlock_file
ms.date: 11/04/2016
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
helpviewer_keywords:
- files [C++], unlocking
- unlock_file function
- _unlock_file function
- unlocking files
ms.assetid: cf380a51-6d3a-4f38-bd64-2d4fb57b4369
ms.openlocfilehash: e3d11cbd59ef5846b33908ae6b6c40d7ea6125e8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353553"
---
# <a name="unlockfile"></a>_unlock_file

Dosyaya erişmek diğer işlemlere izin verme, bir dosyanın kilidini açar.

## <a name="syntax"></a>Sözdizimi

```C
void _unlock_file(
   FILE* file
);
```

### <a name="parameters"></a>Parametreler

*Dosya*<br/>
Dosya tanıtıcısı.

## <a name="remarks"></a>Açıklamalar

**_Unlock_file** işlevi tarafından belirtilen dosyanın kilidini açarak *dosya*. Bir dosyanın kilidini başka işlemler tarafından dosyaya erişim sağlar. Bu işlev sürece çağrılmamalıdır **_lock_file** üzerinde daha önceden çağrıldığından *dosya* işaretçi. Çağırma **_unlock_file** kilitli olmayan bir dosyada bir kilitlenmeyle neden olabilir. Bir örnek için bkz. [_lock_file](lock-file.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_unlock_file**|\<stdio.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_lock_file](lock-file.md)<br/>
