---
title: strnlen, strnlen_s, wcsnlen, wcsnlen_s, _mbsnlen, _mbsnlen_l, _mbstrnlen, _mbstrnlen_l
ms.date: 4/2/2020
api_name:
- wcsnlen
- strnlen_s
- _mbstrnlen
- _mbsnlen_l
- _mbstrnlen_l
- strnlen
- wcsnlen_s
- _mbsnlen
- _o__mbsnlen
- _o__mbsnlen_l
- _o__mbstrnlen
- _o__mbstrnlen_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wcsnlen
- strnlen_s
- _mbsnlen
- _mbsnlen_l
- _tcsnlen
- _tcscnlen
- _mbstrnlen_l
- wcsnlen_s
- _mbstrnlen
- strnlen
- _tcscnlen_l
helpviewer_keywords:
- _tcscnlen function
- _mbstrnlen function
- _mbsnlen_l function
- lengths, strings
- mbstrnlen function
- mbsnlen_l function
- _mbstrnlen_l function
- _tcscnlen_l function
- wcsnlen_l function
- _tcsnlen function
- _mbsnlen function
- strnlen function
- mbsnlen function
- wcsnlen_s function
- strnlen_s function
- mbstrnlen_l function
- wcsnlen function
- string length
- strnlen_l function
ms.assetid: cc05ce1c-72ea-4ae4-a7e7-4464e56e5f80
ms.openlocfilehash: db4fa65fa47dfe11d7ab56ffc5feee06f2634e2a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364466"
---
# <a name="strnlen-strnlen_s-wcsnlen-wcsnlen_s-_mbsnlen-_mbsnlen_l-_mbstrnlen-_mbstrnlen_l"></a>strnlen, strnlen_s, wcsnlen, wcsnlen_s, _mbsnlen, _mbsnlen_l, _mbstrnlen, _mbstrnlen_l

Geçerli yerel alanı veya geçirilen bir dizeyi kullanarak bir dizeuzun uzunluğunu alır. Bu [strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)daha güvenli sürümleri vardır.

> [!IMPORTANT]
> **windows**runtime'da çalışan uygulamalarda _mbsnlen , **_mbsnlen_l,** **_mbstrnlen**ve **_mbstrnlen_l** kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
size_t strnlen(
   const char *str,
   size_t numberOfElements
);
size_t strnlen_s(
   const char *str,
   size_t numberOfElements
);
size_t wcsnlen(
   const wchar_t *str,
   size_t numberOfElements
);
size_t wcsnlen_s(
   const wchar_t *str,
   size_t numberOfElements
);
size_t _mbsnlen(
   const unsigned char *str,
   size_t numberOfElements
);
size_t _mbsnlen_l(
   const unsigned char *str,
   size_t numberOfElements,
   _locale_t locale
);
size_t _mbstrnlen(
   const char *str,
   size_t numberOfElements
);
size_t _mbstrnlen_l(
   const char *str,
   size_t numberOfElements,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*Str*<br/>
Null-terminated string.

*numberOfElements*<br/>
Dize arabelleği boyutu.

*Yerel ayar*<br/>
Kullanılacak yerel yer.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevler, sonlandırıcı null karakteri dahil değil, dizedeki karakter sayısını döndürer. Dizedeki ilk *numberOfElements* baytlarında (veya **wcsnlen**için geniş karakterler) null terminator yoksa, hata durumunu belirtmek için *numberOfElements* döndürülür; null-sonlandırılan dizeleri kesinlikle *numberOfElements*daha az uzunlukları vardır.

**dize** geçersiz bir çok bayt karakter içeriyorsa _mbstrnlen ve **_mbstrnlen_l** döndürün -1.

## <a name="remarks"></a>Açıklamalar

> [!NOTE]
> **strnlen** **strlen**için bir yedek değildir ; **strnlen** yalnızca bilinen boyutta bir arabellekte (örneğin, bir ağ paketinde) gelen güvenilmeyen verilerin boyutunu hesaplamak için kullanılmak üzere tasarlanmıştır. **strnlen** uzunluğu hesaplar, ancak dize sonlandırmazsa arabelleğe geçmez. Diğer durumlar **için, strlen**kullanın. (Aynı **wcsnlen**için de geçerlidir , **_mbsnlen**, ve **_mbstrnlen**.)

Bu işlevlerin her *biri,* sonlandırıcı null karakter dahil değil, str karakter sayısını döndürür. Ancak, **strnlen** ve **strnlen_s** dizeyi tek bayt karakter dizesi olarak yorumlar ve bu nedenle, dize çok bayt karakter içerse bile, dönüş değeri her zaman bayt sayısına eşittir. **wcsnlen** ve **wcsnlen_s** **sırasıyla strnlen** ve **strnlen_s** geniş karaktersürümleri; **wcsnlen** ve **wcsnlen_s** için argümanlar geniş karakterdizeli ve karakter sayısı geniş karakter birimleri bulunmaktadır. Aksi takdirde, **wcsnlen** ve **strnlen** aynı şekilde, **strnlen_s** ve **wcsnlen_s**gibi davranan.

**strnlen**, **wcsnlen**, ve **_mbsnlen** parametrelerini doğrulamayın. *str* **NULL**ise, bir erişim ihlali oluşur.

**parametrelerini doğrulamak** wcsnlen_s ve **strnlen_s.** *str* **NULL**ise, fonksiyonlar 0 döndürer.

**_mbstrnlen** da parametrelerini doğrular. *str* **NULL**ise veya *numberOfElements* **INT_MAX'den**büyükse, **parametre** [doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz bir parametre özel durumu _mbstrnlen. Yürütmenin devam etmesine izin verilirse, **_mbstrnlen** **Errno'u** **EINVAL'e** ayarlar ve -1 döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsnlen**|**strnlen**|**strnlen**|**wcsnlen**|
|**_tcscnlen**|**strnlen**|**_mbsnlen**|**wcsnlen**|
|**_tcscnlen_l**|**strnlen**|**_mbsnlen_l**|**wcsnlen**|

**_mbsnlen** ve **_mbstrnlen** çok bayt karakterli dizedeki çok bayt karakter sayısını döndürer. **_mbsnlen,** şu anda kullanılmakta olan çok bayt kod sayfasına veya geçirilen yerel sayfaya göre çok bayt karakter dizilerini tanır; çok bayt karakter geçerliliği için test etmez. **_mbstrnlen** çok bayt karakter geçerliliği için testler ve multibayt karakter dizileri tanır. **_mbstrnlen** geçirilen dize geçersiz bir çok bayt karakteri içeriyorsa, **errno** **EILSEQ**olarak ayarlanır.

Çıktı değeri, yerel LC_CTYPE **kategori** ayarı ayarı etkilenir; daha fazla bilgi için [setlocale, _wsetlocale](setlocale-wsetlocale.md) bakın. Bu işlevlerin sürümleri aynıdır, ancak **_l** soneki olmayanlar bu yerelliğe bağımlı davranış için geçerli yerel alanı kullanır ve **_l** soneki olan sürümler bunun yerine geçirilen yerel parametreyi kullanır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strnlen**, **strnlen_s**|\<string.h>|
|**wcsnlen**, **wcsnlen_s**|\<string.h> \<veya wchar.h>|
|**_mbsnlen**, **_mbsnlen_l**|\<mbstring.h>|
|**_mbstrnlen**, **_mbstrnlen_l**|\<stdlib.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_strnlen.c

#include <string.h>

int main()
{
   // str1 is 82 characters long. str2 is 159 characters long

   char* str1 = "The length of a string is the number of characters\n"
               "excluding the terminating null.";
   char* str2 = "strnlen takes a maximum size. If the string is longer\n"
                "than the maximum size specified, the maximum size is\n"
                "returned rather than the actual size of the string.";
   size_t len;
   size_t maxsize = 100;

   len = strnlen(str1, maxsize);
   printf("%s\n Length: %d \n\n", str1, len);

   len = strnlen(str2, maxsize);
   printf("%s\n Length: %d \n", str2, len);
}
```

```Output
The length of a string is the number of characters
excluding the terminating null.
Length: 82

strnlen takes a maximum size. If the string is longer
than the maximum size specified, the maximum size is
returned rather than the actual size of the string.
Length: 100
```

## <a name="see-also"></a>Ayrıca bkz.

[Dize Düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[strcoll İşlevleri](../../c-runtime-library/strcoll-functions.md)<br/>
[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
