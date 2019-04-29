---
title: _vcprintf_p, _vcprintf_p_l, _vcwprintf_p, _vcwprintf_p_l
ms.date: 11/04/2016
apiname:
- _vcprintf_p
- _vcwprintf_p_l
- _vcprintf_p_l
- _vcwprintf_p
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
apitype: DLLExport
f1_keywords:
- vcwprintf_p
- vcprintf_p_l
- _vcprintf_p
- _vcprintf_p_l
- vcwprintf_p_l
- vcprintf_p
- _vcwprintf_p
- _vcwprintf_p_l
helpviewer_keywords:
- _vtcprintf_p_l function
- vcprintf_p_l function
- _vcprintf_p_l function
- vtcprintf_p_l function
- vcprintf_p function
- _vcwprintf_p function
- _vcprintf_p function
- vcwprintf_p function
- vcwprintf_p_l function
- vtcprintf_p function
- _vcwprintf_p_l function
- _vtcprintf_p function
ms.assetid: 611024cc-90e7-41db-8e85-145ca95012b1
ms.openlocfilehash: 59e601d5cd03d58fe2d1725ba509a9fa3b2f3422
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62364891"
---
# <a name="vcprintfp-vcprintfpl-vcwprintfp-vcwprintfpl"></a>_vcprintf_p, _vcprintf_p_l, _vcwprintf_p, _vcwprintf_p_l

Bağımsız değişkenler listesine bir işaretçi kullanarak konsola biçimlendirilmiş çıktı yazar ve biçim dizesindeki konum parametrelerini destekler.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _vcprintf_p(
   const char* format,
   va_list argptr
);
int _vcprintf_p_l(
   const char* format,
   locale_t locale,
   va_list argptr
);
int _vcwprintf_p(
   const wchar_t* format,
   va_list argptr
);
int _vcwprintf_p_l(
   const wchar_t* format,
   locale_t locale,
   va_list argptr
);
```

### <a name="parameters"></a>Parametreler

*Biçim*<br/>
Biçim belirtimi.

*argptr*<br/>
Bağımsız değişkenler listesine bir işaretçi.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

Daha fazla bilgi için [biçim belirtim Sözdizimi: printf ve wprintf işlevleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="return-value"></a>Dönüş Değeri

Yazılan karakter sayısını veya bir hata oluştuğunda negatif bir değer. Varsa *biçimi* null bir işaretçiyse, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **errno** ayarlanır **EINVAL** ve -1 döndürülür.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri bağımsız değişken listesi için bir işaretçi alır ve ardından **_putch** biçimlendirir ve konsola verilen veri yazmak için işlevi. (**_vcwprintf_p** kullanan **_putwch** yerine **_putch**. **_vcwprintf_p** öğesinin geniş karakterli sürümüdür **_vcprintf_p**. İşlem bir geniş karakter dizesi bağımsız değişken olarak alır.)

Sahip bu işlevlerin sürümleri **_l** sonekine dışında geçerli yerel ayarı yerine iletilen yerel ayar parametresini kullanırlar.

Her *bağımsız değişken* (varsa) dönüştürülür ve karşılık gelen kapsamındaki biçim belirtimine göre çıkışı olan *biçimi*. Biçim belirtimi konumsal parametreleri destekler Biçim dizesinde bağımsız değişkenler kullanılan sırasını belirleyebilirsiniz. Daha fazla bilgi için [printf_p konumsal parametreler](../../c-runtime-library/printf-p-positional-parameters.md).

Çıkış olduklarında bu işlevlerin satır besleme karakterlerini satır başı satır besleme (CR-LF) birleşimlerine Çevir değil.

> [!IMPORTANT]
> Emin *biçimi* kullanıcı tanımlı bir dize değil. Daha fazla bilgi için [arabellek taşmalarını](/windows/desktop/SecBP/avoiding-buffer-overruns).

Bu işlevler giriş işaretleyicisini ve biçim dizesini doğrular. Varsa *biçimi* veya *bağımsız değişken* olduğu **NULL**, veya biçim dizesi geçersiz biçim karakterleri içeriyorsa, bu işlevler geçersiz parametre işleyicisi açıklandığı gibi çağırır içinde [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bu işlevler -1 döndürür ve **errno** için **EINVAL**.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_vtcprintf_p**|**_vcprintf_p**|**_vcprintf_p**|**_vcwprintf_p**|
|**_vtcprintf_p_l**|**_vcprintf_p_l**|**_vcprintf_p_l**|**_vcwprintf_p_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_vcprintf_p**, **_vcprintf_p_l**|\<conio.h > ve \<stdarg.h >|
|**_vcwprintf_p**, **_vcwprintf_p_l**|\<conio.h > ve \<stdarg.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_vcprintf_p.c
// compile with: /c
#include <conio.h>
#include <stdarg.h>

// An error formatting function that's used to print to the console.
int eprintf(const char* format, ...)
{
   va_list args;
   va_start(args, format);
   int result = _vcprintf_p(format, args);
   va_end(args);
   return result;
}

int main()
{
   int n = eprintf("parameter 2 = %2$d; parameter 1 = %1$s\r\n",
      "one", 222);
   _cprintf_s("%d characters printed\r\n");
}
```

```Output
parameter 2 = 222; parameter 1 = one
38 characters printed
```

## <a name="see-also"></a>Ayrıca bkz.

[Konsol ve bağlantı noktası g/ç](../../c-runtime-library/console-and-port-i-o.md)<br/>
[_cprintf, _cprintf_l, _cwprintf, _cwprintf_l](cprintf-cprintf-l-cwprintf-cwprintf-l.md)<br/>
[va_arg, va_copy, va_end, va_start](va-arg-va-copy-va-end-va-start.md)<br/>
[printf_p Konumsal Parametreler](../../c-runtime-library/printf-p-positional-parameters.md)<br/>
