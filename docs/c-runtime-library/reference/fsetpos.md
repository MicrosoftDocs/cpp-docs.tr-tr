---
title: fsetpos | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 483cf151374c1c3a03e53e49ce67a00a148406fd
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="fsetpos"></a>fsetpos
Akış konumu göstergesi ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int fsetpos(   
   FILE *stream,  
   const fpos_t *pos   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `stream`  
 İşaretçi `FILE` yapısı.  
  
 `pos`  
 Konum göstergesi depolama.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, `fsetpos` 0 döndürür. Hatada, işlevi sıfır olmayan bir değer döndürür ve ayarlar `errno` aşağıdakilerden birini bildirim Sabitleri (ERRNO içinde tanımlanmıştır. H): `EBADF`, yani dosya erişilebilir değil veya nesne, `stream` noktalarına geçerli dosya yapısı; değil veya `EINVAL`, için geçersiz bir değer anlamına gelir `stream` veya `pos` geçirildi. Geçersiz bir parametre geçtiyse, bu işlevler geçersiz parametre işleyicisi açıklandığı gibi çağırma [parametre doğrulaması](../../c-runtime-library/parameter-validation.md).  
  
 Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer hakkında daha fazla bilgi için dönüş kodları.  
  
## <a name="remarks"></a>Açıklamalar  
 `fsetpos` İşlevi ayarlar için dosya konumu göstergesi `stream` değerine `pos`, önceki çağrıda elde `fgetpos` karşı `stream`. İşlev dosya sonu göstergesi temizler ve etkilerinin geri alır [ungetc](../../c-runtime-library/reference/ungetc-ungetwc.md) üzerinde `stream`. Çağırdıktan sonra `fsetpos`, sonraki işlemi `stream` giriş çıkış ya da.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|Gerekli başlık|  
|--------------|---------------------|  
|`fsetpos`|\<stdio.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [fgetpos](../../c-runtime-library/reference/fgetpos.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış g/ç](../../c-runtime-library/stream-i-o.md)   
 [fgetpos](../../c-runtime-library/reference/fgetpos.md)