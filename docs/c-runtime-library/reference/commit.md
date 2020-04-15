---
title: _commit
ms.date: 4/2/2020
api_name:
- _commit
- _o__commit
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _commit
- commit
helpviewer_keywords:
- files [C++], flushing
- flushing files to disk
- commit function
- _commit function
- committing files to disk
ms.assetid: d0c74d3a-4f2d-4fb0-b140-2d687db3d233
ms.openlocfilehash: f8e13e7fc197c66395556d518ecbd1cd20ac1f77
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348624"
---
# <a name="_commit"></a>_commit

Bir dosyayı doğrudan diske temizler.

## <a name="syntax"></a>Sözdizimi

```C
int _commit(
   int fd
);
```

### <a name="parameters"></a>Parametreler

*Fd*<br/>
Açık dosyaya atıfta bulunan dosya tanımlayıcısı.

## <a name="return-value"></a>Dönüş Değeri

**_commit,** dosya başarıyla diske doğru kızartılırsa 0 döndürür. -1'in geri dönüş değeri bir hatayı gösterir.

## <a name="remarks"></a>Açıklamalar

**_commit** işlevi, işletim sistemini *fd* ile ilişkili dosyayı diske yazmaya zorlar. Bu arama, belirtilen dosyanın işletim sisteminin takdirine bağlı olarak değil, hemen temizlenmesini sağlar.

*FD* geçersiz bir dosya tanımlayıcısı ise, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmedevam etmesine izin verilirse, işlev -1 döndürür ve **errno** **EBADF**olarak ayarlanır.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|----------------------|
|**_commit**|\<io.h>|\<errno.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Düşük Seviyeli G/Ç](../../c-runtime-library/low-level-i-o.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_read](read.md)<br/>
[_write](write.md)<br/>
