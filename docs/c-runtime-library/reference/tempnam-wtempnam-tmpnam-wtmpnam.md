---
title: _tempnam, _wtempnam, tmpnam, _wtmpnam
ms.date: 11/04/2016
api_name:
- _wtempnam
- _wtmpnam
- tmpnam
- _tempnam
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
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 9fd1eb9f2f718afec5b7d5555145fcd7e5cc17cf
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957514"
---
# <a name="_tempnam-_wtempnam-tmpnam-_wtmpnam"></a>_tempnam, _wtempnam, tmpnam, _wtmpnam

Geçici dosyalar oluşturmak için kullanabileceğiniz adlar oluşturun. Bu işlevlerin bazılarının daha güvenli sürümleri mevcuttur; bkz. [tmpnam_s, _wtmpnam_s](tmpnam-s-wtmpnam-s.md).

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
**_Tempnam**tarafından döndürülen adlara önceden gönderilecek dize.

*öğesini*<br/>
TMP ortam değişkeni yoksa veya TMP geçerli bir dizin değilse dosya adında kullanılan yol.

*üstbilgisine*<br/>
Oluşturulan adı tutan ve işlevin döndürdüğü adla aynı olacak olan işaretçi. Bu, oluşturulan adı kaydetmek için kullanışlı bir yoldur.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri, bir hata varsa, oluşturulan veya **null** olan ada bir işaretçi döndürür. **TMP_MAX** 'den fazlasını denerseniz hata oluşabilir (bkz. stdio. H) **tmpnam** ile çağırır veya **_TEMPNAM** kullanırsanız ve TMP ortam değişkeninde ve *dir* parametresinde geçersiz bir dizin adı belirtildi.

> [!NOTE]
> **Tmpnam** ve **_wtmpnam** tarafından döndürülen işaretçiler iç statik arabelleklere işaret. Bu işaretçileri serbest bırakmak için [Free](free.md) çağrılmamalıdır. **_tempnam** ve **_wtempnam**tarafından ayrılan işaretçiler için **ücretsiz** olarak çağrılması gerekir.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri, şu anda mevcut olmayan bir dosyanın adını döndürür. **tmpnam** , [Gettemppathw](/windows/win32/api/fileapi/nf-fileapi-gettemppathw)tarafından döndürülen belirlenmiş Windows geçici dizininde benzersiz bir ad döndürür. tempnam, belirtilen bir dizinde benzersiz bir ad oluşturur.  **\_** Bir dosya adının ters eğik çizgiyle ön halden önceden sonlandırıldığına ve \fname21 gibi yol bilgilerine sahip olmadığına, bu adın geçerli çalışma dizini için geçerli olduğunu gösterir.

**Tmpnam**için, bu oluşturulan dosya adını *Str*içinde depolayabilirler. *Str* **null**ise, **tmpnam** sonucu bir iç statik arabellekte bırakır. Bu nedenle, sonraki çağrılar bu değeri yok eder. **Tmpnam** tarafından oluşturulan ad, program tarafından oluşturulan bir dosya adından ve ilk **tmpnam**çağrısından sonra, stdio 'daki **TMP_MAX** olduğunda, temel 32 (. 1-. vvu) içindeki sıralı sayıların bir dosya uzantısı ile oluşur. H 32.767).

**_tempnam** , aşağıdaki kurallar tarafından seçilen bir dizin için benzersiz bir dosya adı oluşturur:

- TMP ortam değişkeni tanımlanmışsa ve geçerli bir dizin adına ayarlandıysa, TMP tarafından belirtilen dizin için benzersiz dosya adları oluşturulur.

- TMP ortam değişkeni tanımlanmazsa veya var olmayan bir dizinin adına ayarlandıysa, **_tempnam** benzersiz adlar oluşturacak yol olarak *dır* parametresini kullanır.

- TMP ortam değişkeni tanımlanmazsa veya var olmayan bir dizinin adına ayarlandıysa *ve Dizin* **null** ise ya da varolmayan bir dizinin adına ayarlandıysa, **_tempnam** geçerli çalışma dizinini gene olarak kullanır. benzersiz adları derecelendirin. Şu anda, hem TMP hem de *dir* , mevcut olmayan dizinlerin adlarını belirtmekte, **_tempnam** işlev çağrısı başarısız olur.

**_Tempnam** tarafından döndürülen ad, *ön ek* ve ardışık bir sayı olacak, belirtilen dizin için benzersiz bir dosya adı oluşturacak şekilde birleştirilir. **_tempnam** uzantısı olmayan dosya adları oluşturuyor. **_tempnam** dosya adı için alan ayırmak üzere [malloc](malloc.md) kullanır; program artık gerekli olmadığında bu alanı boşaltmaktan sorumludur.

**_tempnam** ve **tmpnam** uygun şekilde çok baytlı karakter dize bağımsız değişkenlerini otomatik olarak işler ve işletim sisteminden alınan OEM kod sayfasına göre çok baytlı karakter dizilerini tanıyor. **_wtempnam** , **_tempnam**; öğesinin geniş karakterli bir sürümüdür **_wtempnam** bağımsız değişkenleri ve dönüş değeri geniş karakterli dizelerdir. **_wtempnam** ve **_tempnam** aynı şekilde davranır. Bu, **_wtempnam** çok baytlı karakter dizelerini işlemez. **_wtmpnam** , **tmpnam**öğesinin geniş karakterli bir sürümüdür. **_wtmpnam** öğesinin bağımsız değişkeni ve dönüş değeri geniş karakterli dizelerdir. _wtmpnam, çok baytlı karakter dizelerini işleyememesi dışında **_wtmpnam** ve **tmpnam** **aynı şekilde davranır** .

**_Debug** ve **_Crtdbg_map_ayırma** tanımlanmışsa, **_tempnam** ve **_wtempnam** , [_tempnam_dbg ve _wtempnam_dbg](tempnam-dbg-wtempnam-dbg.md)çağrılarıyla değiştirilmiştir.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ttmpnam**|**tmpnam**|**tmpnam**|**_wtmpnam**|
|**_ttempnam**|**_tempnam**|**_tempnam**|**_wtempnam**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_tempnam**|\<stdio. h >|
|**_wtempnam**, **_wtmpnam**|\<stdio. h > veya \<wchar. h >|
|**tmpnam**|\<stdio. h >|

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

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[malloc](malloc.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[tmpfile](tmpfile.md)<br/>
[tmpfile_s](tmpfile-s.md)<br/>
