---
title: _set_new_mode | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _set_new_mode
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
- set_new_mode
- _set_new_mode
dev_langs:
- C++
helpviewer_keywords:
- handler modes
- _set_new_mode function
- set_new_mode function
ms.assetid: 4d14039a-e54e-4689-8c70-74a4b9834768
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9b914e950fd94435768c355f327d3d48a653e0d5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32407151"
---
# <a name="setnewmode"></a>_set_new_mode

Yeni bir işleyici modu için ayarlar **malloc**.

## <a name="syntax"></a>Sözdizimi

```cpp
int _set_new_mode( int newhandlermode );
```

### <a name="parameters"></a>Parametreler

*newhandlermode*<br/>
Yeni işleyici modu için **malloc**; geçerli değer 0 veya 1'dir.

## <a name="return-value"></a>Dönüş Değeri

Mod kümesi için önceki işleyicisini döndürür **malloc**. 1 değeri, gösterir, bellek ayırma hatası dönüş **malloc** daha önce yeni işleyici yordamı; adlı dönüş değerinin 0, belirtmiyor olduğunu gösterir. Varsa *newhandlermode* bağımsız değişkeni 0 veya 1 eşit değil, -1 döndürür.

## <a name="remarks"></a>Açıklamalar

C++ **_set_new_mode** işlevi ayarlar için yeni işleyici modu [malloc](malloc.md). Yeni işleyici modunu gösterir, hatasında kullanılıp **malloc** belirlediği yeni işleyici yordamı çağırmaktır [_set_new_handler](set-new-handler.md). Varsayılan olarak, **malloc** yeni işleyici yordamı bellek ayırma hatası çağırmaz. Bu varsayılan davranışı geçersiz kılabilirsiniz böylece, **malloc** bellek ayırmak başarısız **malloc** yeni işleyici yordamını aynı çağırıyor biçimi **yeni** işleci mu aynı nedenden dolayı başarısız olduğunda. Daha fazla bilgi için bkz: [yeni](../../cpp/new-operator-cpp.md) ve [silmek](../../cpp/delete-operator-cpp.md) işleçleri *C++ dil başvurusu*. Varsayılan değer geçersiz kılmak için arayın:

```cpp
_set_new_mode(1);
```

program veya Newmode.obj bağlantısıyla erkenden (bkz [bağlantı seçenekleri](../../c-runtime-library/link-options.md)).

Bu işlev, parametre doğrular. Varsa *newhandlermode* 0 veya 1, işlev dışındaki çağırır geçersiz parametre işleyicisi olarak herhangi bir şey açıklanan [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa **_ *** set_new_mode** -1 döndürür ve ayarlar **errno** için **EINVAL**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_set_new_mode**|\<New.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Ayırma](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[free](free.md)<br/>
[realloc](realloc.md)<br/>
[_query_new_handler](query-new-handler.md)<br/>
[_query_new_mode](query-new-mode.md)<br/>
