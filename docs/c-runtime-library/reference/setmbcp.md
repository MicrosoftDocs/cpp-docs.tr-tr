---
title: _setmbcp
ms.date: 11/04/2016
apiname:
- _setmbcp
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
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _setmbcp
- setmbcp
helpviewer_keywords:
- setmbcp function
- _setmbcp function
- multibyte code pages
ms.assetid: cfde53b5-0b73-4684-81b1-a8d3aafc85de
ms.openlocfilehash: c1f4967baa5fda68a7df33bcd08935dca23fab16
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62356465"
---
# <a name="setmbcp"></a>_setmbcp

Yeni bir çok baytlı kod sayfasına ayarlar.

## <a name="syntax"></a>Sözdizimi

```C
int _setmbcp(
   int codepage
);
```

### <a name="parameters"></a>Parametreler

*kod sayfası*<br/>
Yeni kod sayfası ayarı için çok baytlı rutinleri yerel ayarlardan bağımsızdır.

## <a name="return-value"></a>Dönüş Değeri

Kod sayfası başarılı bir şekilde ayarlanmışsa 0 döndürür. İçin bir geçersiz kod sayfası değeri sağlanmazsa *codepage*, -1 ve kod sayfası ayarı değiştirilmemiş döndürür. Kümeleri **errno** için **EINVAL** bir bellek ayırma hatası oluşursa.

## <a name="remarks"></a>Açıklamalar

**_Setmbcp** işlevi yeni bir çok baytlı kod sayfasını belirtir. Varsayılan olarak, çalışma zamanı sistemi, çok baytlı kod sayfasına otomatik olarak sistem varsayılan ANSI kod sayfasına ayarlar. Çok baytlı kod sayfası ayarı, yerel ayara bağımlı olmayan tüm çok baytlı yordamlarını etkiler. Ancak, istemek olası **_setmbcp** geçerli yerel ayar için tanımlanan kod sayfası kullanmak için (bildirim sabitleri aşağıdaki listesini görmek ve davranışı sonuçları ilişkili). Çok baytlı kod sayfası yerine yerel ayar kod sayfası bağımlı olan çok baytlı yordamların bir listesi için bkz. [baytlı karakter sıralarının yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md).

Çok baytlı kod sayfası, çok baytlı karakter işleme göre aşağıdaki çalışma zamanı kitaplığı yordamları da etkiler:

||||
|-|-|-|
|[_exec işlevleri](../../c-runtime-library/exec-wexec-functions.md)|[_mktemp](mktemp-wmktemp.md)|[_stat](stat-functions.md)|
|[_fullpath](fullpath-wfullpath.md)|[_spawn işlevleri](../../c-runtime-library/spawn-wspawn-functions.md)|[_tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md)|
|[_makepath](makepath-wmakepath.md)|[_splitpath](splitpath-wsplitpath.md)|[tmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)|

Ayrıca, çok baytlı karakter aldığınız tüm çalışma zamanı kitaplık yordamları *argv* veya *envp* program bağımsız değişkenleri olarak parametreler (gibi **_exec** ve **_spawn** aileleri) bu dizeler çok baytlı kod sayfasına göre işleyin. Bu nedenle, bu yordamların de bir çağrı tarafından etkilenir **_setmbcp** , çok baytlı kod sayfasını değiştirir.

*Codepage* bağımsız değişkeni aşağıdaki değerlerden birine ayarlanabilir:

- **_MB_CP_ANSI** kullanım ANSI kod sayfası elde program başlangıcında işletim sisteminden.

- **_MB_CP_LOCALE** geçerli yerel kod sayfası elde edilen önceki çağrısından kullanım [setlocale](setlocale-wsetlocale.md).

- **_MB_CP_OEM** kullanım OEM kod sayfası elde program başlangıcında işletim sisteminden.

- **_MB_CP_SBCS** tek baytlı kod sayfasını kullanın. Kod sayfası ayarlandığında **_MB_CP_SBCS**, rutin gibi [_ismbblead](ismbblead-ismbblead-l.md) her zaman false döndürür.

- Değer bir ANSI, OEM veya diğer işletim sistemi-destekli kod sayfası (UTF-7 ve UTF-8, desteklenmeyen) dışında olmasına bakılmaksızın başka geçerli kod sayfasına bir değer.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_setmbcp**|\<Mbctype.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[_getmbcp](getmbcp.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
