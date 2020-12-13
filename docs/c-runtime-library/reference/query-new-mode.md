---
description: 'Hakkında daha fazla bilgi edinin: _query_new_mode'
title: _query_new_mode
ms.date: 11/04/2016
api_name:
- _query_new_mode
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
- api-ms-win-crt-heap-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- query_new_mode
- _query_new_mode
helpviewer_keywords:
- query_new_mode function
- handler modes
- _query_new_mode function
ms.assetid: e185c5f9-b73b-4257-8eff-b47648374768
ms.openlocfilehash: 90c7355f4babc4726c8b52d61309eb1ceb23c9a3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137143"
---
# <a name="_query_new_mode"></a>_query_new_mode

**Malloc** için **_set_new_mode** tarafından ayarlanan yeni işleyici modunu gösteren bir tamsayı döndürür.

## <a name="syntax"></a>Syntax

```C
int _query_new_mode(
   void
);
```

## <a name="return-value"></a>Dönüş Değeri

**Malloc** için 0 veya 1 gibi geçerli yeni işleyici modunu döndürür. 1 dönüş değeri, bellek ayıramadığında, **malloc** 'in yeni işleyici yordamını çağırdığı anlamına gelir; 0 dönüş değeri olmadığını gösterir.

## <a name="remarks"></a>Açıklamalar

C++ **_query_new_mode** işlevi, [malloc](malloc.md)için c++ [_set_new_mode](set-new-mode.md) işlevi tarafından ayarlanan yeni işleyici modunu gösteren bir tamsayı döndürür. Yeni işleyici modu, bellek ayırmayı başarısızlığından, **malloc** 'in [_set_new_handler](set-new-handler.md)tarafından ayarlanan yeni işleyici yordamını çağırmaya yönelik olup olmadığını gösterir. Varsayılan olarak, **malloc** hata durumunda yeni işleyici yordamını çağırmaz. Bu davranışı geçersiz kılmak için **_set_new_mode** kullanabilirsiniz, böylece hata **malloc** , yeni işleyici yordamını, **`new`** bellek ayıramadığında işlecin yaptığı şekilde çağırır. Daha fazla bilgi için bkz. C++ dil başvurusunda [yeni ve delete işleçleri](../../cpp/new-and-delete-operators.md) tartışması.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_query_new_mode**|\<new.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="see-also"></a>Ayrıca bkz.

[Bellek ayırma](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[Süz](free.md)<br/>
[realloc](realloc.md)<br/>
[_query_new_handler](query-new-handler.md)<br/>
