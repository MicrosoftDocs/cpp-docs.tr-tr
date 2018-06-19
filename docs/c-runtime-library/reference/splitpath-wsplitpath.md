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
ms.openlocfilehash: 220e2befc40dba342a7f8c2aa4c94294bc667ce0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32411428"
---
# <a name="splitpath-wsplitpath"></a>_splitpath, _wsplitpath

Bir yol adı bileşenlerine bölün. Bu işlevlerin daha güvenli sürümü, bkz: [_splitpath_s, _wsplitpath_s](splitpath-s-wsplitpath-s.md).

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

*Sürücü* sürücü harfini izleyen iki nokta ile (**:**). Geçirebilirsiniz **NULL** sürücü harfi gerekmiyorsa, bu parametre için.

*dir* dizin yolu, eğik dahil olmak üzere. Eğik ( **/** ), ters eğik çizgi ( **\\** ), ya da her ikisini de kullanılabilir. Geçirebilirsiniz **NULL** dizin yolu gerekmiyorsa, bu parametre için.

*fname* temel dosya adı (uzantısı yok). Geçirebilirsiniz **NULL** filename gerekmiyorsa, bu parametre için.

*ext* dönem baştaki dahil olmak üzere, dosya adı uzantısı (**.**). Geçirebilirsiniz **NULL** dosya adı uzantısı gerekmez, bu parametre için.

## <a name="remarks"></a>Açıklamalar

**_Splitpath** işlevi dört bileşenlerine yolunu keser. **_splitpath** şu anda kullanımda birden çok baytlı kod sayfasına göre çok baytlı karakter sıralarının algılamayı çok baytlı karakter dizesi bağımsız değişkenleri uygun şekilde otomatik olarak yönetir. **_wsplitpath** bir joker karakter sürümü **_splitpath**; bağımsız değişkenleri **_wsplitpath** joker karakter dizelerdir. Bu işlevler aynı şekilde aksi davranır.

**Güvenlik Notu** bu işlevlerin bir arabellek taşması sorunu duruma olası bir tehdit doğurur. Arabellek Taşması, sık yöntemi bir unwarranted ayrıcalıkların sonuçlanan sistem saldırı sorunlardır. Daha fazla bilgi için bkz: [önleme arabellek taşmasına neden](http://msdn.microsoft.com/library/windows/desktop/ms717795). Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [_splitpath_s, _wsplitpath_s](splitpath-s-wsplitpath-s.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsplitpath**|**_splitpath**|**_splitpath**|**_wsplitpath**|

Her bileşenin tam yolunun ayrı bir arabellek depolanır; bildirim sabitleri **_max_drıve**, **_max_dır**, **_MAX_FNAME**, ve **_MAX_EXT** (STDLIB içinde tanımlanmıştır. H) her dosya bileşeni için en büyük boyutu belirtin. Karşılık gelen bildirim sabitleri büyük olan dosya bileşenleri yığın bozulması neden.

Her arabellek olası arabellek taşması önlemek için karşılık gelen bildirim sabit değer olarak büyük olması gerekir.

Aşağıdaki tabloda bildirim sabitleri değerleri listelenmektedir.

|Ad|Değer|
|----------|-----------|
|**_MAX_DRIVE**|3|
|**_MAX_DIR**|256|
|**_MAX_FNAME**|256|
|**_MAX_EXT**|256|

Tam yolu (örneğin, bir dosya adı), bileşen içermiyorsa **_splitpath** atar karşılık gelen arabellekleri dizelere boş.

Geçirebilirsiniz **NULL** için **_splitpath** dışında herhangi bir parametre için *yolu* , gerek yoktur.

Varsa *yolu* olan **NULL**, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa **errno** ayarlanır **EINVAL** ve işlevi döndürür **EINVAL**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_splitpath**|\<stdlib.h >|
|**_wsplitpath**|\<stdlib.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bkz [_makepath](makepath-wmakepath.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_makepath, _wmakepath](makepath-wmakepath.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[_splitpath_s, _wsplitpath_s](splitpath-s-wsplitpath-s.md)<br/>
