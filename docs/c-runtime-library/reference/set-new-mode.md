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
ms.openlocfilehash: 78e3d346bca087a6fd855e6428e6a53779cd7355
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43202522"
---
# <a name="setnewmode"></a>_set_new_mode

İçin yeni bir işleyici modunu ayarlar **malloc**.

## <a name="syntax"></a>Sözdizimi

```cpp
int _set_new_mode( int newhandlermode );
```

### <a name="parameters"></a>Parametreler

*newhandlermode*<br/>
İçin yeni işleyici modunu **malloc**; geçerli değer 0 veya 1'dir.

## <a name="return-value"></a>Dönüş Değeri

Önceki işleyici modu kümesi için döndürür **malloc**. Dönüş değeri 1 gösterir, bellek dağıtma hatasında **malloc** yeni işleyici rutinini; önceki adı olduğu değil, 0 değeri belirtir. Varsa *newhandlermode* bağımsız değişkeni 0 veya 1 eşit değildir, -1 döndürür.

## <a name="remarks"></a>Açıklamalar

C++ **_set_new_mode** işlevi için yeni işleyici modunu ayarlar [malloc](malloc.md). Yeni işleyici modunu gösterir mi, hata durumunda, **malloc** tarafından belirlenen yeni işleyici rutinini çağırmaktır [_set_new_handler](set-new-handler.md). Varsayılan olarak, **malloc** bellek dağıtma hatasında yeni işleyici rutinini çağırmaz. Bu varsayılan davranışı geçersiz kılabilirsiniz böylece, **malloc** bellek ayırmak başarısız **malloc** aynı yeni işleyici rutinini çağırır biçimi **yeni** işleci yok aynı nedenden dolayı başarısız olduğunda. Daha fazla bilgi için [yeni](../../cpp/new-operator-cpp.md) ve [Sil](../../cpp/delete-operator-cpp.md) işleçleri *C++ dil başvurusu*. Varsayılan geçersiz kılmak için çağırın:

```cpp
_set_new_mode(1);
```

program ya da Newmode.obj ile erken (bkz [bağlantı seçenekleri](../../c-runtime-library/link-options.md)).

Bu işlev, parametresini doğrular. Varsa *newhandlermode* 0 veya 1 ise, işlev dışındaki çağırır, geçersiz parametre işleyicisi olarak herhangi bir şey açıklanan [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse <strong>_set_new_mode</strong> -1 döndürür ve ayarlar **errno** için `EINVAL`.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_set_new_mode**|\<New.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Ayırma](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[free](free.md)<br/>
[realloc](realloc.md)<br/>
[_query_new_handler](query-new-handler.md)<br/>
[_query_new_mode](query-new-mode.md)<br/>
