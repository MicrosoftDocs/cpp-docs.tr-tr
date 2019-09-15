---
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
ms.openlocfilehash: 59724dafdc6488596478d0b44b254c4f498fce99
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70950110"
---
# <a name="_query_new_mode"></a>_query_new_mode

**Malloc**için **_set_new_mode** tarafından ayarlanan yeni işleyici modunu gösteren bir tamsayı döndürür.

## <a name="syntax"></a>Sözdizimi

```C
int _query_new_mode(
   void
);
```

## <a name="return-value"></a>Dönüş Değeri

**Malloc**için 0 veya 1 gibi geçerli yeni işleyici modunu döndürür. 1 dönüş değeri, bellek ayıramadığında, **malloc** 'in yeni işleyici yordamını çağırdığı anlamına gelir; 0 dönüş değeri olmadığını gösterir.

## <a name="remarks"></a>Açıklamalar

C++ **_Query_new_mode** işlevi, C++ [malloc](malloc.md)için [_set_new_mode](set-new-mode.md) işlevi tarafından ayarlanan yeni işleyici modunu gösteren bir tamsayı döndürür. Yeni işleyici modu, bellek ayırmayı başarısızlığından, **malloc** 'in [_set_new_handler](set-new-handler.md)tarafından ayarlanan yeni işleyici yordamını çağırmaya yönelik olup olmadığını gösterir. Varsayılan olarak, **malloc** hata durumunda yeni işleyici yordamını çağırmaz. Bu davranışı geçersiz kılmak için **_set_new_mode** kullanabilirsiniz, böylece hata **malloc** , yeni işleyici yordamını, bellek ayıramadığında **Yeni** işlecin yaptığı şekilde çağırır. Daha fazla bilgi için, C++ dil başvurusundaki [New ve delete işleçleri](../../cpp/new-and-delete-operators.md) tartışmalarına bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_query_new_mode**|\<Yeni. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Ayırma](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[free](free.md)<br/>
[realloc](realloc.md)<br/>
[_query_new_handler](query-new-handler.md)<br/>
