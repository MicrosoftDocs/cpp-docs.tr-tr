---
title: vsnprintf_s, _vsnprintf_s, _vsnprintf_s_l, _vsnwprintf_s, _vsnwprintf_s_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _vsnwprintf_s
- _vsnwprintf_s_l
- _vsnprintf_s
- vsnprintf_s
- _vsnprintf_s_l
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
- ntdll.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- _vsnprintf_s
- _vsntprintf_s
- _vsnwprintf_s
dev_langs:
- C++
helpviewer_keywords:
- vsnwprintf_s function
- _vsntprintf_s function
- _vsntprintf_s_l function
- vsntprintf_s function
- vsnwprintf_s_l function
- vsnprintf_s_l function
- vsntprintf_s_l function
- _vsnwprintf_s_l function
- _vsnprintf_s function
- vsnprintf_s function
- _vsnprintf_s_l function
- _vsnwprintf_s function
- formatted text [C++]
ms.assetid: 147ccfce-58c7-4681-a726-ef54ac1c604e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 66fd7c468e516c25e2c2b408b8c1112061eeb5e0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32417948"
---
# <a name="vsnprintfs-vsnprintfs-vsnprintfsl-vsnwprintfs-vsnwprintfsl"></a>vsnprintf_s, _vsnprintf_s, _vsnprintf_s_l, _vsnwprintf_s, _vsnwprintf_s_l

Bir işaretçi bağımsız değişken listesini kullanarak biçimlendirilmiş çıktı yazma. Sürümleri bunlar [vsnprintf, _vsnprintf, _vsnprintf_l, _vsnwprintf, _vsnwprintf_l](vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Sözdizimi

```C
int vsnprintf_s(
   char *buffer,
   size_t sizeOfBuffer,
   size_t count,
   const char *format,
   va_list argptr
);
int _vsnprintf_s(
   char *buffer,
   size_t sizeOfBuffer,
   size_t count,
   const char *format,
   va_list argptr
);
int _vsnprintf_s_l(
   char *buffer,
   size_t sizeOfBuffer,
   size_t count,
   const char *format,
   locale_t locale,
   va_list argptr
);
int _vsnwprintf_s(
   wchar_t *buffer,
   size_t sizeOfBuffer,
   size_t count,
   const wchar_t *format,
   va_list argptr
);
int _vsnwprintf_s_l(
   wchar_t *buffer,
   size_t sizeOfBuffer,
   size_t count,
   const wchar_t *format,
   locale_t locale,
   va_list argptr
);
template <size_t size>
int _vsnprintf_s(
   char (&buffer)[size],
   size_t count,
   const char *format,
   va_list argptr
); // C++ only
template <size_t size>
int _vsnwprintf_s(
   wchar_t (&buffer)[size],
   size_t count,
   const wchar_t *format,
   va_list argptr
); // C++ only
```

### <a name="parameters"></a>Parametreler

*Arabellek*<br/>
Çıktı için depolama konumu.

*sizeOfBuffer*<br/>
Boyutunu *arabellek* karakter sayısı olarak çıktı.

*Sayısı*<br/>
(Sonlandırma null dahil değil), yazmak için karakter üst sınırını veya [_TRUNCATE](../../c-runtime-library/truncate.md).

*Biçimi*<br/>
Biçim belirtimi.

*argptr*<br/>
İşaretçi bağımsız değişken listesi.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

Daha fazla bilgi için bkz: [biçim belirtimleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="return-value"></a>Dönüş Değeri

**vsnprintf_s**, **_vsnprintf_s** ve **_vsnwprintf_s** çıkış hata oluşursa sonlandırma null veya negatif bir değer içermeyen yazılan karakterlerin sayısını döndürür. **vsnprintf_s** aynıdır **_vsnprintf_s**. **vsnprintf_s** ANSI standart uyumluluk için bulunmaktadır. **_vnsprintf** geriye dönük uyumluluk için tutulmaktadır.

Veri ve bir sonlandırma null depolamak için gerekli depolama aşarsa *sizeOfBuffer*, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md)sürece *sayısı*  olan [_TRUNCATE](../../c-runtime-library/truncate.md), bu durumda büyük bir dize olarak uygun *arabellek* yazılır ve döndürülen -1. Geçersiz parametre işleyicisi sonra yürütme devam ederse, bu işlevler kümesi *arabellek* boş bir dize olarak ayarlayın **errno** için **ERANGE**ve -1 döndürür.

Varsa *arabellek* veya *biçimi* olan bir **NULL** işaretçisi veya *sayısı* küçük veya ona eşit sıfır olarak geçersiz parametre işleyicisi çağrılır. Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler kümesi **errno** için **EINVAL** ve -1 döndürür.

### <a name="error-conditions"></a>Hata koşulları

|**Koşul**|Döndür|**errno**|
|-----------------|------------|-------------|
|*Arabellek* olan **NULL**|-1|**EINVAL**|
|*Biçim* olan **NULL**|-1|**EINVAL**|
|*Count* < = 0|-1|**EINVAL**|
|*sizeOfBuffer* çok küçük (ve *sayısı* ! = **_TRUNCATE**)|-1 (ve *arabellek* boş bir dize olarak ayarlayın)|**ERANGE**|

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri bir bağımsız değişken listesi için bir işaretçi alır sonra biçimlendirir ve en fazla Yazar *sayısı* tarafından verilen verileri belleğe karakterlerinden işaret için *arabellek* ve bir sonlandırma null ekler.

Varsa *sayısı* olan [_TRUNCATE](../../c-runtime-library/truncate.md), daha uygun şekilde dize olarak bu işlevler yazma sonra *arabellek* sonlandırma null yer bırakarak oluştu. Varsa tüm dizesiyle (sonlandırma null) sığacak *arabellek*, sonra bu işlevler (sonlandırma null dahil değil) yazılmış karakterlerin sayısını döndürür; Aksi takdirde, bu işlevler, kesme belirtmek için -1 Döndür oluştu.

Bu işlevleri sürümlerini **_l** soneki, geçerli iş parçacığı yerel ayar yerine geçirilen yerel ayar parametresi kullanmasını dışında aynıdır.

> [!IMPORTANT]
> Emin *biçimi* kullanıcı tanımlı bir dize değil. Daha fazla bilgi için bkz: [önleme arabellek taşmasına neden](http://msdn.microsoft.com/library/windows/desktop/ms717795).

> [!NOTE]
> Sonlandırma boş yer olduğundan emin olmak için olduğundan emin olun *sayısı* arabellek uzunluğundan ya da kullanım değerinden kesinlikle küçük olan **_TRUNCATE**.

C++'da, bu işlevler kullanılarak şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı arabellek uzunluğu otomatik olarak Infer (boyutu bağımsız değişkeniyle belirtme ihtiyacını ortadan) ve bunlar otomatik olarak yeni, güvenli dekiler ile daha eski, güvenli olmayan işlevleri değiştirebilirsiniz. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vsntprintf_s**|**_vsnprintf_s**|**_vsnprintf_s**|**_vsnwprintf_s**|
|**_vsntprintf_s_l**|**_vsnprintf_s_l**|**_vsnprintf_s_l**|**_vsnwprintf_s_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|----------------------|
|**vsnprintf_s**|\<stdio.h > ve \<stdarg.h >|\<VarArgs.h > *|
|**_vsnprintf_s**, **_vsnprintf_s_l**|\<stdio.h > ve \<stdarg.h >|\<VarArgs.h > *|
|**_vsnwprintf_s**, **_vsnwprintf_s_l**|\<stdio.h > veya \<wchar.h >, ve \<stdarg.h >|\<VarArgs.h > *|

\* UNIX V uyumluluk için gereklidir.

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```cpp
// crt_vsnprintf_s.cpp
#include <stdio.h>
#include <wtypes.h>

void FormatOutput(LPCSTR formatstring, ...)
{
   int nSize = 0;
   char buff[10];
   memset(buff, 0, sizeof(buff));
   va_list args;
   va_start(args, formatstring);
   nSize = vsnprintf_s( buff, _countof(buff), _TRUNCATE, formatstring, args);
   printf("nSize: %d, buff: %s\n", nSize, buff);
   va_end(args);
}

int main() {
   FormatOutput("%s %s", "Hi", "there");
   FormatOutput("%s %s", "Hi", "there!");
   FormatOutput("%s %s", "Hi", "there!!");
}
```

```Output
nSize: 8, buff: Hi there
nSize: 9, buff: Hi there!
nSize: -1, buff: Hi there!
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[vprintf İşlevleri](../../c-runtime-library/vprintf-functions.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[va_arg, va_copy, va_end, va_start](va-arg-va-copy-va-end-va-start.md)<br/>
