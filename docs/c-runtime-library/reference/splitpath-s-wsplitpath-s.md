---
description: 'Hakkında daha fazla bilgi edinin: _splitpath_s _wsplitpath_s'
title: _splitpath_s, _wsplitpath_s
ms.date: 4/2/2020
api_name:
- _wsplitpath_s
- _splitpath_s
- _o__splitpath_s
- _o__wsplitpath_s
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
- api-ms-win-crt-filesystem-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _wsplitpath_s
- splitpath_s
- _splitpath_s
- wsplitpath_s
helpviewer_keywords:
- splitpath_s function
- pathnames
- _splitpath_s function
- _wsplitpath_s function
- path names
- wsplitpath_s function
ms.assetid: 30fff3e2-cd00-4eb6-b5a2-65db79cb688b
ms.openlocfilehash: f14ea8a31d241abae3a214067cae1e4d34e97861
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97292357"
---
# <a name="_splitpath_s-_wsplitpath_s"></a>_splitpath_s, _wsplitpath_s

Bir yol adını bileşenlere ayırır. Bunlar, [CRT 'Daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleriyle [_wsplitpath _splitpath](splitpath-wsplitpath.md) sürümleridir.

## <a name="syntax"></a>Sözdizimi

```C
errno_t _splitpath_s(
   const char * path,
   char * drive,
   size_t driveNumberOfElements,
   char * dir,
   size_t dirNumberOfElements,
   char * fname,
   size_t nameNumberOfElements,
   char * ext,
   size_t extNumberOfElements
);
errno_t _wsplitpath_s(
   const wchar_t * path,
   wchar_t * drive,
   size_t driveNumberOfElements,
   wchar_t *dir,
   size_t dirNumberOfElements,
   wchar_t * fname,
   size_t nameNumberOfElements,
   wchar_t * ext,
   size_t extNumberOfElements
);
template <size_t drivesize, size_t dirsize, size_t fnamesize, size_t extsize>
errno_t _splitpath_s(
   const char *path,
   char (&drive)[drivesize],
   char (&dir)[dirsize],
   char (&fname)[fnamesize],
   char (&ext)[extsize]
); // C++ only
template <size_t drivesize, size_t dirsize, size_t fnamesize, size_t extsize>
errno_t _wsplitpath_s(
   const wchar_t *path,
   wchar_t (&drive)[drivesize],
   wchar_t (&dir)[dirsize],
   wchar_t (&fname)[fnamesize],
   wchar_t (&ext)[extsize]
); // C++ only
```

### <a name="parameters"></a>Parametreler

*Yolun*<br/>
Tam yol.

*sürücü*<br/>
Sürücü harfi, ardından iki nokta üst üste (**:**). Sürücü harfine ihtiyacınız yoksa, bu parametre için **null değeri** geçirebilirsiniz.

*driveNumberOfElements*<br/>
Tek bayt veya geniş karakterdeki *sürücü* arabelleğinin boyutu. *Sürücü* **null** ise, bu değer 0 olmalıdır.

*öğesini*<br/>
Sondaki eğik çizgi dahil dizin yolu. Eğik çizgi ( **/** ), ters eğik çizgi ( **\\** ) veya her ikisi de kullanılabilir. Dizin yoluna ihtiyacınız yoksa, bu parametre için **null değeri** geçirebilirsiniz.

*Dirnumberoföğeleri*<br/>
Tek bayt veya geniş karakterdeki *Dizin* arabelleğinin boyutu. *Dır* **null** ise, bu değer 0 olmalıdır.

*fname*<br/>
Taban dosya adı (uzantı olmadan). Dosya adına ihtiyacınız yoksa, bu parametre için **null değeri** geçirebilirsiniz.

*nameNumberOfElements*<br/>
Tek bayt veya geniş karakterdeki *fname* arabelleğinin boyutu. *Fname* **null** ise, bu değer 0 olmalıdır.

*leri*<br/>
Baştaki nokta (**.**) dahil dosya adı uzantısı. Dosya adı uzantısına ihtiyacınız yoksa, bu parametre için **null değeri** geçirebilirsiniz.

*extNumberOfElements*<br/>
Tek bayt veya geniş karakterdeki *dış* arabelleğin boyutu. *EXT* **null** ise, bu değer 0 olmalıdır.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır; hatada hata kodu.

### <a name="error-conditions"></a>Hata koşulları

|Koşul|Dönüş Değeri|
|---------------|------------------|
|*yol* **null**|**EıNVAL**|
|*sürücü* **null**, *driveNumberOfElements* sıfır dışında|**EıNVAL**|
|*sürücü* **null** olmayan, *driveNumberOfElements* sıfır|**EıNVAL**|
|*dır* **null**, *dirnumberofelements* sıfır değil|**EıNVAL**|
|*dır* **null** değil, *dirnumberofelements* sıfır|**EıNVAL**|
|*fname* **null**, *nameNumberOfElements* sıfır değil|**EıNVAL**|
|*fname* **null** olmayan, *nameNumberOfElements* sıfır|**EıNVAL**|
|*EXT* **null**, *extnumberofelements* sıfır değil|**EıNVAL**|
|*EXT* **null** değil, *extnumberofelements* sıfır|**EıNVAL**|

Yukarıdaki koşullardan herhangi biri oluşursa, [parametre doğrulama](../../c-runtime-library/parameter-validation.md) bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **errno** olarak **EINVAL** ve **EINVAL** döndürür.

Arabelleklerden herhangi biri sonucu tutmak için çok kısaysa, bu işlevler dizelerin boş olması için tüm arabellekleri temizler, **errno** , **ERANGE** olarak ayarlanır ve **ERANGE** döndürülür.

## <a name="remarks"></a>Açıklamalar

**_Splitpath_s** işlevi bir yolu dört bileşene ayırır. **_splitpath_s** çok baytlı karakter dizesi bağımsız değişkenlerini uygun şekilde otomatik olarak işler ve çok baytlı karakter dizilerini kullanımda olan çok baytlı kod sayfasına göre tanıyor. **_wsplitpath_s** , **_splitpath_s** geniş karakterli bir sürümüdür; **_wsplitpath_s** bağımsız değişkenler geniş karakterli dizelerdir. Bu işlevler, aynı şekilde davranır

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsplitpath_s**|**_splitpath_s**|**_splitpath_s**|**_wsplitpath_s**|

Tam yolun her bileşeni ayrı bir arabellekte saklanır; bildirim sabitleri **_MAX_DRIVE**, **_MAX_DIR**, **_MAX_FNAME** ve **_MAX_EXT** (Stdlib içinde tanımlanmıştır). H) her dosya bileşeni için izin verilen en büyük boyutu belirtin. Karşılık gelen bildirim sabitlerinden daha büyük dosya bileşenleri yığın bozulmasına neden olur.

Aşağıdaki tablo, bildirim sabitlerinin değerlerini listelemektedir.

|Ad|Değer|
|----------|-----------|
|_MAX_DRIVE|3|
|_MAX_DIR|256|
|_MAX_FNAME|256|
|_MAX_EXT|256|

Tam yol bir bileşen içermiyorsa (örneğin, bir dosya adı), **_splitpath_s** karşılık gelen arabelleğe boş bir dize atar.

C++ ' da, bu işlevlerin kullanılması şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir ve bir boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırır. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Bu işlevlerin hata ayıklama Kitaplığı sürümleri ilk olarak arabelleği 0xFE ile doldurur. Bu davranışı devre dışı bırakmak için [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)kullanın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_splitpath_s**|\<stdlib.h>|
|**_wsplitpath_s**|\<stdlib.h> veya \<wchar.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[_Makepath_s _wmakepath_s](makepath-s-wmakepath-s.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
[_splitpath, _wsplitpath](splitpath-wsplitpath.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_makepath, _wmakepath](makepath-wmakepath.md)<br/>
[_setmbcp](setmbcp.md)<br/>
