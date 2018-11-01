---
title: _query_new_mode
ms.date: 11/04/2016
apiname:
- _query_new_mode
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- query_new_mode
- _query_new_mode
helpviewer_keywords:
- query_new_mode function
- handler modes
- _query_new_mode function
ms.assetid: e185c5f9-b73b-4257-8eff-b47648374768
ms.openlocfilehash: 327f22c847793316bd126721b4a66846d7da84dd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50620031"
---
# <a name="querynewmode"></a>_query_new_mode

Belirlenen yeni işleyici modu belirten bir tamsayı döndürür **_set_new_mode** için **malloc**.

## <a name="syntax"></a>Sözdizimi

```C
int _query_new_mode(
   void
);
```

## <a name="return-value"></a>Dönüş Değeri

İçin geçerli yeni işleyici modu, 0 veya 1 döndürür **malloc**. Dönüş değeri 1 gösterir, bellek dağıtma hatasında **malloc** ; yeni işleyici rutinini çağırır 0 dönüş değeri yok olduğunu gösterir.

## <a name="remarks"></a>Açıklamalar

C++ **_query_new_mode** işlevi C++ tarafından ayarlanmış olan yeni işleyici modu belirten bir tamsayı döndürür [_set_new_mode](set-new-mode.md) için işlev [malloc](malloc.md). Yeni işleyici modu belirtir olup olmadığına göre bellek ayırma hatası **malloc** tarafından belirlenen yeni işleyici rutinini çağırmaktır [_set_new_handler](set-new-handler.md). Varsayılan olarak, **malloc** hatasında yeni işleyici rutinini çağırmaz. Kullanabileceğiniz **_set_new_mode** bu nedenle bu davranışı geçersiz kılmak için hata durumunda **malloc** aynı yeni işleyici rutinini çağırır biçimi **yeni** işlecinin yaptığı için başarısız olduğunda bellek ayrılamadı. Daha fazla bilgi için bkz [yeni ve delete işleçleri](../../cpp/new-and-delete-operators.md) C++ dil başvurusu.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_query_new_mode**|\<New.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Ayırma](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[free](free.md)<br/>
[realloc](realloc.md)<br/>
[_query_new_handler](query-new-handler.md)<br/>
