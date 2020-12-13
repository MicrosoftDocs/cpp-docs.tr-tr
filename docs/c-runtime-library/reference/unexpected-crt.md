---
description: 'Hakkında daha fazla bilgi edinin: beklenmeyen (CRT)'
title: beklenmeyen (CRT)
ms.date: 11/04/2016
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- unexpected
helpviewer_keywords:
- unexpected function
ms.assetid: 2f873763-15ad-4556-a924-dcf28f2b52b4
ms.openlocfilehash: 73c632c4dd5bfedbb1c3724e60786b348f77f0be
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186642"
---
# <a name="unexpected-crt"></a>beklenmeyen (CRT)

**Set_unexpected** kullanarak belirttiğiniz **sonlandırma** veya işlevi çağırır.

## <a name="syntax"></a>Syntax

```C
void unexpected( void );
```

## <a name="remarks"></a>Açıklamalar

**Beklenmeyen** yordam, C++ özel durum işlemenin geçerli uygulamasıyla kullanılmaz. **beklenmeyen** çağrılar varsayılan olarak **sonlandırılır** . Özel bir sonlandırma işlevi yazarak ve bağımsız değişkeni olarak işlevinizin adını **set_unexpected** çağırarak, bu varsayılan davranışı değiştirebilirsiniz. **beklenmeyen** bir bağımsız değişken olarak verilen son işlevi çağıran **set_unexpected**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**bek**|\<eh.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Özel durum Işleme yordamları](../../c-runtime-library/exception-handling-routines.md)<br/>
[durdur](abort.md)<br/>
[_set_se_translator](set-se-translator.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[sonlandırmayı](terminate-crt.md)<br/>
