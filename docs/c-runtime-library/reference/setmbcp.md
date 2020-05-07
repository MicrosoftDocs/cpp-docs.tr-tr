---
title: _setmbcp
ms.date: 4/2/2020
api_name:
- _setmbcp
- _o__setmbcp
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 18712661b2bda1eaaf0c583b922ad73a781b4abc
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82918823"
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

**_Setmbcp** işlevi yeni bir çok baytlı kod sayfasını belirtir. Varsayılan olarak, çalışma zamanı sistemi, çok baytlı kod sayfasını otomatik olarak sistem varsayılan ANSI kod sayfasına ayarlar. Çok baytlı kod sayfası ayarı, yerel ayara bağımlı olmayan tüm çok baytlı yordamları etkiler. Ancak, geçerli yerel ayar için tanımlanan kod sayfasını kullanmak üzere **_setmbcp** söylemek mümkündür (aşağıdaki bildirim sabitleri ve ilgili davranış sonuçları listesine bakın). Çok baytlı kod sayfası yerine yerel ayar kodu sayfasına bağımlı çok baytlı yordamların bir listesi için bkz. [çok baytlı karakter dizileri yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md).

Çok baytlı kod sayfası, aşağıdaki çalışma zamanı kitaplığı yordamlarına göre çok baytlı karakter işlemeyi da etkiler:

||||
|-|-|-|
|[_exec işlevleri](../../c-runtime-library/exec-wexec-functions.md)|[_mktemp](mktemp-wmktemp.md)|[_stat](stat-functions.md)|
|[_fullpath](fullpath-wfullpath.md)|[_spawn işlevleri](../../c-runtime-library/spawn-wspawn-functions.md)|[_tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md)|
|[_makepath](makepath-wmakepath.md)|[_splitpath](splitpath-wsplitpath.md)|[tmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)|

Ayrıca, ( **_exec** ve **_spawn** aileleri gibi) çok baytlı karakter *argv* veya *envp* program bağımsız değişkenlerini parametre olarak alan tüm çalışma zamanı kitaplığı yordamları, bu dizeleri çok baytlı kod sayfasına göre işler. Bu nedenle bu yordamlar, çok baytlı kod sayfasını değiştiren **_setmbcp** çağrısıyla de etkilenir.

*CodePage* bağımsız değişkeni aşağıdaki değerlerden herhangi birine ayarlanabilir:

- **_MB_CP_ANSI** Program başlangıcında işletim sisteminden alınan ANSI kod sayfasını kullanın.

- **_MB_CP_LOCALE** Önceki bir [setlocale](setlocale-wsetlocale.md)çağrısından elde edilen geçerli yerel ayarın kod sayfasını kullanın.

- **_MB_CP_OEM** Program başlangıcında işletim sisteminden alınan OEM kod sayfasını kullanın.

- **_MB_CP_SBCS** Tek baytlı kod sayfasını kullanın. Kod sayfası **_MB_CP_SBCS**olarak ayarlandığında, [_ismbblead](ismbblead-ismbblead-l.md) gibi bir yordam her zaman false döndürür.

- **_MB_CP_UTF8** UTF-8 kullanın.  Kod sayfası **_MB_CP_UTF8**olarak ayarlandığında, [_ismbblead](ismbblead-ismbblead-l.md) gibi bir yordam her zaman false döndürür.

- Değerin bir ANSI, OEM veya diğer işletim sistemi tarafından desteklenen kod sayfası (desteklenmeyen UTF-7 hariç) olmasına bakılmaksızın herhangi bir diğer geçerli kod sayfası değeri.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_setmbcp**|\<Mbctype. h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[_getmbcp](getmbcp.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
