---
title: fsetpos
ms.date: 11/04/2016
api_name:
- fsetpos
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
ms.openlocfilehash: f44ab1b35c9e598f82dbc0af96979476ee353541
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70956517"
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

*ka*<br/>
**Dosya** yapısına yönelik işaretçi.

*'un*<br/>
Konum göstergesi depolaması.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa **fsetpos** 0 döndürür. Hata durumunda, işlev sıfır dışında bir değer döndürür ve **errno** değerini aşağıdaki bildirim sabitlerinden birine ayarlar (errno içinde tanımlanmıştır). H): **EBADF**, dosyanın erişilemeyen veya *akışın* işaret ettiği nesnenin geçerli bir dosya yapısı olmadığı anlamına gelir; veya **EINVAL**, yani *Stream* veya *POS* için geçersiz bir değer geçildi. Geçersiz bir parametre geçirilirse, bu işlevler [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır.

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) .

## <a name="remarks"></a>Açıklamalar

**Fsetpos** işlevi, *akış için dosya* konumu göstergesini, **fgetpos** 'un *akışa*karşı önceki çağrısında elde edilen *POS*değerine ayarlar. İşlevi dosya sonu göstergesini temizler ve *Stream*üzerinde [ungetc](ungetc-ungetwc.md) 'nin tüm etkilerini geri alır. **Fsetpos**çağrıldıktan sonra *akıştaki* bir sonraki işlem girdi ya da çıktı olabilir.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fsetpos**|\<stdio. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[Fgetpos](fgetpos.md)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fgetpos](fgetpos.md)<br/>
