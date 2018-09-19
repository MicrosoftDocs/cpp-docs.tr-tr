---
title: _except_handler3 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _except_handler3
apilocation:
- msvcrt.dll
- msvcr90.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr100.dll
- msvcr110.dll
apitype: DLLExport
f1_keywords:
- _except_handler3
- except_handler3
dev_langs:
- C++
helpviewer_keywords:
- _except_handler3 function
- except_handler3 function
ms.assetid: b0c64898-0ae5-48b7-9724-80135a0813e2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b1b93cf52ee7690aa86f4a80acae2731197ec9d9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46115378"
---
# <a name="excepthandler3"></a>_except_handler3

İç CRT işlevi. Geçerli özel durumu işlemek için uygun özel durum işleyicisi bulmak için framework tarafından kullanılır.

## <a name="syntax"></a>Sözdizimi

```
int _except_handler3(
   PEXCEPTION_RECORD exception_record,
   PEXCEPTION_REGISTRATION registration,
   PCONTEXT context,
   PEXCEPTION_REGISTRATION dispatcher
);
```

#### <a name="parameters"></a>Parametreler

*exceptıon_record*<br/>
[in] Özel durum hakkında bilgi sağlar.

*Kayıt*<br/>
[in] Özel durum işleyicisi bulmak için kapsam tablo belirten kayıt kullanılmalıdır.

*Bağlam*<br/>
[in] Ayrılmış.

*Dağıtıcı*<br/>
[in] Ayrılmış.

## <a name="return-value"></a>Dönüş Değeri

Bir özel durum oluşturmayabilir, döndürür `DISPOSITION_DISMISS`. Özel durum bir düzey yukarı kapsülleyerek özel durum işleyicilerine geçirilmelidir döndürür `DISPOSITION_CONTINUE_SEARCH`.

## <a name="remarks"></a>Açıklamalar

Bu yöntemin uygun özel durum işleyicisi bulunursa, özel durum işleyicisine geçirir. Bu durumda, bu yöntemi çağıran koda döndürmüyor ve dönüş değeri önemli değildir.

## <a name="see-also"></a>Ayrıca Bkz.

[Alfabetik İşlev Başvurusu](../c-runtime-library/reference/crt-alphabetical-function-reference.md)