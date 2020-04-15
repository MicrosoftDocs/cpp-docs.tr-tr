---
title: _close
ms.date: 4/2/2020
api_name:
- _close
- _o__close
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
- _close
helpviewer_keywords:
- _close function
- close function
- files [C++], closing
ms.assetid: 4708a329-8acf-4cd9-b7b0-a952e1897247
ms.openlocfilehash: 4d8b702a10624ae80629b4ce4644c428322500cb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348653"
---
# <a name="_close"></a>_close

Bir dosyayı kapatır.

## <a name="syntax"></a>Sözdizimi

```C
int _close(
   int fd
);
```

### <a name="parameters"></a>Parametreler

*Fd*<br/>
Açık dosyaya atıfta bulunan dosya tanımlayıcısı.

## <a name="return-value"></a>Dönüş Değeri

dosya başarıyla kapatılırsa **_close** 0 döndürür. -1'in geri dönüş değeri bir hatayı gösterir.

## <a name="remarks"></a>Açıklamalar

**_close** işlevi *fd*ile ilişkili dosyayı kapatır.

Dosya tanımlayıcısı ve altta yatan işletim sistemi dosya tutamacı kapatılır. Bu nedenle, dosya win32 işlevi **CreateFile** kullanılarak ilk olarak açıldı ve **_open_osfhandle**kullanarak bir dosya tanımlayıcısına dönüştürüldüyse **CloseHandle'ı** aramak gerekli değildir.

Bu işlev parametrelerini doğrular. *fD* hatalı bir dosya tanımlayıcısı ise, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütme devam etmesine izin verilirse, işlevleri -1 döndürür ve **errno** **EBADF**ayarlanır.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|---------------------|
|**_close**|\<io.h>|\<errno.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

[_open](open-wopen.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Düşük Seviyeli G/Ç](../../c-runtime-library/low-level-i-o.md)<br/>
[_chsize](chsize.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_dup, _dup2](dup-dup2.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_unlink, _wunlink](unlink-wunlink.md)<br/>
