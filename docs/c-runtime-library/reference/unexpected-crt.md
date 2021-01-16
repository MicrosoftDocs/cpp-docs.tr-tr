---
description: 'Hakkında daha fazla bilgi edinin: beklenmeyen (CRT)'
title: beklenmeyen (CRT)
ms.date: 1/14/2021
api_name:
- unexpected
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- unexpected
helpviewer_keywords:
- unexpected function
ms.assetid: 2f873763-15ad-4556-a924-dcf28f2b52b4
ms.openlocfilehash: 098d686e7c33d17020990b1db168d95c327d5112
ms.sourcegitcommit: 1cd8f8a75fd036ffa57bc70f3ca869042d8019d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2021
ms.locfileid: "98242910"
---
# <a name="unexpected-crt"></a>`unexpected` CRT

**`terminate`** Kullanarak belirttiğiniz veya çağıran işlev **`set_unexpected`** .

## <a name="syntax"></a>Syntax

```C
void unexpected( void );
```

## <a name="remarks"></a>Açıklamalar

**`unexpected`** Yordam, C++ özel durum işlemenin geçerli uygulamasıyla kullanılmaz. **`unexpected`****`terminate`** Varsayılan olarak çağırır. Bu varsayılan davranışı, özel bir sonlandırma işlevi yazarak değiştirebilirsiniz. **`set_unexpected`** İşlevinizin adını bağımsız değişkeni olarak çağırın. **`unexpected`** geçirilen son işlevi çağırır **`set_unexpected`** .

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**`unexpected`**|`<eh.h>`|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Özel durum Işleme yordamları](../../c-runtime-library/exception-handling-routines.md)<br/>
[durdur](abort.md)<br/>
[_set_se_translator](set-se-translator.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[sonlandırmayı](terminate-crt.md)<br/>
