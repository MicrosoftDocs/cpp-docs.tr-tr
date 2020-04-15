---
title: fsetpos
ms.date: 4/2/2020
api_name:
- fsetpos
- _o_fsetpos
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
- fsetpos
helpviewer_keywords:
- streams, setting position indicators
- fsetpos function
ms.assetid: 6d19ff48-1a2b-47b3-9f23-ed0a47b5a46e
ms.openlocfilehash: 22b8cebd0154c0dbfc3d21843380ebc9a139059a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345727"
---
# <a name="fsetpos"></a>fsetpos

Akış konumu göstergesini ayarlar.

## <a name="syntax"></a>Sözdizimi

```C
int fsetpos(
   FILE *stream,
   const fpos_t *pos
);
```

### <a name="parameters"></a>Parametreler

*Akışı*<br/>
**DOSYA** yapısı için işaretçi.

*Pos*<br/>
Konum göstergesi depolama.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, **fsetpos** 0 döndürür. Hata da, işlev sıfır olmayan bir değer döndürür ve **errno'yu** aşağıdaki bildirim sabitlerinden birine ayarlar (ERRNO'da tanımlanır). H): **EBADF**, dosyaya erişilemediğini veya *akış* konusuolan nesnenin geçerli bir dosya yapısı olmadığı anlamına gelir; veya **EINVAL**, *hangi akış* veya *pos* için geçersiz bir değer geçti anlamına gelir. Geçersiz bir parametre geçirilirse, bu işlevler [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır.

Bunlar ve diğer iade kodları hakkında daha fazla bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bakın.

## <a name="remarks"></a>Açıklamalar

**Fsetpos** işlevi, *akış* için dosya konumu göstergesini, *akışa*karşı **fgetpos'a** yapılan bir önceki çağrıda elde edilen *pos*değerine ayarlar. İşlev dosya sonu göstergesini temizler ve *akış*üzerindeki [ungetc'in](ungetc-ungetwc.md) herhangi bir etkisini geri alır. **fsetpos'u**aradıktan sonra, *akıştaki* bir sonraki işlem giriş veya çıktı olabilir.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fsetpos**|\<stdio.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

[Fgetpos](fgetpos.md)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Akış I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fgetpos](fgetpos.md)<br/>
