---
title: _splitpath_s, _wsplitpath_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
apitype: DLLExport
f1_keywords:
- _wsplitpath_s
- splitpath_s
- _splitpath_s
- wsplitpath_s
dev_langs:
- C++
helpviewer_keywords:
- splitpath_s function
- pathnames
- _splitpath_s function
- _wsplitpath_s function
- path names
- wsplitpath_s function
ms.assetid: 30fff3e2-cd00-4eb6-b5a2-65db79cb688b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e5fd1407aa6c2b7630e0720eeec179ca27e7d31a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32417438"
---
# <a name="splitpaths-wsplitpaths"></a>_splitpath_s, _wsplitpath_s

Bir yol adı bileşenlerine keser. Sürümleri bunlar [_splitpath, _wsplitpath](splitpath-wsplitpath.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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

*Yol*<br/>
Tam yolu.

*Sürücü*<br/>
Sürücü harfini izleyen iki nokta ile (**:**). Geçirebilirsiniz **NULL** sürücü harfi gerekmiyorsa, bu parametre için.

*driveNumberOfElements*<br/>
Boyutunu *sürücü* tek baytlı veya uluslararası karakter arabellek. Varsa *sürücü* olan **NULL**, bu değerin 0 olması gerekir.

*Dir*<br/>
Sondaki eğik çizgi dahil olmak üzere dizin yolu. Eğik ( **/** ), ters eğik çizgi ( **\\** ), ya da her ikisini de kullanılabilir. Geçirebilirsiniz **NULL** dizin yolu gerekmiyorsa, bu parametre için.

*dirNumberOfElements*<br/>
Boyutunu *dir* tek baytlı veya uluslararası karakter arabellek. Varsa *dir* olan **NULL**, bu değerin 0 olması gerekir.

*fname*<br/>
Temel dosya adı (uzantısı olmadan). Geçirebilirsiniz **NULL** filename gerekmiyorsa, bu parametre için.

*nameNumberOfElements*<br/>
Boyutunu *fname* tek baytlı veya uluslararası karakter arabellek. Varsa *fname* olan **NULL**, bu değerin 0 olması gerekir.

*ext*<br/>
Dosya adı uzantısı, dönem baştaki dahil olmak üzere (**.**). Geçirebilirsiniz **NULL** dosya adı uzantısı gerekmez, bu parametre için.

*extNumberOfElements*<br/>
Boyutunu *ext* tek baytlı veya uluslararası karakter arabellek. Varsa *ext* olan **NULL**, bu değerin 0 olması gerekir.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır; hatasında bir hata kodu.

### <a name="error-conditions"></a>Hata koşulları

|Koşul|Dönüş Değeri|
|---------------|------------------|
|*yol* olan **NULL**|**EINVAL**|
|*Sürücü* olan **NULL**, *driveNumberOfElements* sıfır değil|**EINVAL**|
|*Sürücü* olan olmayan**NULL**, *driveNumberOfElements* sıfır|**EINVAL**|
|*dir* olan **NULL**, *dirNumberOfElements* sıfır değil|**EINVAL**|
|*dir* olan olmayan**NULL**, *dirNumberOfElements* sıfır|**EINVAL**|
|*fname* olan **NULL**, *nameNumberOfElements* sıfır değil|**EINVAL**|
|*fname* olan olmayan**NULL**, *nameNumberOfElements* sıfır|**EINVAL**|
|*ext* olan **NULL**, *extNumberOfElements* sıfır değil|**EINVAL**|
|*ext* olan olmayan**NULL**, *extNumberOfElements* sıfır|**EINVAL**|

Yukarıdaki koşullardan herhangi biri meydana gelirse, geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md) . Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler kümesi **errno** için **EINVAL** ve geri dönüp **EINVAL**.

Herhangi bir arabellek ise sonucu tutmak için çok kısa, bu işlevler dizeleri boş, ayarlamak için tüm arabellekler temizleyin **errno** için **ERANGE**ve geri dönüp **ERANGE**.

## <a name="remarks"></a>Açıklamalar

**_Splitpath_s** işlevi dört bileşenlerine yolunu keser. **_splitpath_s** şu anda kullanımda birden çok baytlı kod sayfasına göre çok baytlı karakter sıralarının algılamayı çok baytlı karakter dizesi bağımsız değişkenleri uygun şekilde otomatik olarak yönetir. **_wsplitpath_s** bir joker karakter sürümü **_splitpath_s**; bağımsız değişkenleri **_wsplitpath_s** joker karakter dizelerdir. Aksi takdirde bu işlevler aynı şekilde davranır

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsplitpath_s**|**_splitpath_s**|**_splitpath_s**|**_wsplitpath_s**|

Her bileşenin tam yolunun ayrı bir arabellek depolanır; bildirim sabitleri **_max_drıve**, **_max_dır**, **_MAX_FNAME**, ve **_MAX_EXT** (STDLIB içinde tanımlanmıştır. H) her dosya bileşeni için izin verilen en büyük boyutu belirtin. Bileşenleri karşılık gelen bildirim sabitleri yığın bozulması neden daha büyük dosya.

Aşağıdaki tabloda bildirim sabitleri değerleri listelenmektedir.

|Ad|Değer|
|----------|-----------|
|_MAX_DRIVE|3|
|_MAX_DIR|256|
|_MAX_FNAME|256|
|_MAX_EXT|256|

Tam yolu (örneğin, bir dosya adı), bileşen içermiyorsa **_splitpath_s** karşılık gelen arabellek boş bir dize atar.

C++'da, bu işlevler kullanılarak şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı, boyutu bağımsız değişkeniyle belirtme ihtiyacını ortadan arabellek uzunluğu bir otomatik olarak Infer. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).

Bu işlevler hata ayıklama sürümleri ilk 0xFD arabellekle doldurun. Bu davranışı devre dışı bırakmak için [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_splitpath_s**|\<stdlib.h >|
|**_wsplitpath_s**|\<stdlib.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bkz [_makepath_s, _wmakepath_s](makepath-s-wmakepath-s.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
[_splitpath, _wsplitpath](splitpath-wsplitpath.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_makepath, _wmakepath](makepath-wmakepath.md)<br/>
[_setmbcp](setmbcp.md)<br/>
