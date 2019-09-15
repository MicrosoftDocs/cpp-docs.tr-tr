---
title: _unlock_file
ms.date: 11/04/2016
api_name:
- _unlock_file
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
ms.openlocfilehash: 2983408f066ea00c0b7ab111d9a6349700ecaece
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957485"
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

**_Unlock_ın** işlevi *Dosya*tarafından belirtilen dosyanın kilidini açar. Bir dosyanın kilidini açmak, diğer işlemlere göre dosyaya erişim sağlar. Bu işlev, **_lock_file** , daha önce *Dosya* işaretçisi üzerinde çağrılmadığı müddetçe çağrılmamalıdır. Kilitli olmayan bir dosyada **_unlock_unlock_fıle** çağrısı kilitlenmeye neden olabilir. Bir örnek için bkz. [_lock_.](lock-file.md)

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_unlock_file**|\<stdio. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_lock_file](lock-file.md)<br/>
