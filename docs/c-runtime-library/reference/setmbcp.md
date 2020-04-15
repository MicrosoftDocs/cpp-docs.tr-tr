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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 61086471c6194aaa8434d291647978bf891a8aea
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337599"
---
# <a name="_setmbcp"></a>_setmbcp

Yeni bir çok bayt kod sayfası ayarlar.

## <a name="syntax"></a>Sözdizimi

```C
int _setmbcp(
   int codepage
);
```

### <a name="parameters"></a>Parametreler

*Codepage*<br/>
Yerel denbağımsız çok bayt yordamları için yeni kod sayfası ayarı.

## <a name="return-value"></a>Dönüş Değeri

Kod sayfası başarıyla ayarlanırsa 0 döndürür. Geçersiz bir kod sayfası değeri kod sayfası için *sağlanırsa*, -1 döndürür ve kod sayfası ayarı değişmez. Bellek ayırma hatası oluşursa **errno'u** **EINVAL** olarak ayarlar.

## <a name="remarks"></a>Açıklamalar

**_setmbcp** işlevi yeni bir çok bayt kod sayfası belirtir. Varsayılan olarak, çalışma zamanı sistemi otomatik olarak sistem varsayılan ANSI kod sayfasına çok bayt kod sayfasını ayarlar. Çok bayt kod sayfası ayarı, yerel olarak bağımlı olmayan tüm çok bayt yordamlarını etkiler. Ancak, **_setmbcp** geçerli yerel alan için tanımlanan kod sayfasını kullanmaları için talimat vermek mümkündür (aşağıdaki bildirim sabitleri ve ilişkili davranış sonuçları listesine bakın). Çok bayt kod sayfası yerine yerel kod sayfasına bağlı olan çok bayt [yordamlarının](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)listesi için bkz.

Çok bayt kod sayfası, aşağıdaki çalışma zamanı kitaplığı yordamları tarafından çok bayt karakter işleme etkiler:

||||
|-|-|-|
|[_exec fonksiyonları](../../c-runtime-library/exec-wexec-functions.md)|[_mktemp](mktemp-wmktemp.md)|[_stat](stat-functions.md)|
|[_fullpath](fullpath-wfullpath.md)|[_spawn fonksiyonları](../../c-runtime-library/spawn-wspawn-functions.md)|[_tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md)|
|[_makepath](makepath-wmakepath.md)|[_splitpath](splitpath-wsplitpath.md)|[tmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)|

Buna ek olarak, parametreler **(_exec** ve **_spawn** aileleri gibi) olarak multibayt *karaktera argv* veya *envp* programı bağımsız değişkenleri alan tüm çalışma zamanı kitaplık yordamları bu dizeleri çok bayt kod sayfasına göre işler. Bu nedenle, bu yordamlar da çok bayt kod sayfasını değiştiren **_setmbcp** için bir çağrı etkilenir.

Kod sayfası bağımsız *değişkeni* aşağıdaki değerlerden herhangi biri için ayarlanabilir:

- **_MB_CP_ANSI** Program başlatmada işletim sisteminden elde edilen ANSI kod sayfasını kullanın.

- **_MB_CP_LOCALE** Önceki bir çağrıdan alınan geçerli yerel kodu sayfasını [kullanarak yerelliği ayarlayın.](setlocale-wsetlocale.md)

- **_MB_CP_OEM** Program başlatmada işletim sisteminden elde edilen OEM kod sayfasını kullanın.

- **_MB_CP_SBCS** Tek bayt kod sayfasını kullanın. Kod sayfası **_MB_CP_SBCS**ayarlandığında, [_ismbblead](ismbblead-ismbblead-l.md) gibi bir yordam her zaman yanlış döndürür.

- **_MB_CP_UTF8** UTF-8'i kullanın.  Kod sayfası **_MB_CP_UTF8**ayarlandığında, [_ismbblead](ismbblead-ismbblead-l.md) gibi bir yordam her zaman yanlış döndürür.

- Değerin ANSI, OEM veya işletim sistemi tarafından desteklenen diğer bir kod sayfası olup olmadığına bakılmaksızın diğer geçerli kod sayfa değeri (desteklenmeyen UTF-7 hariç).

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_setmbcp**|\<mbctype.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[_getmbcp](getmbcp.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
