---
description: 'Hakkında daha fazla bilgi edinin: _splitpath _wsplitpath'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: d270cf15c00c42f350dafe0cd45dddbb2f6594c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97292318"
---
# <a name="_splitpath-_wsplitpath"></a>_splitpath, _wsplitpath

Bir yol adını bileşenlere bölün. Bu işlevlerin daha güvenli sürümleri mevcuttur, bkz. [_splitpath_s, _wsplitpath_s](splitpath-s-wsplitpath-s.md).

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

*Yolun*<br/>
Tam yol.

*sürücü*<br/>
Sürücü harfi, ardından iki nokta üst üste (**:**). Sürücü harfine ihtiyacınız yoksa, bu parametre için **null değeri** geçirebilirsiniz.

*öğesini*<br/>
Sondaki eğik çizgi dahil dizin yolu. Eğik çizgi ( **/** ), ters eğik çizgi ( **\\** ) veya her ikisi de kullanılabilir. Dizin yoluna ihtiyacınız yoksa, bu parametre için **null değeri** geçirebilirsiniz.

*fname*<br/>
Taban dosya adı (uzantı yok). Dosya adına ihtiyacınız yoksa, bu parametre için **null değeri** geçirebilirsiniz.

*leri*<br/>
Baştaki nokta (**.**) dahil dosya adı uzantısı. Dosya adı uzantısına ihtiyacınız yoksa, bu parametre için **null değeri** geçirebilirsiniz.

## <a name="remarks"></a>Açıklamalar

**_Splitpath** işlevi bir yolu dört bileşene ayırır. **_splitpath** çok baytlı karakter dizesi bağımsız değişkenlerini uygun şekilde otomatik olarak işler ve çok baytlı karakter dizilerini kullanımda olan çok baytlı kod sayfasına göre tanıyor. **_wsplitpath** , **_splitpath** geniş karakterli bir sürümüdür; **_wsplitpath** bağımsız değişkenler geniş karakterli dizelerdir. Bu işlevler, aynı şekilde davranır.

**Güvenlik notunun** Bu işlevler, bir arabellek taşması sorunu ile ilgili olası bir tehdit doğurur. Arabellek taşması sorunları, sistem saldırılarına karşı sık kullanılan bir yöntemdir ve bu da garanti edilmemiş ayrıcalık yükselmesine neden olur. Daha fazla bilgi için bkz. [arabellek taşmalarını önleme](/windows/win32/SecBP/avoiding-buffer-overruns). Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz. [_splitpath_s, _wsplitpath_s](splitpath-s-wsplitpath-s.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsplitpath**|**_splitpath**|**_splitpath**|**_wsplitpath**|

Tam yolun her bileşeni ayrı bir arabellekte saklanır; bildirim sabitleri **_MAX_DRIVE**, **_MAX_DIR**, **_MAX_FNAME** ve **_MAX_EXT** (Stdlib içinde tanımlanmıştır). H) her bir dosya bileşeni için en büyük boyutu belirtin. Karşılık gelen bildirim sabitlerinden daha büyük olan dosya bileşenleri yığın bozulması oluşmasına neden olur.

Olası arabellek taşmasını önlemek için her bir arabelleğin karşılık gelen bildirim sabiti kadar büyük olması gerekir.

Aşağıdaki tablo, bildirim sabitlerinin değerlerini listelemektedir.

|Ad|Değer|
|----------|-----------|
|**_MAX_DRIVE**|3|
|**_MAX_DIR**|256|
|**_MAX_FNAME**|256|
|**_MAX_EXT**|256|

Tam yol bir bileşen (örneğin, bir dosya adı) içermiyorsa **_splitpath** , karşılık gelen arabelleklere boş dizeler atar.

İhtiyacınız *olmayan bir* parametre Için **_splitpath** **null değeri** geçirebilirsiniz.

*Yol* **null** ise, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, **errno** **EINVAL** olarak ayarlanır ve işlev **EINVAL** döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_splitpath**|\<stdlib.h>|
|**_wsplitpath**|\<stdlib.h> veya \<wchar.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[_Makepath](makepath-wmakepath.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_makepath, _wmakepath](makepath-wmakepath.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[_splitpath_s, _wsplitpath_s](splitpath-s-wsplitpath-s.md)<br/>
