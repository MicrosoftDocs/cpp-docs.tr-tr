---
title: fsetpos
ms.date: 11/04/2016
apiname:
- fsetpos
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
- fsetpos
helpviewer_keywords:
- streams, setting position indicators
- fsetpos function
ms.assetid: 6d19ff48-1a2b-47b3-9f23-ed0a47b5a46e
ms.openlocfilehash: 9854c71e381da6ec9a75d440b9588e2476bada7c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287579"
---
# <a name="fsetpos"></a>fsetpos

Akış konumu göstergesi ayarlar.

## <a name="syntax"></a>Sözdizimi

```C
int fsetpos(
   FILE *stream,
   const fpos_t *pos
);
```

### <a name="parameters"></a>Parametreler

*Stream*<br/>
İşaretçi **dosya** yapısı.

*POS*<br/>
Depolama konumu göstergesi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, **fsetpos** 0 döndürür. Hata olduğunda, işlev sıfır olmayan bir değer döndürür ve ayarlar **errno** aşağıdakilerden birini bildirim Sabitleri (ERRNO içinde tanımlanır. H): **EBADF**, yani dosya erişilebilir değil veya nesne, *stream* noktalarına geçerli dosya yapısı; değil veya **EINVAL**, için geçersiz bir değer anlamına gelir *akış*  veya *pos* geçirildi. Geçersiz bir parametre olarak geçirilir, bu işlevler geçersiz parametre işleyicisi içinde açıklanan şekilde çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md).

Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer hakkında daha fazla bilgi için dönüş kodları.

## <a name="remarks"></a>Açıklamalar

**Fsetpos** işlevi ayarlar için dosya konumu göstergesi *stream* değerine *pos*, önceki çağrıda elde **fgetpos**karşı *stream*. İşlev dosya sonu göstergesini temizler ve herhangi bir etkilerini geri alır [ungetc](ungetc-ungetwc.md) üzerinde *stream*. Arama sonra **fsetpos**, sonraki işlemi *stream* giriş çıkış veya.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fsetpos**|\<stdio.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bakın [fgetpos](fgetpos.md).

## <a name="see-also"></a>Ayrıca bkz.

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fgetpos](fgetpos.md)<br/>
