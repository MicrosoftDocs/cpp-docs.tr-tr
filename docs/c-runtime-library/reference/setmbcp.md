---
title: _setmbcp | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- setmbcp function
- _setmbcp function
- multibyte code pages
ms.assetid: cfde53b5-0b73-4684-81b1-a8d3aafc85de
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2e879d4cf6ebc7cb7f61199b3bb52f1a5e3f5389
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="setmbcp"></a>_setmbcp

Yeni bir çok baytlı kod sayfası ayarlar.

## <a name="syntax"></a>Sözdizimi

```C
int _setmbcp(
   int codepage
);
```

### <a name="parameters"></a>Parametreler

*kod sayfası*<br/>
Yerel ayar bağımsız birden çok baytlı yordamları için yeni kod sayfası ayarı.

## <a name="return-value"></a>Dönüş Değeri

Kod sayfası başarılı bir şekilde ayarlanmışsa, 0 döndürür. İçin bir geçersiz kod sayfası değer sağlanmazsa *codepage*, -1 ve kod sayfası ayarı değiştirilmemiş döndürür. Ayarlar **errno** için **EINVAL** bir bellek ayırma hatası oluşursa.

## <a name="remarks"></a>Açıklamalar

**_Setmbcp** işlevi yeni birden çok baytlı kod sayfasını belirtir. Varsayılan olarak, çalışma zamanı sistem sistem varsayılan ANSI kod sayfasına birden çok baytlı kod sayfası otomatik olarak ayarlar. Birden çok baytlı kod sayfası ayarı yerel ayara bağımlı olmayan tüm birden çok baytlı yordamları etkiler. Ancak, bu istemeniz mümkündür **_setmbcp** geçerli yerel ayar için tanımlanan kod sayfasını kullanmak üzere (bildirim sabitleri aşağıdaki listesini görmek ve davranış sonuçları ilişkili). Birden çok baytlı kod sayfası yerine yerel ayar kod sayfası bağımlı birden çok baytlı yordamları bir listesi için bkz: [çok baytlı karakter sıralarının yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md).

Birden çok baytlı kod sayfası, çok baytlı karakter işleme göre aşağıdaki çalışma zamanı kitaplığı yordamları da etkiler:

||||
|-|-|-|
|[_exec işlevleri](../../c-runtime-library/exec-wexec-functions.md)|[_mktemp](mktemp-wmktemp.md)|[_stat](stat-functions.md)|
|[_fullpath](fullpath-wfullpath.md)|[_spawn işlevleri](../../c-runtime-library/spawn-wspawn-functions.md)|[_tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md)|
|[_makepath](makepath-wmakepath.md)|[_splitpath](splitpath-wsplitpath.md)|[tmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)|

Ayrıca, çok baytlı karakter aldığınız tüm çalışma zamanı kitaplığı yordamları *argv* veya *envp* program bağımsız değişken olarak parametreler (gibi **_exec** ve **_spawn** aileleri) birden çok baytlı kod sayfasına göre bu dizeler işlem. Bu nedenle, bu yordamlar ayrıca bir çağrı tarafından etkilenen **_setmbcp** birden çok baytlı kod sayfası değiştirir.

*Codepage* bağımsız değişkeni aşağıdaki değerlerden birine ayarlanabilir:

- **_MB_CP_ANSI** kullanım ANSI kod sayfası elde program başlangıçta işletim sisteminden.

- **_MB_CP_LOCALE** geçerli yerel kod sayfası elde önceki çağrısından kullanım [setlocale](setlocale-wsetlocale.md).

- **_MB_CP_OEM** kullanım OEM kod sayfası elde program başlangıçta işletim sisteminden.

- **_MB_CP_SBCS** kullanım tek baytlı kod sayfası. Kod sayfası ayarlandığında **_MB_CP_SBCS**, rutin gibi [_ismbblead](ismbblead-ismbblead-l.md) her zaman false döndürür.

- Değer ANSI, OEM veya diğer işletim sistemi-destekli kod sayfası (UTF-7 ve dışında UTF-8 desteklenmez) olmasına bakılmaksızın herhangi diğer geçerli kod sayfası bir değer.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_setmbcp**|\<Mbctype.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[_getmbcp](getmbcp.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
