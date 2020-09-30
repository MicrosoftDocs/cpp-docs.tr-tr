---
title: __argc, __argv, __wargv
description: Microsoft C çalışma zamanı kitaplığı genel sabitlerini __argc , __argv ve değerlerini açıklar __wargv .
ms.date: 11/04/2016
api_name:
- __wargv
- __argv
- __argc
api_location:
- msvcrt120.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __argv
- __argc
- __wargv
helpviewer_keywords:
- __argv
- __wargv
- __argc
ms.assetid: 17001b0a-04ad-4762-b3a6-c54847f02d7c
no-loc:
- __argc
- __argv
- __wargv
- main
- wmain
ms.openlocfilehash: 02c130be0d2dcb8e48d2bb5c75438c94003fc9dd
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91507598"
---
# <a name="no-loc__argc-no-loc__argv-no-loc__wargv"></a>__argc, __argv, __wargv

`__argc`Genel değişken, programa geçirilen komut satırı bağımsız değişkenlerinin sayısının sayısıdır. `__argv` , program bağımsız değişkenlerini içeren bir dizi tek baytlık karakter veya çok baytlı karakter dizelerinin bir işaretçisidir ve `__wargv` Program bağımsız değişkenlerini içeren geniş karakterli dizeler dizisinin bir işaretçisidir. Bu genel değişkenler, veya için bağımsız değişkenleri sağlar `main` `wmain` .

## <a name="syntax"></a>Sözdizimi

```C
extern int __argc;
extern char ** __argv;
extern wchar_t ** __wargv;
```

## <a name="remarks"></a>Açıklamalar

İşlevini kullanan bir programda ve programı `main`  `__argc` `__argv` başlatmak için kullanılan komut satırı kullanılarak program başlangıcında başlatılır. Komut satırı bağımsız bağımsız değişkenlere ayrıştırılır ve joker karakterler genişletilir. Bağımsız değişkenlerin sayısı öğesine atanır `__argc` ve bağımsız değişken dizeleri yığına ayrılır ve bağımsız değişkenlerin dizisine bir işaretçi atanır `__argv` . Geniş karakter ve bir işlev kullanmak üzere derlenen bir programda `wmain` bağımsız değişkenler ayrıştırılır ve joker karakterler geniş karakterli dizeler olarak genişletilir ve bağımsız değişken dizesi dizisine bir işaretçi atanır `__wargv` .

Taşınabilir kod için, `main` programınızda komut satırı bağımsız değişkenlerini almak için geçirilen bağımsız değişkenleri kullanmanızı öneririz.

### <a name="generic-text-routine-mappings"></a>Genel metin rutin eşlemeleri

|Tchar.h yordamı|_UNICODE tanımsız|_UNICODE tanımlanmış|
|---------------------|---------------------------|-----------------------|
|`__targv`|`__argv`|`__wargv`|

## <a name="requirements"></a>Gereksinimler

|Genel değişken|Gerekli başlık|
|---------------------|---------------------|
|`__argc`, `__argv`, `__wargv`|\<stdlib.h>, \<cstdlib> (C++)|

`__argc`, `__argv` ve, `__wargv` Microsoft uzantılarıdır. Uyumluluk bilgileri için bkz. [Uyumluluk](../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Genel değişkenler](../c-runtime-library/global-variables.md)\
[main işlev ve komut satırı bağımsız değişkenleri (C++)](../cpp/main-function-command-line-args.md)\
[wmainYerine kullanmamain](../cpp/main-function-command-line-args.md)
