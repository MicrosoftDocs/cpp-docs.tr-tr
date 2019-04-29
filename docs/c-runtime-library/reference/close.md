---
title: _close
ms.date: 11/04/2016
apiname:
- _close
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _close
helpviewer_keywords:
- _close function
- close function
- files [C++], closing
ms.assetid: 4708a329-8acf-4cd9-b7b0-a952e1897247
ms.openlocfilehash: faea008903136e8abdc39297672b31800ada796d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62340020"
---
# <a name="close"></a>_close

Bir dosyayı kapatır.

## <a name="syntax"></a>Sözdizimi

```C
int _close(
   int fd
);
```

### <a name="parameters"></a>Parametreler

*FD*<br/>
Açık dosyaya başvuran dosya tanımlayıcısı.

## <a name="return-value"></a>Dönüş Değeri

**_close** dosya başarıyla kapattıysanız, 0 döndürür. -1 dönüş değeri bir hata olduğunu gösterir.

## <a name="remarks"></a>Açıklamalar

**_Close** işlevi, ilişkili dosyayı kapatır *fd*.

Dosya tanımlayıcısı ve temel alınan işletim sistemi dosya tanıtıcısı kapatılır. Bu nedenle, çağrı gerekli değildir **CloseHandle** Win32 işlevini kullanarak dosyanın ilk açıldığı varsa **CreateFile** kullanarak bir dosya tanımlayıcısı dönüştürülecek **_open_osfhandle**.

Bu işlev, parametrelerini doğrular. Varsa *fd* bir hatalı dosya tanımlayıcısı açıklandığı gibi geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse işlevler -1 döndürür ve **errno** ayarlanır **EBADF**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_close**|\<io.h >|\<errno.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bakın [_aç](open-wopen.md).

## <a name="see-also"></a>Ayrıca bkz.

[Düşük düzey g/ç](../../c-runtime-library/low-level-i-o.md)<br/>
[_chsize](chsize.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_dup, _dup2](dup-dup2.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_unlink, _wunlink](unlink-wunlink.md)<br/>
