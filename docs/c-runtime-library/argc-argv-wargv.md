---
title: __argc, __argv, __wargv
ms.date: 11/04/2016
apiname:
- __wargv
- __argv
- __argc
apilocation:
- msvcrt120.dll
apitype: DLLExport
f1_keywords:
- __argv
- __argc
- __wargv
helpviewer_keywords:
- __argv
- __wargv
- __argc
ms.assetid: 17001b0a-04ad-4762-b3a6-c54847f02d7c
ms.openlocfilehash: f428d81215193361a409473a411eb5c4d91fa997
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57743304"
---
# <a name="argc-argv-wargv"></a>__argc, __argv, __wargv

`__argc` Genel değişkenidir programa geçirilen komut satırı bağımsız değişkenleri sayısını. `__argv` program bağımsız değişkenleri içeren bir tek baytlı karakter veya çok byte karakterli dize dizisi bir işaretçidir ve `__wargv` program bağımsız değişkenleri içeren bir geniş karakterli dize dizisi bir işaretçisidir. Bu genel değişkenler bağımsız değişkenleri sağlayın `main` veya `wmain`.

## <a name="syntax"></a>Sözdizimi

```
extern int __argc;
extern char ** __argv;
extern wchar_t ** __wargv;
```

## <a name="remarks"></a>Açıklamalar

Kullanan bir programda `main` işlevi `__argc` ve `__argv` program başlangıcında programı başlatmak için kullanılan komut satırını kullanarak başlatılır. Komut satırı bağımsız ayrıştırılır ve joker karakterler genişletilir. Bağımsız değişken sayısı atandığı `__argc` bağımsız değişkeni dize yığında ayrılır ve bağımsız değişkenlerin dizisine bir işaretçi atandığı `__argv`. Geniş karakterler kullanmak için derlenmiş bir programda ve `wmain` işlevi, bağımsız değişkenler Ayrıştırılan ve joker karakterler geniş karakterli dize olarak genişletilmiş ve bağımsız değişkeni dize dizisine bir işaretçi atandığı `__wargv`.

Kullanmak için geçirilen bağımsız değişkenler tavsiye ederiz taşınabilir kod için `main` programın komut satırı bağımsız değişkenlerini almak için.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE tanımlı değil|_UNICODE tanımlanmış|
|---------------------|---------------------------|-----------------------|
|`__targv`|`__argv`|`__wargv`|

## <a name="requirements"></a>Gereksinimler

|Genel değişkeni|Gerekli başlık|
|---------------------|---------------------|
|`__argc`, `__argv`, `__wargv`|\<stdlib.h>, \<cstdlib> (C++)|

`__argc`, `__argv`, ve `__wargv` Microsoft uzantılarıdır. Uyumluluk bilgileri için bkz. [Uyumluluk](../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Global Değişkenler](../c-runtime-library/global-variables.md)<br/>
[Ana: Program başlatma](../cpp/main-program-startup.md)<br/>
[main Yerine wmain Kullanma](../cpp/using-wmain-instead-of-main.md)
