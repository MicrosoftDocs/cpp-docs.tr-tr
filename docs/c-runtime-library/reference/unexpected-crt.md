---
title: Beklenmeyen (CRT) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- unexpected
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
apitype: DLLExport
f1_keywords:
- unexpected
dev_langs:
- C++
helpviewer_keywords:
- unexpected function
ms.assetid: 2f873763-15ad-4556-a924-dcf28f2b52b4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fd8dc51c41ebf938f59493cbd62fac3e0a491601
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="unexpected-crt"></a>beklenmeyen (CRT)

Çağrıları **sonlandırmak** veya kullanarak belirttiğiniz işlevi **set_unexpected**.

## <a name="syntax"></a>Sözdizimi

```C
void unexpected( void );
```

## <a name="remarks"></a>Açıklamalar

**Beklenmeyen** yordamı C++ özel durum işleme geçerli uygulamasıyla kullanılmaz. **Beklenmeyen** çağrıları **sonlandırmak** varsayılan olarak. Özel sonlandırma işlevi yazma ve arama bu varsayılan davranışı değiştirebilirsiniz **set_unexpected** işlevinizi bağımsız değişkeni olarak adı. **Beklenmeyen** bağımsız değişken olarak verilen son işlevi çağırır **set_unexpected**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**beklenmeyen**|\<EH.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme Rutinleri](../../c-runtime-library/exception-handling-routines.md)<br/>
[abort](abort.md)<br/>
[_set_se_translator](set-se-translator.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[Sonlandırma](terminate-crt.md)<br/>
