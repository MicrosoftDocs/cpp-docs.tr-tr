---
title: _cputs, _cputws
ms.date: 4/2/2020
api_name:
- _cputws
- _cputs
- _o__cputs
- _o__cputws
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
- api-ms-win-crt-conio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- cputws
- _cputs
- _cputws
helpviewer_keywords:
- strings [C++], writing
- _cputs function
- _cputws function
- putting strings to the console
- cputs function
- console, sending strings to
- cputws function
ms.assetid: ec418484-0f8d-43ec-8d8b-198a556c659e
ms.openlocfilehash: 3b8f49fc7fbe90d4069a5dfeef9bbba3a7f05335
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348378"
---
# <a name="_cputs-_cputws"></a>_cputs, _cputws

Konsola bir dize koyar.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
int _cputs(
   const char *str
);
int _cputws(
   const wchar_t *str
);
```

### <a name="parameters"></a>Parametreler

*Str*<br/>
Çıkış dizesi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, **_cputs** 0 döndürür. İşlev başarısız olursa, sıfır olmayan bir değer döndürür.

## <a name="remarks"></a>Açıklamalar

**_cputs** işlevi, doğrudan konsola *str* tarafından işaret edilen null-sonlandırılan dizeyi yazar. Bir satır döndürme satırı beslemesi (CR-LF) birleşimi dize otomatik olarak eklenmiyor.

Bu işlev parametresini doğrular. *str* **NULL**ise, Geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmenin devam etmesine izin verilirse, **errno** **EINVAL** olarak ayarlanır ve -1 döndürülür.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_cputts**|**_cputs**|**_cputs**|**_cputws**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|---------------------|
|**_cputs**|\<conio.h>|\<errno.h>|
|**_cputws**|\<conio.h>|\<errno.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="libraries"></a>Kitaplıklar

C çalışma [zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="example"></a>Örnek

```C
// crt_cputs.c
// compile with: /c
// This program first displays a string to the console.

#include <conio.h>
#include <errno.h>

void print_to_console(char* buffer)
{
   int retval;
   retval = _cputs( buffer );
   if (retval)
   {
       if (errno == EINVAL)
       {
         _cputs( "Invalid buffer in print_to_console.\r\n");
       }
       else
         _cputs( "Unexpected error in print_to_console.\r\n");
   }
}

void wprint_to_console(wchar_t* wbuffer)
{
   int retval;
   retval = _cputws( wbuffer );
   if (retval)
   {
       if (errno == EINVAL)
       {
         _cputws( L"Invalid buffer in wprint_to_console.\r\n");
       }
       else
         _cputws( L"Unexpected error in wprint_to_console.\r\n");
   }
}

int main()
{

   // String to print at console.
   // Notice the \r (return) character.
   char* buffer = "Hello world (courtesy of _cputs)!\r\n";
   wchar_t *wbuffer = L"Hello world (courtesy of _cputws)!\r\n";
   print_to_console(buffer);
   wprint_to_console( wbuffer );
}
```

```Output
Hello world (courtesy of _cputs)!
Hello world (courtesy of _cputws)!
```

## <a name="see-also"></a>Ayrıca bkz.

[Konsol ve Bağlantı Noktası G/Ç](../../c-runtime-library/console-and-port-i-o.md)<br/>
[_putch, _putwch](putch-putwch.md)<br/>
