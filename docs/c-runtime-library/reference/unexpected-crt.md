---
title: Beklenmeyen (CRT) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
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
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3fce88dd7b2fdb821fc015130d25e54701c3e467
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
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
