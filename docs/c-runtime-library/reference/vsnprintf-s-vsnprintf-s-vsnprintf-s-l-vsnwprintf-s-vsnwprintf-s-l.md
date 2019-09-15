---
title: vsnprintf_s, _vsnprintf_s, _vsnprintf_s_l, _vsnwprintf_s, _vsnwprintf_s_l
ms.date: 11/04/2016
api_name:
- _vsnwprintf_s
- _vsnwprintf_s_l
- _vsnprintf_s
- vsnprintf_s
- _vsnprintf_s_l
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
- ntdll.dll
- ucrtbase.dll
- ntoskrnl.exe
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _vsnprintf_s
- _vsntprintf_s
- _vsnwprintf_s
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
ms.openlocfilehash: 8c41a09ce35819403b2361dcf5ad53eb93b7a615
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70945284"
---
# <a name="vsnprintf_s-_vsnprintf_s-_vsnprintf_s_l-_vsnwprintf_s-_vsnwprintf_s_l"></a>vsnprintf_s, _vsnprintf_s, _vsnprintf_s_l, _vsnwprintf_s, _vsnwprintf_s_l

Bağımsız değişken listesi için bir işaretçi kullanarak biçimli çıktı yazın. Bu sürümler, [CRT 'Deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi, [vsnprintf, _vsnprintf, _vsnprintf_l, _vsnwprintf, _vsnwprintf_l](vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md) güvenlik geliştirmeleriyle ilgili sürümleridir.

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

*arabelleğin*<br/>
Çıktı için depolama konumu.

*sizeOfBuffer*<br/>
Çıkış *arabelleğinin* karakter sayısı olarak boyutu.

*biriktirme*<br/>
Yazılacak maksimum karakter sayısı (Sonlandırıcı null değeri dahil değil) veya [_Truncate](../../c-runtime-library/truncate.md).

*format*<br/>
Biçim belirtimi.

*argptr*<br/>
Bağımsız değişken listesi işaretçisi.

*ayarlar*<br/>
Kullanılacak yerel ayar.

Daha fazla bilgi için bkz. [Biçim belirtimleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="return-value"></a>Dönüş Değeri

**vsnprintf_s**, **_vsnprintf_s** ve **_vsnwprintf_s** , yazılan karakterlerin sayısını, Sonlandırıcı null değerini veya bir çıkış hatası oluşursa negatif bir değeri döndürür. **vsnprintf_s** , **_vsnprintf_s**ile aynıdır. **vsnprintf_s** , ANSI standardına uyum sağlamak için eklenmiştir. **_vnsprintf** geriye dönük uyumluluk için tutulur.

Verileri depolamak için gereken depolama alanı ve bir Sonlandırıcı null değeri *sizeOfBuffer*değerini aşarsa, *Count* [_TRUNCATE](../../c-runtime-library/truncate.md)olmadığı [sürece, bu](../../c-runtime-library/parameter-validation.md)durumda *arabelleğe* sığacak şekilde dize yazılır ve-1 döndürülür. Yürütme geçersiz parametre işleyiciden sonra devam ediyorsa, bu işlevler *arabelleği* boş bir dizeye ayarlar, **errno** , **ERANGE**ayarla ve-1 döndürür.

*Arabellek* veya *Biçim* **null** işaretçisiyse veya *sayı* sıfırdan küçükse veya eşitse, geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **errno** olarak **EINVAL** ve-1 döndürür.

### <a name="error-conditions"></a>Hata koşulları

|**Koşul**|döndürülmesini|**errno**|
|-----------------|------------|-------------|
|*arabellek* **null**|-1|**EINVAL**|
|*Biçim* **null**|-1|**EINVAL**|
|*sayı* < = 0|-1|**EINVAL**|
|*sizeOfBuffer* çok küçük (ve *Count* ! = **_TRUNCATE**)|-1 (ve *arabellek* boş bir dizeye ayarlanmış)|**ERANGE**|

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri bağımsız değişken listesi için bir işaretçi alır, ardından, belirtilen verilerin karakter *sayısını* *arabelleğe* göre işaret eden belleğe göre biçimlendirir ve yazar ve bir Sonlandırıcı null değeri ekler.

*Count* [_TRUNCATE](../../c-runtime-library/truncate.md)ise, bu işlevler dizenin büyük bir kısmını, bir Sonlandırıcı null değeri ayrılırken *arabelleğe* sığacak şekilde yazar. Tüm dize (null değeri sonlandırılıyor) *arabelleğe*sığıyorsa, bu işlevler yazılan karakter sayısını (Sonlandırıcı null dahil değil) döndürür; Aksi takdirde, bu işlevler, kesilmenin oluştuğunu göstermek için-1 döndürür.

**_L** sonekine sahip bu işlevlerin sürümleri, geçerli iş parçacığı yerel ayarı yerine geçirilen yerel ayar parametresini kullanmaları dışında aynıdır.

> [!IMPORTANT]
> *Biçimin* Kullanıcı tanımlı bir dize olmadığından emin olun. Daha fazla bilgi için bkz. [arabellek taşmalarını önleme](/windows/win32/SecBP/avoiding-buffer-overruns).

> [!NOTE]
> Sonlandırıcı null değerinin boş olduğundan emin olmak için, *Count* 'un arabellek uzunluğundan kesinlikle daha az olduğundan emin olun veya **_TRUNCATE**kullanın.

' C++De, bu işlevlerin kullanılması şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir (bir boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırır) ve eski, güvenli olmayan işlevleri otomatik olarak yeni, güvenli karşılıklarıyla değiştirebilir. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vsntprintf_s**|**_vsnprintf_s**|**_vsnprintf_s**|**_vsnwprintf_s**|
|**_vsntprintf_s_l**|**_vsnprintf_s_l**|**_vsnprintf_s_l**|**_vsnwprintf_s_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgiler|
|-------------|---------------------|----------------------|
|**vsnprintf_s**|\<stdio. h > ve \<stdarg. h >|\<varargs. h > *|
|**_vsnprintf_s**, **_vsnprintf_s_l**|\<stdio. h > ve \<stdarg. h >|\<varargs. h > *|
|**_vsnwprintf_s**, **_vsnwprintf_s_l**|\<stdio. h > veya \<wchar. h > ve \<stdarg. h >|\<varargs. h > *|

\*UNIX V uyumluluğu için gereklidir.

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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
