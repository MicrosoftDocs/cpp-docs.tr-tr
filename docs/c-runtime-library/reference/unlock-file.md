---
title: _unlock_file
ms.date: 4/2/2020
api_name:
- _unlock_file
- _o__unlock_file
api_location:
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _unlock_file
- unlock_file
helpviewer_keywords:
- files [C++], unlocking
- unlock_file function
- _unlock_file function
- unlocking files
ms.assetid: cf380a51-6d3a-4f38-bd64-2d4fb57b4369
ms.openlocfilehash: ed79f66baebf71c89e537c8343779bef44ebfbb8
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82909200"
---
# <a name="_unlock_file"></a>_unlock_file

Bir dosyanın kilidini açarak diğer işlemlerin dosyaya erişmesine izin verir.

## <a name="syntax"></a>Sözdizimi

```C
void _unlock_file(
   FILE* file
);
```

### <a name="parameters"></a>Parametreler

*dosyasýný*<br/>
Dosya tanıtıcısı.

## <a name="remarks"></a>Açıklamalar

**_Unlock_file** işlevi *Dosya*tarafından belirtilen dosyanın kilidini açar. Bir dosyanın kilidini açmak, diğer işlemlere göre dosyaya erişim sağlar. Bu işlev, **_lock_file** daha önce *Dosya* İşaretçisinde çağrılmadığı müddetçe çağrılmamalıdır. Kilitli olmayan bir dosyada **_unlock_file** çağırmak kilitlenmeye neden olabilir. Bir örnek için bkz. [_lock_file](lock-file.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_unlock_file**|\<stdio. h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dosya IŞLEME](../../c-runtime-library/file-handling.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_lock_file](lock-file.md)<br/>
