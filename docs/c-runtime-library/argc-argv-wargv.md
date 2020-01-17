---
title: __argc, __argv, __wargv
description: Microsoft C çalışma zamanı kitaplığı genel sabitlerini __argc, __argvve __wargvaçıklar.
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
ms.openlocfilehash: 86a22a7391c7bde34d7734631a2970a45851dda3
ms.sourcegitcommit: e93f3e6a110fe38bc642055bdf4785e620d4220f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/16/2020
ms.locfileid: "76123987"
---
# <a name="opno-loc__argc-opno-loc__argv-opno-loc__wargv"></a>__argc, __argv, __wargv

`__argc` genel değişkeni, programa geçirilen komut satırı bağımsız değişkenlerinin sayısının sayısıdır. `__argv`, program bağımsız değişkenlerini içeren tek baytlık karakter veya çok baytlı karakter dizeleri dizisinin bir işaretçisidir ve `__wargv` program bağımsız değişkenlerini içeren geniş karakterli dizeler dizisinin bir işaretçisidir. Bu genel değişkenler `main` veya `wmain`bağımsız değişkenlerini sağlar.

## <a name="syntax"></a>Sözdizimi

```C
extern int __argc;
extern char ** __argv;
extern wchar_t ** __wargv;
```

## <a name="remarks"></a>Açıklamalar

`main` işlevi kullanan bir programda, `__argc` ve `__argv` programı başlatmak için kullanılan komut satırı kullanılarak program başlangıcında başlatılır. Komut satırı bağımsız bağımsız değişkenlere ayrıştırılır ve joker karakterler genişletilir. Bağımsız değişkenlerin sayısı `__argc` atanır ve bağımsız değişken dizeleri yığına ayrılır ve bağımsız değişken dizisine yönelik bir işaretçi `__argv`atanır. Geniş karakter ve `wmain` işlevi kullanacak şekilde derlenen bir programda, bağımsız değişkenler ayrıştırılır ve joker karakterler geniş karakterli dizeler olarak genişletilir ve bağımsız değişken dizesi dizisine bir işaretçi `__wargv`atanır.

Taşınabilir kod için, programınızdaki komut satırı bağımsız değişkenlerini almak üzere `main` geçirilen bağımsız değişkenleri kullanmanızı öneririz.

### <a name="generic-text-routine-mappings"></a>Genel metin rutin eşlemeleri

|Tchar.h yordamı|_UNICODE tanımsız|_UNICODE tanımlanmış|
|---------------------|---------------------------|-----------------------|
|`__targv`|`__argv`|`__wargv`|

## <a name="requirements"></a>Gereksinimler

|Genel değişken|Gerekli başlık|
|---------------------|---------------------|
|`__argc`, `__argv`, `__wargv`|\<Stdlib. h >, \<cstdlib > (C++)|

`__argc`, `__argv`ve `__wargv` Microsoft uzantılarıdır. Uyumluluk bilgileri için bkz. [Uyumluluk](../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Genel değişkenler](../c-runtime-library/global-variables.md)\
[main işlevi ve komut satırı bağımsız değişkenleri (C++)](../cpp/main-function-command-line-args.md)\
[main yerine wmain kullanma](../cpp/using-wmain-instead-of-main.md)
