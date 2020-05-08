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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 8fa6ec1f37703ce51e0c9c565d766c56cf164322
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82910175"
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

Başarılı olursa **fsetpos** 0 döndürür. Hata durumunda, işlev sıfır dışında bir değer döndürür ve **errno** değerini aşağıdaki bildirim sabitlerinden birine ayarlar (errno içinde tanımlanmıştır). H): **EBADF**, dosyanın erişilebilir olmadığı veya *akışın* işaret ettiği nesnenin geçerli bir dosya yapısı olmadığı anlamına gelir; veya **EINVAL**, yani *Stream* veya *POS* için geçersiz bir değer geçildi. Geçersiz bir parametre geçirilirse, bu işlevler [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır.

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) .

## <a name="remarks"></a>Açıklamalar

**Fsetpos** işlevi, *akış için dosya* konumu göstergesini, **fgetpos** 'un *akışa*karşı önceki çağrısında elde edilen *POS*değerine ayarlar. İşlevi dosya sonu göstergesini temizler ve *Stream*üzerinde [ungetc](ungetc-ungetwc.md) 'nin tüm etkilerini geri alır. **Fsetpos**çağrıldıktan sonra *akıştaki* bir sonraki işlem girdi ya da çıktı olabilir.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fsetpos**|\<stdio. h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[Fgetpos](fgetpos.md)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fgetpos](fgetpos.md)<br/>
