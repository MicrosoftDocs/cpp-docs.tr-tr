---
title: _splitpath_s, _wsplitpath_s
ms.date: 11/04/2016
apiname:
- _wsplitpath_s
- _splitpath_s
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
- api-ms-win-crt-filesystem-l1-1-0.dll
- ntoskrnl.exe
apitype: DLLExport
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
ms.openlocfilehash: 87af8bac525844c06fdfc16d7d13a06eef4d61ab
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62355035"
---
# <a name="splitpaths-wsplitpaths"></a>_splitpath_s, _wsplitpath_s

Bir yol adı bileşenlerine böler. Bunlar sürümleridir [_splitpath, _wsplitpath](splitpath-wsplitpath.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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

*Yolu*<br/>
Tam yolu.

*Sürücü*<br/>
Sürücü harfini izleyen iki nokta (**:**). Geçirebilirsiniz **NULL** sürücü harfini gerekmiyorsa, bu parametre için.

*driveNumberOfElements*<br/>
Boyutu *sürücü* tek baytlı veya geniş karakter arabelleği. Varsa *sürücü* olduğu **NULL**, bu değer, 0 olmalıdır.

*dizini*<br/>
Dizin yolu, eğik çizgi de dahil. İleri eğik çizgi ( **/** ), ters eğik çizgi ( **\\** ), veya her ikisi de kullanılabilir. Geçirebilirsiniz **NULL** dizin yolu gerekmiyorsa, bu parametre için.

*dirNumberOfElements*<br/>
Boyutu *dir* tek baytlı veya geniş karakter arabelleği. Varsa *dir* olduğu **NULL**, bu değer, 0 olmalıdır.

*fname*<br/>
Temel dosya adı (uzantısı olmadan). Geçirebilirsiniz **NULL** filename gerekmiyorsa, bu parametre için.

*nameNumberOfElements*<br/>
Boyutu *fname* tek baytlı veya geniş karakter arabelleği. Varsa *fname* olduğu **NULL**, bu değer, 0 olmalıdır.

*ext*<br/>
Dönem baştaki dahil olmak üzere, dosya adı uzantısı (**.**). Geçirebilirsiniz **NULL** dosya adı uzantısı gerekmiyorsa, bu parametre için.

*extNumberOfElements*<br/>
Boyutu *ext* tek baytlı veya geniş karakter arabelleği. Varsa *ext* olduğu **NULL**, bu değer, 0 olmalıdır.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır; bir hata kodu.

### <a name="error-conditions"></a>Hata koşulları

|Koşul|Dönüş Değeri|
|---------------|------------------|
|*yol* olduğu **NULL**|**EINVAL**|
|*Sürücü* olduğu **NULL**, *driveNumberOfElements* sıfır değil|**EINVAL**|
|*Sürücü* olan olmayan**NULL**, *driveNumberOfElements* sıfırdır|**EINVAL**|
|*dir* olduğu **NULL**, *dirNumberOfElements* sıfır değil|**EINVAL**|
|*dir* olan olmayan**NULL**, *dirNumberOfElements* sıfırdır|**EINVAL**|
|*fname* olduğu **NULL**, *nameNumberOfElements* sıfır değil|**EINVAL**|
|*fname* olan olmayan**NULL**, *nameNumberOfElements* sıfırdır|**EINVAL**|
|*ext* olduğu **NULL**, *extNumberOfElements* sıfır değil|**EINVAL**|
|*ext* olan olmayan**NULL**, *extNumberOfElements* sıfırdır|**EINVAL**|

Yukarıdaki koşullardan herhangi biri meydana gelirse, geçersiz parametre işleyicisi açıklandığı gibi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md) . Yürütme devam etmesine izin verilirse bu işlevler kümesi **errno** için **EINVAL** ve dönüş **EINVAL**.

Herhangi bir arabellek ise sonuç tutmak için çok kısa, bu işlevler tüm arabellekler boş dizeler için ayarlayın temizlemeniz **errno** için **ERANGE**ve dönüş **ERANGE**.

## <a name="remarks"></a>Açıklamalar

**_Splitpath_s** işlevi bir yol dört bileşenlerine böler. **_splitpath_s** çok baytlı karakter sıralarını şu anda çok baytlı kod sayfasına göre algılamayı çok baytlı karakter dizesi bağımsız değişkenleri uygun şekilde otomatik olarak işler. **_wsplitpath_s** geniş karakterli sürümüdür **_splitpath_s**; bağımsız değişkenler **_wsplitpath_s** geniş karakterli dizelerdir. Bu işlevler, aynı şekilde davranır

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsplitpath_s**|**_splitpath_s**|**_splitpath_s**|**_wsplitpath_s**|

Her bileşenin tam yolunun ayrı bir arabellek depolanır; bildirim sabitleri **_max_drıve**, **_max_dır**, **_MAX_FNAME**, ve **_MAX_EXT** (STDLIB içinde tanımlanır. H) her dosya bileşeni için izin verilen en büyük boyutu belirtin. Bileşenleri, ilgili bildirim sabitleri yığın bozulması neden daha büyük bir dosya.

Aşağıdaki tabloda, bildirim sabitleri değerlerini listeler.

|Ad|Değer|
|----------|-----------|
|_MAX_DRIVE|3|
|_MAX_DIR|256|
|_MAX_FNAME|256|
|_MAX_EXT|256|

Tam yolu (örneğin, bir dosya adı), bir bileşen içermiyorsa **_splitpath_s** boş bir dize karşılık gelen arabelleğe atar.

C++ dilinde bu işlevlerin kullanılması şablon aşırı yüklemeleriyle basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğu bir boyut bağımsız değişkeni belirtme gereksinimi ortadan otomatik olarak çıkarabilir. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Bu işlevlerin hata ayıklama sürümleri, ilk arabellek 0xFD ile doldurur. Bu davranışı devre dışı bırakmak için [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_splitpath_s**|\<stdlib.h >|
|**_wsplitpath_s**|\<stdlib.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bakın [_makepath_s, _wmakepath_s](makepath-s-wmakepath-s.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
[_splitpath, _wsplitpath](splitpath-wsplitpath.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_makepath, _wmakepath](makepath-wmakepath.md)<br/>
[_setmbcp](setmbcp.md)<br/>
