---
description: 'Daha fazla bilgi edinin: fkoyar, fputws'
title: fputs, fputws
ms.date: 4/2/2020
api_name:
- fputs
- fputws
- _o_fputs
- _o_fputws
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
- fputs
- fputws
- _fputts
helpviewer_keywords:
- streams, writing strings to
- fputws function
- _fputts function
- fputs function
- fputts function
ms.assetid: d48c82b8-aa17-4830-8c7d-30442ddbb326
ms.openlocfilehash: bba51a6001d9ec27f39b590b2246a50409f5e47d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314119"
---
# <a name="fputs-fputws"></a>fputs, fputws

Akışa bir dize yazar.

## <a name="syntax"></a>Sözdizimi

```C
int fputs(
   const char *str,
   FILE *stream
);
int fputws(
   const wchar_t *str,
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*<br/>
Çıkış dizesi.

*ka*<br/>
**Dosya** yapısına yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri, başarılı olursa negatif olmayan bir değer döndürür. Bir hatada, **ffıler** ve **fputws** , **EOF** döndürür. *Str* veya *Stream* null bir işaretçisiyse, bu işlevler [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **errno** ' ı **EINVAL** olarak ayarlar ve **sonra da** ,  **fputws** , **fıof** öğesini döndürür.

Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) .

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri *Str* geçerli konumdaki çıkış *akışına* kopyalar. **fputws** , geniş karakterli bağımsız değişken *Str* 'yi çok baytlı bir karakter dizesi olarak *akışa* veya bir geniş karakterli dizeyi sırasıyla metin modunda veya ikili *modda açılıp açılmayacağı şekilde* kopyalar. Ne işlevi, Sonlandırıcı null karakterini kopyalar.

Akış ANSI modunda açılırsa iki işlev aynı şekilde davranır. **fler** Şu anda bir UNICODE akışına çıktıyı desteklemez.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_fputts**|**fkoyar**|**fkoyar**|**fputws**|

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fkoyar**|\<stdio.h>|
|**fputws**|\<stdio.h> veya \<wchar.h>|

Konsol Evrensel Windows Platformu (UWP) uygulamalarında desteklenmez. Bu konsol ile ilişkili standart akış tutamaçları (**stdin**, **stdout** ve **stderr**), C çalışma zamanı işlevlerinin bunları UWP uygulamalarında kullanabilmesi için yeniden yönlendirilmelidir. Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_fputs.c
// This program uses fputs to write
// a single line to the stdout stream.

#include <stdio.h>

int main( void )
{
   fputs( "Hello world from fputs.\n", stdout );
}
```

```Output
Hello world from fputs.
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış G/Ç](../../c-runtime-library/stream-i-o.md)<br/>
[fgets, fgetws](fgets-fgetws.md)<br/>
[gets, _getws](../../c-runtime-library/gets-getws.md)<br/>
[puts, _putws](puts-putws.md)<br/>
