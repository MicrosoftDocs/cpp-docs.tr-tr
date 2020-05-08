---
title: ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s
ms.date: 4/2/2020
api_name:
- _ctime64_s
- _wctime32_s
- ctime_s
- _wctime64_s
- _ctime32_s
- _wctime_s
- _o__ctime32_s
- _o__ctime64_s
- _o__wctime32_s
- _o__wctime64_s
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
- api-ms-win-crt-time-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- ctime64_s
- _ctime32_s
- _tctime32_s
- _ctime64_s
- _wctime_s
- _tctime_s
- _tctime64_s
- ctime_s
- ctime32_s
helpviewer_keywords:
- _wctime32_s function
- ctime64_s function
- _tctime64_s function
- _wctime_s function
- tctime_s function
- _wctime64_s function
- ctime_s function
- ctime32_s function
- _ctime64_s function
- tctime64_s function
- wctime64_s function
- wctime_s function
- _tctime_s function
- tctime32_s function
- wctime32_s function
- time, converting
- _ctime32_s function
- _tctime32_s function
ms.assetid: 36ac419a-8000-4389-9fd8-d78b747a009b
ms.openlocfilehash: ca7636f7054b6c7e228b57e0e776250f1b4ccb32
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82914816"
---
# <a name="ctime_s-_ctime32_s-_ctime64_s-_wctime_s-_wctime32_s-_wctime64_s"></a>ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s

Bir zaman değerini dizeye dönüştürün ve yerel saat dilimi ayarlarını yapın. Bu sürümler, [CRT 'Daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklanan şekilde, güvenlik geliştirmeleriyle [, _ctime64, _wctime _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md) .

## <a name="syntax"></a>Sözdizimi

```C
errno_t ctime_s(
   char* buffer,
   size_t numberOfElements,
   const time_t *sourceTime
);
errno_t _ctime32_s(
   char* buffer,
   size_t numberOfElements,
   const __time32_t *sourceTime
);
errno_t _ctime64_s(
   char* buffer,
   size_t numberOfElements,
   const __time64_t *sourceTime )
;
errno_t _wctime_s(
   wchar_t* buffer,
   size_t numberOfElements,
   const time_t *sourceTime
);
errno_t _wctime32_s(
   wchar_t* buffer,
   size_t numberOfElements,
   const __time32_t *sourceTime
);
errno_t _wctime64_s(
   wchar_t* buffer,
   size_t numberOfElements,
   const __time64_t *sourceTime
);
```

```cpp
template <size_t size>
errno_t _ctime32_s(
   char (&buffer)[size],
   const __time32_t *sourceTime
); // C++ only
template <size_t size>
errno_t _ctime64_s(
   char (&buffer)[size],
   const __time64_t *sourceTime
); // C++ only
template <size_t size>
errno_t _wctime32_s(
   wchar_t (&buffer)[size],
   const __time32_t *sourceTime
); // C++ only
template <size_t size>
errno_t _wctime64_s(
   wchar_t (&buffer)[size],
   const __time64_t *sourceTime
); // C++ only
```

### <a name="parameters"></a>Parametreler

*arabelleğin*<br/>
26 karakter tutabilecek kadar büyük olmalıdır. Karakter dizesi sonucuna yönelik bir işaretçi veya şunu içeriyorsa **null** :

- *Sourcetime* , 1 Ocak 1970, UTC 'nin gece yarısından önceki bir tarihi temsil eder.

- **_Ctime32_s** veya **_Wctime32_s** kullanırsanız ve *sourcetime* , 23:59:59 Ocak 2038, UTC 'den sonraki bir tarihi temsil eder.

- **_Ctime64_s** veya **_Wctime64_s** kullanırsanız ve *Sourcetime* 23:59:59, 31 Aralık 3000, UTC 'den sonraki bir tarihi temsil eder.

- **_Ctime_s** veya **_wctime_s**kullanıyorsanız, bu işlevler önceki işlevlere sarmalayıcılardır. Açıklamalar bölümüne bakın.

*numberOfElements*<br/>
Arabelleğin boyutu.

*sourceTime*<br/>
Saklı saate yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır. Geçersiz bir parametre nedeniyle hata oluşursa, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa bir hata kodu döndürülür. Hata kodları ERRNO içinde tanımlanmıştır. Olsun Bu hataların listelenmesi için bkz. [errno](../../c-runtime-library/errno-constants.md). Her bir hata koşulu için oluşturulan gerçek hata kodları aşağıdaki tabloda gösterilmiştir.

## <a name="error-conditions"></a>Hata koşulları

|*arabelleğin*|*numberOfElements*|*sourceTime*|Döndürülmesini|*Arabellekteki* değer|
|--------------|------------------------|------------|------------|-----------------------|
|**DEĞER**|kaydedilmemiş|kaydedilmemiş|**EıNVAL**|Değiştirilmedi|
|**Null** değil (geçerli belleğe işaret eder)|0|kaydedilmemiş|**EıNVAL**|Değiştirilmedi|
|**Null** değil|0< boyutu < 26|kaydedilmemiş|**EıNVAL**|Boş dize|
|**Null** değil|>= 26|NULL|**EıNVAL**|Boş dize|
|**Null** değil|>= 26|< 0|**EıNVAL**|Boş dize|

## <a name="remarks"></a>Açıklamalar

**Ctime_s** işlevi, bir [time_t](../../c-runtime-library/standard-types.md) yapısı olarak depolanan bir zaman değerini bir karakter dizesine dönüştürür. *Sourcetime* değeri genellikle gece yarısından beri geçen saniye sayısı ( [time](time-time32-time64.md)00:00:00), 1 Ocak 1970, Eşgüdümlü Evrensel Saat (UTC) döndüren bir çağrıdan alınmıştır. Dönüş değeri dizesi tam 26 karakter içerir ve şu biçimdedir:

`Wed Jan 02 02:03:55 1980\n\0`

24 saatlik bir saat kullanılır. Tüm alanların sabit bir genişliği vardır. Yeni satır karakteri (' \n ') ve null karakteri (' \ 0 ') dizenin son iki konumunu kaplar.

Dönüştürülen karakter dizesi de yerel saat dilimi ayarlarına göre ayarlanır. Yerel saati yapılandırma hakkında bilgi için [saat](time-time32-time64.md), [_ftime](ftime-ftime32-ftime64.md)ve [localtime32_s](localtime-s-localtime32-s-localtime64-s.md) işlevlerine ve saat dilimi ortamı ile genel değişkenleri tanımlama hakkında bilgi için [_tzset](tzset.md) işlevine bakın.

**_wctime32_s** ve **_wctime64_s** , **_ctime32_s** ve **_ctime64_s**'ın geniş karakterli sürümüdür; geniş karakterli dizeye bir işaretçi döndürülüyor. Aksi takdirde, **_ctime64_s**, **_wctime32_s**ve **_wctime64_s** **_ctime32_s**aynı şekilde davranır.

**ctime_s** , **_ctime64_s** değerlendirilen ve **time_t** **__time64_t**eşdeğer bir satır içi işlevdir. Derleyicinin **time_t** eski 32 bit **time_t**olarak yorumlamasını zorlamak istiyorsanız **_USE_32BIT_TIME_T**tanımlayabilirsiniz. Bunu yapmak **ctime_s** **_ctime32_s**değerlendirmesine neden olur. Uygulamanız 18 Ocak 2038 ' den sonra başarısız olabileceğinden ve 64-bit platformlarda izin verilmediği için bu önerilmez.

C++ ' da, bu işlevlerin kullanılması şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir ve bir boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırır. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Bu işlevlerin hata ayıklama Kitaplığı sürümleri ilk olarak arabelleği 0xFE ile doldurur. Bu davranışı devre dışı bırakmak için [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tctime_s**|**ctime_s**|**ctime_s**|**_wctime_s**|
|**_tctime32_s**|**_ctime32_s**|**_ctime32_s**|**_wctime32_s**|
|**_tctime64_s**|**_ctime64_s**|**_ctime64_s**|**_wctime64_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**ctime_s**, **_ctime32_s**, **_ctime64_s**|\<Time. h>|
|**_wctime_s**, **_wctime32_s**, **_wctime64_s**|\<Time. h> veya \<wchar. h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="example"></a>Örnek

```C
// crt_wctime_s.c
// This program gets the current
// time in time_t form and then uses _wctime_s to
// display the time in string form.

#include <time.h>
#include <stdio.h>

#define SIZE 26

int main( void )
{
   time_t ltime;
   wchar_t buf[SIZE];
   errno_t err;

   time( &ltime );

   err = _wctime_s( buf, SIZE, &ltime );
   if (err != 0)
   {
      printf("Invalid Arguments for _wctime_s. Error Code: %d\n", err);
   }
   wprintf_s( L"The time is %s\n", buf );
}
```

```Output
The time is Fri Apr 25 13:03:39 2003
```

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Yönetimi](../../c-runtime-library/time-management.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
