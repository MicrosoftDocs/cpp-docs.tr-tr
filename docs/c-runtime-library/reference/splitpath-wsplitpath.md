---
title: _splitpath, _wsplitpath
ms.date: 4/2/2020
api_name:
- _wsplitpath
- _splitpath
- _o__splitpath
- _o__wsplitpath
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wsplitpath
- _splitpath
- splitpath
- _wsplitpath
- _tsplitpath
helpviewer_keywords:
- _splitpath function
- pathnames
- wsplitpath function
- splitpath function
- _wsplitpath function
- tsplitpath function
- path names
- _tsplitpath function
ms.assetid: 32bd76b5-1385-4ee8-a64c-abcb541cd2e4
ms.openlocfilehash: 6798f93b2d1bc18a190b3b015bf8c882a3fa8a37
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81355607"
---
# <a name="_splitpath-_wsplitpath"></a>_splitpath, _wsplitpath

Bir yol adını bileşenlere ayırın. Bu işlevlerin daha güvenli sürümleri mevcuttur, [_splitpath_s bakın, _wsplitpath_s.](splitpath-s-wsplitpath-s.md)

## <a name="syntax"></a>Sözdizimi

```C
void _splitpath(
   const char *path,
   char *drive,
   char *dir,
   char *fname,
   char *ext
);
void _wsplitpath(
   const wchar_t *path,
   wchar_t *drive,
   wchar_t *dir,
   wchar_t *fname,
   wchar_t *ext
);
```

### <a name="parameters"></a>Parametreler

*Yolu*<br/>
Tam yol.

*Sürücü*<br/>
Sürücü harfi, ardından bir kolon (**:**). Sürücü harfine ihtiyacınız yoksa bu parametre için **NULL'u** geçebilirsiniz.

*Dir*<br/>
İzyolu yolu, çizgi izleme de dahil olmak üzere. İleri eğik **/** çizgiler ( **\\** ), ters eğik çizgi ( ), veya her ikisi de kullanılabilir. Dizin yoluna ihtiyacınız yoksa bu parametre için **NULL'u** geçebilirsiniz.

*Fname*<br/>
Temel dosya adı (uzantısı yok). Dosya adı gerekmezseniz bu parametre için **NULL** geçirebilirsiniz.

*Dahili*<br/>
Dosya adı uzantısı, satır aralığı da dahil olmak üzere (**.**). Dosya adı uzantısına ihtiyacınız yoksa bu parametre için **NULL'u** geçebilirsiniz.

## <a name="remarks"></a>Açıklamalar

**_splitpath** işlevi bir yolu dört bileşenine ayırır. **_splitpath,** çok bayt karakterli dize bağımsız değişkenlerini uygun şekilde işleyerek, şu anda kullanılmakta olan çok bayt kod sayfasına göre çok bayt karakter dizilerini tanıyarak çalışır. **_wsplitpath** **_splitpath**geniş karakterli bir versiyonudur; **_wsplitpath** bağımsız değişkenleri geniş karakterli dizeleridir. Bu işlevler aynı şekilde başka türlü çalışır.

**Güvenlik Notu** Bu işlevler, arabellek taşma sorunu tarafından ortaya çıkarılan olası bir tehdit le karşı lanır. Arabellek taşma sorunları, sık karşılaşılan bir sistem saldırısı yöntemidir ve bu da haksız bir ayrıcalık yükselmesine neden olabilir. Daha fazla bilgi için [bkz.](/windows/win32/SecBP/avoiding-buffer-overruns) Bu işlevlerin daha güvenli sürümleri mevcuttur; [_splitpath_s, _wsplitpath_s](splitpath-s-wsplitpath-s.md)bakın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsplitpath**|**_splitpath**|**_splitpath**|**_wsplitpath**|

Tam yolun her bileşeni ayrı bir arabellekte depolanır; _MAX_DRIVE **,** **_MAX_DIR,** **_MAX_FNAME**ve **_MAX_EXT** (STDLIB'de tanımlanan) manifesto sabitleri. H) her dosya bileşeni için maksimum boyutu belirtin. Karşılık gelen bildirim sabitlerinden daha büyük dosya bileşenleri yığın bozulmasına neden olur.

Olası arabellek taşmasını önlemek için her arabellek karşılık gelen bildirim sabiti kadar büyük olmalıdır.

Aşağıdaki tabloda bildirim sabitlerinin değerleri listelenebönemlidir.

|Adı|Değer|
|----------|-----------|
|**_MAX_DRIVE**|3|
|**_MAX_DIR**|256|
|**_MAX_FNAME**|256|
|**_MAX_EXT**|256|

Tam yol bir bileşen (örneğin, bir dosya adı) içermiyorsa, **_splitpath** ilgili arabelleklere boş dizeleri atar.

Gerek meyen *yol* dışındaki herhangi bir parametre için **_SPLITPATH** için **NULL'u** geçebilirsiniz.

*Yol* **NULL**ise, Geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, **errno** **EINVAL** olarak ayarlanır ve işlev **EINVAL**döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_splitpath**|\<stdlib.h>|
|**_wsplitpath**|\<stdlib.h> \<veya wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

[_makepath](makepath-wmakepath.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Dosya Işleme](../../c-runtime-library/file-handling.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_makepath, _wmakepath](makepath-wmakepath.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[_splitpath_s, _wsplitpath_s](splitpath-s-wsplitpath-s.md)<br/>
