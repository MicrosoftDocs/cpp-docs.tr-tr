---
title: fsetpos | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- streams, setting position indicators
- fsetpos function
ms.assetid: 6d19ff48-1a2b-47b3-9f23-ed0a47b5a46e
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0ceacacbe029488995c47e305682b56751347591
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
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

*Akış*<br/>
İşaretçi **dosya** yapısı.

*POS*<br/>
Konum göstergesi depolama.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, **fsetpos** 0 döndürür. Hatada, işlevi sıfır olmayan bir değer döndürür ve ayarlar **errno** aşağıdakilerden birini bildirim Sabitleri (ERRNO içinde tanımlanmıştır. H): **EBADF**, yani dosya erişilebilir değil veya nesne, *akış* noktalarına geçerli dosya yapısı; değil veya **EINVAL**, için geçersiz bir değer anlamına gelir *akış* veya *pos* geçirildi. Geçersiz bir parametre geçtiyse, bu işlevler geçersiz parametre işleyicisi açıklandığı gibi çağırma [parametre doğrulaması](../../c-runtime-library/parameter-validation.md).

Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer hakkında daha fazla bilgi için dönüş kodları.

## <a name="remarks"></a>Açıklamalar

**Fsetpos** işlevi ayarlar için dosya konumu göstergesi *akış* değerine *pos*, önceki çağrıda elde **fgetpos**karşı *akış*. İşlev dosya sonu göstergesi temizler ve etkilerinin geri alır [ungetc](ungetc-ungetwc.md) üzerinde *akış*. Çağırdıktan sonra **fsetpos**, sonraki işlemi *akış* giriş çıkış ya da.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fsetpos**|\<stdio.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bkz [fgetpos](fgetpos.md).

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fgetpos](fgetpos.md)<br/>
