---
title: __argc, __argv, __wargv
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
ms.openlocfilehash: 59ab1f5ba52e6dc84d44e8cb5465cfa412d01895
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70940632"
---
# <a name="__argc-__argv-__wargv"></a>__argc, __argv, __wargv

`__argc` Genel değişken, programa geçirilen komut satırı bağımsız değişkenlerinin sayısının sayısıdır. `__argv`, program bağımsız değişkenlerini içeren bir dizi tek baytlık karakter veya çok baytlı karakter dizelerinin bir işaretçisidir ve `__wargv` program bağımsız değişkenlerini içeren geniş karakterli dizeler dizisinin bir işaretçisidir. Bu genel değişkenler, veya `main` `wmain`için bağımsız değişkenleri sağlar.

## <a name="syntax"></a>Sözdizimi

```
extern int __argc;
extern char ** __argv;
extern wchar_t ** __wargv;
```

## <a name="remarks"></a>Açıklamalar

`main`İşlevinikullanan bir programda `__argv`veprogramı başlatmak için kullanılan komut satırı kullanılarak program başlangıcında başlatılır. `__argc` Komut satırı bağımsız bağımsız değişkenlere ayrıştırılır ve joker karakterler genişletilir. Bağımsız değişkenlerin sayısı öğesine `__argc` atanır ve bağımsız değişken dizeleri yığına ayrılır ve bağımsız değişkenlerin dizisine bir işaretçi `__argv`atanır. Geniş karakter ve bir `wmain` işlev kullanmak üzere derlenen bir programda bağımsız değişkenler ayrıştırılır ve joker karakterler geniş karakterli dizeler olarak genişletilir ve bağımsız değişken dizesi dizisine bir işaretçi `__wargv`atanır.

Taşınabilir kod için, programınızda komut satırı bağımsız değişkenlerini almak `main` için geçirilen bağımsız değişkenleri kullanmanızı öneririz.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNıCODE tanımlı değil|_UNICODE tanımlanmış|
|---------------------|---------------------------|-----------------------|
|`__targv`|`__argv`|`__wargv`|

## <a name="requirements"></a>Gereksinimler

|Genel değişken|Gerekli başlık|
|---------------------|---------------------|
|`__argc`, `__argv`, `__wargv`|\<Stdlib. h >, \<cstdlib > (C++)|

`__argc`, `__argv` ve`__wargv` , Microsoft uzantılarıdır. Uyumluluk bilgileri için bkz. [Uyumluluk](../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Global Değişkenler](../c-runtime-library/global-variables.md)<br/>
[main: Program Başlatma](../cpp/main-program-startup.md)<br/>
[main Yerine wmain Kullanma](../cpp/using-wmain-instead-of-main.md)
