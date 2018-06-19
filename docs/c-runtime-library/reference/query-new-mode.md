---
title: _query_new_mode | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- query_new_mode function
- handler modes
- _query_new_mode function
ms.assetid: e185c5f9-b73b-4257-8eff-b47648374768
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8907b043e8b4441d6e5213a1d386dbc1a5a6910a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32405724"
---
# <a name="querynewmode"></a>_query_new_mode

Tarafından belirlenen yeni işleyici modu belirten bir tamsayı döndürür **_set_new_mode** için **malloc**.

## <a name="syntax"></a>Sözdizimi

```C
int _query_new_mode(
   void
);
```

## <a name="return-value"></a>Dönüş Değeri

Geçerli yeni işleyici modu, 0 veya 1 döndürür **malloc**. 1 değeri, gösterir, bellek ayırma hatası dönüş **malloc** yeni işleyici yordamını; çağırıyor dönüş değerinin 0 yok olduğunu gösterir.

## <a name="remarks"></a>Açıklamalar

C++ **_query_new_mode** işlevi C++ tarafından ayarlanır yeni işleyici modu belirten bir tamsayı döndürür [_set_new_mode](set-new-mode.md) için işlev [malloc](malloc.md). Yeni işleyici modunu gösterir olup olmadığına göre bellek ayırma hatası **malloc** belirlediği yeni işleyici yordamı çağırmaktır [_set_new_handler](set-new-handler.md). Varsayılan olarak, **malloc** yeni işleyici yordamı hatada çağırmaz. Kullanabilirsiniz **_set_new_mode** bu nedenle bu davranışı geçersiz kılmak için hatasında **malloc** yeni işleyici yordamını aynı çağırıyor biçimi **yeni** işleci için başarısız olduğunda yapar bellek ayrılamadı. Açıklamalara daha fazla bilgi için bkz: [yeni ve delete işleçleri](../../cpp/new-and-delete-operators.md) C++ dil başvurusu.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_query_new_mode**|\<New.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Ayırma](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[free](free.md)<br/>
[realloc](realloc.md)<br/>
[_query_new_handler](query-new-handler.md)<br/>
