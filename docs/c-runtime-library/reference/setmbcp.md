---
title: _setmbcp
ms.date: 11/04/2016
api_name:
- _setmbcp
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
- api-ms-win-crt-locale-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _setmbcp
- setmbcp
helpviewer_keywords:
- setmbcp function
- _setmbcp function
- multibyte code pages
ms.assetid: cfde53b5-0b73-4684-81b1-a8d3aafc85de
ms.openlocfilehash: 1db6a83bd864180d513f61cf255bd862283a6cd0
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948208"
---
# <a name="_setmbcp"></a>_setmbcp

Yeni bir çok baytlı kod sayfası ayarlar.

## <a name="syntax"></a>Sözdizimi

```C
int _setmbcp(
   int codepage
);
```

### <a name="parameters"></a>Parametreler

*sayfasının*<br/>
Yerel ayarda bağımsız çok baytlı yordamlar için yeni kod sayfası ayarı.

## <a name="return-value"></a>Dönüş Değeri

Kod sayfası başarıyla ayarlandıysa 0 döndürür. *Kod sayfası için geçersiz*bir kod sayfası değeri sağlanırsa,-1 döndürür ve kod sayfası ayarı değiştirilmez. Bir bellek ayırma hatası oluşursa, **errno** 'ı **EINVAL** olarak ayarlar.

## <a name="remarks"></a>Açıklamalar

**_Setmbcp** işlevi yeni bir çok baytlı kod sayfası belirtir. Varsayılan olarak, çalışma zamanı sistemi, çok baytlı kod sayfasını otomatik olarak sistem varsayılan ANSI kod sayfasına ayarlar. Çok baytlı kod sayfası ayarı, yerel ayara bağımlı olmayan tüm çok baytlı yordamları etkiler. Ancak, **_setmbcp** 'nin geçerli yerel ayar için tanımlanan kod sayfasını kullanmasını söylemek mümkündür (aşağıdaki bildirim sabitleri ve ilgili davranış sonuçları listesine bakın). Çok baytlı kod sayfası yerine yerel ayar kodu sayfasına bağımlı çok baytlı yordamların bir listesi için bkz. [çok baytlı karakter dizileri yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md).

Çok baytlı kod sayfası, aşağıdaki çalışma zamanı kitaplığı yordamlarına göre çok baytlı karakter işlemeyi da etkiler:

||||
|-|-|-|
|[_exec işlevleri](../../c-runtime-library/exec-wexec-functions.md)|[_mktemp](mktemp-wmktemp.md)|[_stat](stat-functions.md)|
|[_fullpath](fullpath-wfullpath.md)|[_üretme işlevleri](../../c-runtime-library/spawn-wspawn-functions.md)|[_tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md)|
|[_makepath](makepath-wmakepath.md)|[_splitpath](splitpath-wsplitpath.md)|[tmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)|

Buna ek olarak, çok baytlı karakter *argv* veya *envp* program bağımsız değişkenlerini parametre olarak ( **_exec** ve **_üretme** aileleri gibi) alan tüm çalışma zamanı kitaplığı yordamları, bu dizeleri çok baytlı kod sayfasına göre işler. Bu nedenle bu yordamlar, çok baytlı kod sayfasını değiştiren **_setmbcp** çağrısıyla de etkilenir.

*CodePage* bağımsız değişkeni aşağıdaki değerlerden herhangi birine ayarlanabilir:

- **_Mb_cp_ansi** Program başlangıcında işletim sisteminden alınan ANSI kod sayfasını kullanın.

- **_Mb_cp_locale** Önceki bir [setlocale](setlocale-wsetlocale.md)çağrısından elde edilen geçerli yerel ayarın kod sayfasını kullanın.

- **_Mb_cp_oem** Program başlangıcında işletim sisteminden alınan OEM kod sayfasını kullanın.

- **_Mb_cp_sbcs** Tek baytlı kod sayfasını kullanın. Kod sayfası **_Mb_cp_sbcs**olarak ayarlandığında, [_ismbblider](ismbblead-ismbblead-l.md) gibi bir yordam her zaman false döndürür.

- Değerin bir ANSI, OEM veya diğer işletim sistemi tarafından desteklenen kod sayfası (UTF-7 ve UTF-8 hariç) olmasına bakılmaksızın herhangi bir diğer geçerli kod sayfası değeri.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_setmbcp**|\<Mbctype. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[_getmbcp](getmbcp.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
