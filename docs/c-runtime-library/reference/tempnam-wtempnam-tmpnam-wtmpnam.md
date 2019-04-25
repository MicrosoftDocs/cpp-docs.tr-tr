---
title: _tempnam, _wtempnam, tmpnam, _wtmpnam
ms.date: 11/04/2016
apiname:
- _wtempnam
- _wtmpnam
- tmpnam
- _tempnam
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
- wtempnam
- _wtmpnam
- wtmpnam
- tmpnam
- _wtempnam
- _tempnam
helpviewer_keywords:
- wtempnam function
- file names [C++], creating temporary
- _tempnam function
- ttmpnam function
- tmpnam function
- tempnam function
- wtmpnam function
- temporary files, creating
- file names [C++], temporary
- _ttmpnam function
- _wtmpnam function
- _wtempnam function
ms.assetid: 3ce75f0f-5e30-42a6-9791-8d7cbfe70fca
ms.openlocfilehash: 29fa8fc836b1b52bcf66247b3f6aaba47b8c2eaa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62284879"
---
# <a name="tempnam-wtempnam-tmpnam-wtmpnam"></a>_tempnam, _wtempnam, tmpnam, _wtmpnam

Geçici dosyalar oluşturmak için kullanabileceğiniz adları oluşturun. Bu işlevlerden bazılarının daha güvenli sürümleri mevcuttur; bkz: [tmpnam_s, _wtmpnam_s](tmpnam-s-wtmpnam-s.md).

## <a name="syntax"></a>Sözdizimi

```C
char *_tempnam(
   const char *dir,
   const char *prefix
);
wchar_t *_wtempnam(
   const wchar_t *dir,
   const wchar_t *prefix
);
char *tmpnam(
   char *str
);
wchar_t *_wtmpnam(
   wchar_t *str
);
```

### <a name="parameters"></a>Parametreler

*prefix*<br/>
Bekletilen tarafından döndürülen adlarına olacak dize **_tempnam**.

*dizini*<br/>
Dosya adında hiçbir TMP ortam değişkeni yoksa veya TMP geçerli bir dizin değil ise kullanılan yol.

*str*<br/>
Oluşturulan adı tutacak ve işlevin döndürdüğü adıyla aynı olacak işaretçisi. Oluşturulan ad kaydetmek için kullanışlı bir yoldur.

## <a name="return-value"></a>Dönüş Değeri

Oluşturulan ad bu işlevlerin her biri işaretçi döndürür veya **NULL** bir hata varsa. Çalışırsanız hata meydana gelebilir birden fazla **TMP_MAX** (STDIO bakın. H) çağrılarını **tmpnam** veya kullanıyorsanız **_tempnam** ve TMP ortam değişkenini hem de belirtilen geçersiz dizin adı *dir* parametresi.

> [!NOTE]
> Tarafından döndürülen işaretçileri **tmpnam** ve **_wtmpnam** noktası statik iç arabellek. [Ücretsiz](free.md) bu işaretçileri serbest bırakmak çağrılmamalıdır. **Ücretsiz** tarafından ayrılan işaretçiler için çağrılması gereken **_tempnam** ve **_wtempnam**.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri, şu anda mevcut olmayan bir dosya adını döndürür. **tmpnam** tarafından döndürülen belirlenen Windows geçici dizinde benzersiz bir ad verir [GetTempPathW](/windows/desktop/api/fileapi/nf-fileapi-gettemppathw). **\_tempnam** atanmış farklı bir dizinde benzersiz bir ad oluşturur. Bir dosya adı bekletilen ters eğik çizgi ve \fname21 gibi hiçbir yol bilgisi olduğunda bu adı geçerli çalışma dizini için geçerli olduğunu belirttiğinden unutmayın.

İçin **tmpnam**, bu oluşturulan dosya adında depolayabilirsiniz *str*. Varsa *str* olduğu **NULL**, ardından **tmpnam** sonucu bir iç statik arabellek bırakır. Bu nedenle sonraki çağrılar, bu değer yok. Tarafından oluşturulan adı **tmpnam** bir program tarafından oluşturulan dosya adı ve ilk çağrısından sonra oluşan **tmpnam**, sıralı sayıların temel 32 bir dosya uzantısı (.1-.vvu olduğunda **TMP_MAX**  STDIO içinde. H 32.767 ise).

**_tempnam** benzersiz bir dosya adı aşağıdaki kurallara göre seçilen bir dizin oluşturur:

- TMP ortam değişkenini tanımlanır ve geçerli dizin adına ayarlayın, benzersiz dosya adları TMP tarafından belirtilen dizin için oluşturulur.

- TMP ortam değişkeni tanımlanmamışsa veya var olmayan bir dizin adını ayarlarsanız **_tempnam** kullanacağı *dir* parametre olarak, bunu oluşturacağını benzersiz adlar yolu.

- TMP ortam değişkeni tanımlanmamışsa veya var olmayan bir dizin adını ayarlarsanız ve varsa *dir* ya da **NULL** veya mevcut değil, bir dizinin adına ayarlayın **_ tempnam** geçerli çalışma dizini benzersiz adlar oluşturmak için kullanır. Şu anda, hem TMP ve *dir* yok, dizin adlarını belirtmek **_tempnam** işlev çağrısı başarısız olur.

Tarafından döndürülen adı **_tempnam** bir birleşimi olacaktır *önek* ve benzersiz bir dosya adı için belirtilen dizin oluşturmak için birleştirecek bir sıralı numara. **_tempnam** hiçbir uzantılı dosya adları oluşturur. **_tempnam** kullanan [malloc](malloc.md) ; dosya adı için alan ayırmak için artık gerekli değilse, bu alanı boşaltmayı içeren için sorumlu bir programdır.

**_tempnam** ve **tmpnam** otomatik olarak algılamayı OEM kod sayfasına göre çok baytlı karakter dizileri tanıtıcı çok baytlı karakter dizesi bağımsız değişken olarak uygun alınan işletim sisteminden. **_wtempnam** geniş karakterli sürümüdür **_tempnam**; bağımsız değişkenler ve dönüş değeri **_wtempnam** geniş karakterli dizelerdir. **_wtempnam** ve **_tempnam** aynı şekilde davranır **_wtempnam** çok baytlı karakter dizelerini işlemez. **_wtmpnam** geniş karakterli sürümüdür **tmpnam**; bağımsız değişkeni ve dönüş değeri **_wtmpnam** geniş karakterli dizelerdir. **_wtmpnam** ve **tmpnam** aynı şekilde davranır **_wtmpnam** çok baytlı karakter dizelerini işlemez.

Varsa **_DEBUG** ve **_CRTDBG_MAP_ALLOC** tanımlanan **_tempnam** ve **_wtempnam** çağrılarıyla değiştirilir [_tempnam _dbg ve _wtempnam_dbg](tempnam-dbg-wtempnam-dbg.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ttmpnam**|**tmpnam**|**tmpnam**|**_wtmpnam**|
|**_ttempnam**|**_tempnam**|**_tempnam**|**_wtempnam**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_tempnam**|\<stdio.h >|
|**_wtempnam**, **_wtmpnam**|\<stdio.h > veya \<wchar.h >|
|**tmpnam**|\<stdio.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_tempnam.c
// compile with: /W3
// This program uses tmpnam to create a unique filename in the
// temporary directory, and _tempname to create a unique filename
// in C:\\tmp.

#include <stdio.h>
#include <stdlib.h>

int main(void)
{
   char * name1 = NULL;
   char * name2 = NULL;
   char * name3 = NULL;

   // Create a temporary filename for the current working directory:
   if ((name1 = tmpnam(NULL)) != NULL) { // C4996
   // Note: tmpnam is deprecated; consider using tmpnam_s instead
      printf("%s is safe to use as a temporary file.\n", name1);
   } else {
      printf("Cannot create a unique filename\n");
   }

   // Create a temporary filename in temporary directory with the
   // prefix "stq". The actual destination directory may vary
   // depending on the state of the TMP environment variable and
   // the global variable P_tmpdir.

   if ((name2 = _tempnam("c:\\tmp", "stq")) != NULL) {
      printf("%s is safe to use as a temporary file.\n", name2);
   } else {
      printf("Cannot create a unique filename\n");
   }

   // When name2 is no longer needed:
   if (name2) {
      free(name2);
   }

   // Unset TMP environment variable, then create a temporary filename in C:\tmp.
   if (_putenv("TMP=") != 0) {
      printf("Could not remove TMP environment variable.\n");
   }

   // With TMP unset, we will use C:\tmp as the temporary directory.
   // Create a temporary filename in C:\tmp with prefix "stq".
   if ((name3 = _tempnam("c:\\tmp", "stq")) != NULL) {
      printf("%s is safe to use as a temporary file.\n", name3);
   }
   else {
      printf("Cannot create a unique filename\n");
   }

   // When name3 is no longer needed:
   if (name3) {
      free(name3);
   }

   return 0;
}
```

```Output
C:\Users\LocalUser\AppData\Local\Temp\sriw.0 is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\stq2 is safe to use as a temporary file.
c:\tmp\stq3 is safe to use as a temporary file.
```

## <a name="see-also"></a>Ayrıca bkz.

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[malloc](malloc.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[tmpfile](tmpfile.md)<br/>
[tmpfile_s](tmpfile-s.md)<br/>
