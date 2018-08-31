---
title: _splitpath, _wsplitpath | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wsplitpath
- _splitpath
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
apitype: DLLExport
f1_keywords:
- wsplitpath
- _splitpath
- splitpath
- _wsplitpath
- _tsplitpath
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 69123bfd07d992d96c504e538ded157c49991dab
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43221614"
---
# <a name="splitpath-wsplitpath"></a>_splitpath, _wsplitpath

Bir yol adı bileşenlere ayırmak. Bu işlevlerin daha güvenli sürümleri mevcuttur, bkz [_splitpath_s, _wsplitpath_s](splitpath-s-wsplitpath-s.md).

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

*yol* tam yolu.

*Sürücü* sürücü harfini izleyen iki nokta (**:**). Geçirebilirsiniz **NULL** sürücü harfini gerekmiyorsa, bu parametre için.

*dir* dizin yolu, eğik çizgi de dahil. İleri eğik çizgi ( **/** ), ters eğik çizgi ( **\\** ), veya her ikisi de kullanılabilir. Geçirebilirsiniz **NULL** dizin yolu gerekmiyorsa, bu parametre için.

*fname* temel dosya adı (uzantısı). Geçirebilirsiniz **NULL** filename gerekmiyorsa, bu parametre için.

*ext* dönem baştaki dahil olmak üzere, dosya adı uzantısı (**.**). Geçirebilirsiniz **NULL** dosya adı uzantısı gerekmiyorsa, bu parametre için.

## <a name="remarks"></a>Açıklamalar

**_Splitpath** işlevi bir yol dört bileşenlerine böler. **_splitpath** çok baytlı karakter sıralarını şu anda çok baytlı kod sayfasına göre algılamayı çok baytlı karakter dizesi bağımsız değişkenleri uygun şekilde otomatik olarak işler. **_wsplitpath** geniş karakterli sürümüdür **_splitpath**; bağımsız değişkenler **_wsplitpath** geniş karakterli dizelerdir. Bu işlevler, aynı şekilde davranır.

**Güvenlik Notu** bu işlevler bir arabellek taşması sorunu duruma olası bir tehdit doğurur. Arabellek taşması sorunları, sistem saldırı, bir unwarranted ayrıcalık yükseltilmesi ile sonuçlanan sık kullanılan bir yöntemdir. Daha fazla bilgi için [arabellek taşmalarını](/windows/desktop/SecBP/avoiding-buffer-overruns). Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz: [_splitpath_s, _wsplitpath_s](splitpath-s-wsplitpath-s.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsplitpath**|**_splitpath**|**_splitpath**|**_wsplitpath**|

Her bileşenin tam yolunun ayrı bir arabellek depolanır; bildirim sabitleri **_max_drıve**, **_max_dır**, **_MAX_FNAME**, ve **_MAX_EXT** (STDLIB içinde tanımlanır. H) her dosya bileşeni için en büyük boyutu belirtin. Karşılık gelen bildirim sabitleri daha büyük olan dosya bileşeni yığın bozulması neden.

Her arabellek olası arabellek taşması önlemek için karşılık gelen Bildirim sabiti büyük olmalıdır.

Aşağıdaki tabloda, bildirim sabitleri değerlerini listeler.

|Ad|Değer|
|----------|-----------|
|**_MAX_DRIVE**|3|
|**_MAX_DIR**|256|
|**_MAX_FNAME**|256|
|**_MAX_EXT**|256|

Tam yolu (örneğin, bir dosya adı), bir bileşen içermiyorsa **_splitpath** boş dizeleri karşılık gelen arabellekleri için atar.

Geçirebilirsiniz **NULL** için **_splitpath** dışında herhangi bir parametre için *yolu* , gerek yoktur.

Varsa *yolu* olduğu **NULL**, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **errno** ayarlanır **EINVAL** ve işlev döndürür **EINVAL**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_splitpath**|\<stdlib.h >|
|**_wsplitpath**|\<stdlib.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bakın [_makepath](makepath-wmakepath.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_makepath, _wmakepath](makepath-wmakepath.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[_splitpath_s, _wsplitpath_s](splitpath-s-wsplitpath-s.md)<br/>
