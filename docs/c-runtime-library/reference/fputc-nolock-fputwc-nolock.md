---
description: 'Hakkında daha fazla bilgi edinin: _fputc_nolock _fputwc_nolock'
title: _fputc_nolock, _fputwc_nolock
ms.date: 4/2/2020
api_name:
- _fputwc_nolock
- _fputc_nolock
- _o__fputc_nolock
- _o__fputwc_nolock
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
- _fputc_nolock
- fputwc_nolock
- fputc_nolock
- fputtc_nolock
- _fputwc_nolock
- _fputtc_nolock
helpviewer_keywords:
- streams, writing characters to
- fputwc_nolock function
- fputtc_nolock function
- _fputc_nolock function
- fputc_nolock function
- _fputtc_nolock function
- _fputwc_nolock function
ms.assetid: c63eb3ad-58fa-46d0-9249-9c25f815eab9
ms.openlocfilehash: c9070f641fce2acbd584ef75f6209464f3e90130
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314170"
---
# <a name="_fputc_nolock-_fputwc_nolock"></a>_fputc_nolock, _fputwc_nolock

İş parçacığını kilitlemeden akışa bir karakter yazar.

## <a name="syntax"></a>Sözdizimi

```C
int _fputc_nolock(
   int c,
   FILE *stream
);
wint_t _fputwc_nolock(
   wchar_t c,
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*,*<br/>
Yazılacak karakter.

*ka*<br/>
**Dosya** yapısına yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri yazılan karakteri döndürür. Hata bilgileri için bkz. [fputc, fputwc](fputc-fputwc.md).

## <a name="remarks"></a>Açıklamalar

**_fputc_nolock** ve **_fputwc_nolock** , sırasıyla **fputc** ve **fputwc** ile aynıdır, ancak diğer iş parçacıkları tarafından girişim tarafından korunmazlar. Diğer iş parçacıklarını kilitleme yükünü sunmadığından daha hızlı olabilir. Bu işlevleri yalnızca, tek iş parçacıklı uygulamalar gibi iş parçacığı güvenli bağlamlarda veya çağırma kapsamının iş parçacığı yalıtımını zaten işlediği yerde kullanın.

Akış ANSI modunda açılırsa iki işlev aynı şekilde davranır. **_fputc_nolock** , şu anda UNICODE bir akışa çıktıyı desteklemez.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_fputtc_nolock**|**_fputc_nolock**|**_fputc_nolock**|**_fputwc_nolock**|

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fputc_nolock**|\<stdio.h>|
|**_fputwc_nolock**|\<stdio.h> veya \<wchar.h>|

Konsol Evrensel Windows Platformu (UWP) uygulamalarında desteklenmez. Bu konsol ile ilişkili standart akış tutamaçları (**stdin**, **stdout** ve **stderr**), C çalışma zamanı işlevlerinin bunları UWP uygulamalarında kullanabilmesi için yeniden yönlendirilmelidir. Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_fputc_nolock.c
// This program uses _fputc_nolock
// to send a character array to stdout.

#include <stdio.h>

int main( void )
{
   char strptr1[] = "This is a test of _fputc_nolock!!\n";
   char *p;

   // Print line to stream using fputc.
   p = strptr1;
   while( (*p != '\0') && _fputc_nolock( *(p++), stdout ) != EOF ) ;

}
```

```Output
This is a test of _fputc_nolock!!
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış G/Ç](../../c-runtime-library/stream-i-o.md)<br/>
[fgetc, fgetwc](fgetc-fgetwc.md)<br/>
[putc, putwc](putc-putwc.md)<br/>
