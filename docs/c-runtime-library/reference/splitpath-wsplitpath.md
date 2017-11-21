---
title: _splitpath, _wsplitpath | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
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
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6e1b8dd85a8ddbfbf64af000eee8cacca26bf1ce
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="splitpath-wsplitpath"></a>_splitpath, _wsplitpath
Bir yol adı bileşenlerine bölün. Bu işlevlerin daha güvenli sürümü, bkz: [_splitpath_s, _wsplitpath_s](../../c-runtime-library/reference/splitpath-s-wsplitpath-s.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
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
  
#### <a name="parameters"></a>Parametreler  
 `path`  
 Tam yolu.  
  
 `drive`  
 Sürücü harfini izleyen iki nokta ile (`:`). Geçirebilirsiniz `NULL` sürücü harfi gerekmiyorsa, bu parametre için.  
  
 `dir`  
 Sondaki eğik çizgi dahil olmak üzere dizin yolu. Eğik ( `/` ), ters eğik çizgi ( `\` ), ya da her ikisini de kullanılabilir. Geçirebilirsiniz `NULL` dizin yolu gerekmiyorsa, bu parametre için.  
  
 `fname`  
 Temel dosya adı (uzantısı yok). Geçirebilirsiniz `NULL` filename gerekmiyorsa, bu parametre için.  
  
 `ext`  
 Dosya adı uzantısı, dönem baştaki dahil olmak üzere (`.`). Geçirebilirsiniz `NULL` dosya adı uzantısı gerekmez, bu parametre için.  
  
## <a name="remarks"></a>Açıklamalar  
 `_splitpath` İşlevi dört bileşenlerine yolunu keser. `_splitpath`çok baytlı karakter sıralarının şu anda kullanımda birden çok baytlı kod sayfasına göre algılamayı çok baytlı karakter dizesi bağımsız değişkenleri uygun şekilde otomatik olarak yönetir. `_wsplitpath`bir joker karakter sürümü `_splitpath`; bağımsız değişkenleri `_wsplitpath` joker karakter dizelerdir. Bu işlevler aynı şekilde aksi davranır.  
  
 **Güvenlik Notu** bu işlevlerin bir arabellek taşması sorunu duruma olası bir tehdit doğurur. Arabellek Taşması, sık yöntemi bir unwarranted ayrıcalıkların sonuçlanan sistem saldırı sorunlardır. Daha fazla bilgi için bkz: [önleme arabellek taşmasına neden](http://msdn.microsoft.com/library/windows/desktop/ms717795). Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [_splitpath_s, _wsplitpath_s](../../c-runtime-library/reference/splitpath-s-wsplitpath-s.md).  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tsplitpath`|`_splitpath`|`_splitpath`|`_wsplitpath`|  
  
 Her bileşenin tam yolunun ayrı bir arabellek depolanır; bildirim sabitleri `_MAX_DRIVE`, `_MAX_DIR`, `_MAX_FNAME`, ve `_MAX_EXT` (STDLIB içinde tanımlanmıştır. H) her dosya bileşeni için en büyük boyutu belirtin. Karşılık gelen bildirim sabitleri büyük olan dosya bileşenleri yığın bozulması neden.  
  
 Her arabellek olası arabellek taşması önlemek için karşılık gelen bildirim sabit değer olarak büyük olması gerekir.  
  
 Aşağıdaki tabloda bildirim sabitleri değerleri listelenmektedir.  
  
|Ad|Değer|  
|----------|-----------|  
|_MAX_DRIVE|3|  
|_MAX_DIR|256|  
|_MAX_FNAME|256|  
|_MAX_EXT|256|  
  
 Tam yolu (örneğin, bir dosya adı), bileşen içermiyorsa `_splitpath` atar karşılık gelen arabellekleri dizelere boş.  
  
 Geçirebilirsiniz `NULL` için `_splitpath` dışında herhangi bir parametre için `path` , gerek yoktur.  
  
 Varsa `path` olan `NULL`, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa `errno` ayarlanır `EINVAL` ve işlevi döndürür `EINVAL`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_splitpath`|\<stdlib.h >|  
|`_wsplitpath`|\<stdlib.h > veya \<wchar.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [_makepath](../../c-runtime-library/reference/makepath-wmakepath.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dosya işleme](../../c-runtime-library/file-handling.md)   
 [_fullpath, _wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [_makepath, _wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [_splitpath_s, _wsplitpath_s](../../c-runtime-library/reference/splitpath-s-wsplitpath-s.md)