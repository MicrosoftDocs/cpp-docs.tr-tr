---
title: puts, _putws
ms.date: 4/2/2020
api_name:
- _putws
- puts
- _o__putws
- _o_puts
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
- _putts
- _putws
- puts
helpviewer_keywords:
- strings [C++], writing
- _putts function
- standard output, writing to
- putws function
- puts function
- putts function
- _putws function
ms.assetid: 32dada12-ed45-40ac-be06-3feeced9ecd6
ms.openlocfilehash: 9681373ccf338daf05be3120fbadd39ba471e86a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332955"
---
# <a name="puts-_putws"></a>puts, _putws

**Stdout**için bir dize yazar.

## <a name="syntax"></a>Sözdizimi

```C
int puts(
   const char *str
);
int _putws(
   const wchar_t *str
);
```

### <a name="parameters"></a>Parametreler

*Str*<br/>
Çıkış dizesi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa negatif olmayan bir değer verir. **Koyar** başarısız olursa, **EOF**döndürür; **_putws** başarısız olursa, **WEOF**döndürür. *Str* null işaretçisi ise, Geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütme devam etmesine izin verilirse, işlevleri **EINVAL** **için errno** ayarlayın ve **EOF** veya **WEOF**dönmek.

Bu ve diğer hata kodları hakkında bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)bakın.

## <a name="remarks"></a>Açıklamalar

**Koyar** işlevi, dize sonlandırıcı null karakterini ('\0') çıkış akışındaki yeni bir çizgi karakteriyle ('\n') değiştirerek standart çıkış **akışına** *str* yazar.

**_putws** **koyar**geniş karakterli versiyonudur; akış ANSI modunda açıldığında iki işlev aynı şekilde çalışır. **koyar** şu anda bir UNICODE akışına çıktı desteklemiyor.

**_putwch** geçerli CONSOLE LOCALE ayarını kullanarak Unicode karakterleri yazar.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_putts**|**Koyar**|**Koyar**|**_putws**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**Koyar**|\<stdio.h>|
|**_putws**|\<stdio.h>|

Konsol, Evrensel Windows Platformu (UWP) uygulamalarında desteklenmez. Konsol, **stdin,** **stdout**ve **stderr**ile ilişkili standart akış kolları, C çalışma zamanı işlevleri UWP uygulamalarında bunları kullanamadan önce yönlendirilmelidir. Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="libraries"></a>Kitaplıklar

C çalışma [zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="example"></a>Örnek

```C
// crt_puts.c
// This program uses puts to write a string to stdout.

#include <stdio.h>

int main( void )
{
   puts( "Hello world from puts!" );
}
```

### <a name="output"></a>Çıktı

```Output
Hello world from puts!
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fputs, fputws](fputs-fputws.md)<br/>
[fgets, fgetws](fgets-fgetws.md)<br/>
