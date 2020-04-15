---
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 364544a9423668494747405e801d59b73de4e6c6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81355626"
---
# <a name="_splitpath_s-_wsplitpath_s"></a>_splitpath_s, _wsplitpath_s

Yol adını bileşenlere ayırır. Bunlar, [CRT'deki](splitpath-wsplitpath.md) Güvenlik Özellikleri'nde açıklandığı gibi güvenlik geliştirmeleriyle _wsplitpath _splitpath [sürümleridir.](../../c-runtime-library/security-features-in-the-crt.md)

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
Tam yol.

*Sürücü*<br/>
Sürücü harfi, ardından bir kolon (**:**). Sürücü harfine ihtiyacınız yoksa bu parametre için **NULL'u** geçebilirsiniz.

*driveNumberOfElements*<br/>
*Sürücü* arabelleği tek bayt veya geniş karakterler boyutu. *Sürücü* **NULL**ise, bu değer 0 olmalıdır.

*Dir*<br/>
İzyolu yolu, çizgi izleme de dahil olmak üzere. İleri eğik **/** çizgiler ( **\\** ), ters eğik çizgi ( ), veya her ikisi de kullanılabilir. Dizin yoluna ihtiyacınız yoksa bu parametre için **NULL'u** geçebilirsiniz.

*dirNumberOfElements*<br/>
Tek bayt veya geniş karakterlerdeki *dir* arabelleği boyutu. *dir* **NULL**ise, bu değer 0 olmalıdır.

*Fname*<br/>
Temel dosya adı (uzantısız). Dosya adı gerekmezseniz bu parametre için **NULL** geçirebilirsiniz.

*nameNumberOfElements*<br/>
Tek bayt veya geniş karakterlerdeki *fname* arabelleği boyutu. *fname* **NULL**ise, bu değer 0 olmalıdır.

*Dahili*<br/>
Dosya adı uzantısı, satır aralığı da dahil olmak üzere (**.**). Dosya adı uzantısına ihtiyacınız yoksa bu parametre için **NULL'u** geçebilirsiniz.

*extNumberOfElements*<br/>
Tek bayt veya geniş karakterlerdeki *ext* arabelleği boyutu. *Ext* **NULL**ise, bu değer 0 olmalıdır.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır; hata bir hata kodu.

### <a name="error-conditions"></a>Hata Koşulları

|Koşul|Dönüş Değeri|
|---------------|------------------|
|*yol* **NULL'dur**|**Eınval**|
|*sürücü* **NULL'** dur, *driveNumberOfElements* sıfır değildir|**Eınval**|
|*sürücü* **null**olmayan, *driveNumberOfElements* sıfır|**Eınval**|
|*dir* **NULL**, *dirNumberOfElements* olmayan sıfır|**Eınval**|
|*dir* non-**NULL**, *dirNumberOfElements* sıfır|**Eınval**|
|*fname* **NULL**' dur , *nameNumberOfElements* sıfır olmayan|**Eınval**|
|*fname* non-**NULL**, *nameNumberOfElements* sıfır|**Eınval**|
|*ext* **NULL,** *extNumberOfElements* olmayan sıfır|**Eınval**|
|*ext* olmayan-**NULL,** *extNumberOfElements* sıfır|**Eınval**|

Yukarıdaki koşullardan herhangi biri oluşursa, geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md) açıklandığı gibi çağrılır. Yürütme devam etmesine izin verilirse, bu işlevler EINVAL **için errno** ayarlayın ve **EINVAL** döndürün. **EINVAL**

Arabelleklerden herhangi biri sonucu tutmak için çok kısaysa, bu işlevler tüm arabellekleri boş dizeleri temizlemek, **ERANGE** **için errno** ayarlayın ve **ERANGE**döndürün.

## <a name="remarks"></a>Açıklamalar

**_splitpath_s** işlevi bir yolu dört bileşenine ayırır. **_splitpath_s,** çok bayt karakterli dize bağımsız değişkenlerini uygun şekilde işleyerek, şu anda kullanılmakta olan çok bayt kod sayfasına göre çok bayt karakter dizilerini tanıyarak çalışır. **_wsplitpath_s** **_splitpath_s**geniş karakterli bir versiyonudur; **_wsplitpath_s** bağımsız değişkenleri geniş karakterli dizeleridir. Bu işlevler aynı şekilde başka şekilde çalışır

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsplitpath_s**|**_splitpath_s**|**_splitpath_s**|**_wsplitpath_s**|

Tam yolun her bileşeni ayrı bir arabellekte depolanır; _MAX_DRIVE **,** **_MAX_DIR,** **_MAX_FNAME**ve **_MAX_EXT** (STDLIB'de tanımlanan) manifesto sabitleri. H) her dosya bileşeni için izin verilen maksimum boyutu belirtin. Dosya bileşenleri, karşılık gelen bildirim sabitlerinden daha büyük yığın bozulmasına neden olur.

Aşağıdaki tabloda bildirim sabitlerinin değerleri listelenebönemlidir.

|Adı|Değer|
|----------|-----------|
|_MAX_DRIVE|3|
|_MAX_DIR|256|
|_MAX_FNAME|256|
|_MAX_EXT|256|

Tam yol bir bileşen (örneğin, bir dosya adı) içermiyorsa, **_splitpath_s** ilgili arabelleğe boş bir dize atar.

C++'da, bu işlevleri kullanmak şablon aşırı yükleri ile basitleştirilir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkararak boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırabilir. Daha fazla bilgi için Bkz. [Güvenli Şablon Overloads.](../../c-runtime-library/secure-template-overloads.md)

Bu işlevlerin hata ayıklama kitaplığı sürümleri önce arabelleği 0xFE ile doldurur. Bu davranışı devre dışı kullanabilirsiniz, [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)kullanın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_splitpath_s**|\<stdlib.h>|
|**_wsplitpath_s**|\<stdlib.h> \<veya wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

[_makepath_s, _wmakepath_s](makepath-s-wmakepath-s.md)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Dosya Işleme](../../c-runtime-library/file-handling.md)<br/>
[_splitpath, _wsplitpath](splitpath-wsplitpath.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_makepath, _wmakepath](makepath-wmakepath.md)<br/>
[_setmbcp](setmbcp.md)<br/>
