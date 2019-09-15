---
title: _except_handler3
ms.date: 11/04/2016
api_name:
- _except_handler3
api_location:
- msvcrt.dll
- msvcr90.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr100.dll
- msvcr110.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _except_handler3
- except_handler3
helpviewer_keywords:
- _except_handler3 function
- except_handler3 function
ms.assetid: b0c64898-0ae5-48b7-9724-80135a0813e2
ms.openlocfilehash: 5e1dbab97e0f193d4ff59c19229d2c00e2cd7d6a
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70944477"
---
# <a name="_except_handler3"></a>_except_handler3

İç CRT işlevi. Geçerli özel durumu işlemek için uygun özel durum işleyicisini bulmak için bir Framework tarafından kullanılır.

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

*exception_record*<br/>
'ndaki Özel durum hakkında bilgi.

*kaydını*<br/>
'ndaki Özel durum işleyicisini bulmak için hangi kapsam tablosunun kullanılması gerektiğini belirten kayıt.

*bağlam*<br/>
'ndaki Ayrılamadı.

*Dağıtıcı*<br/>
'ndaki Ayrılamadı.

## <a name="return-value"></a>Dönüş Değeri

Bir özel durum kapatıldıktan sonra, döndürür `DISPOSITION_DISMISS`. Özel durumun kapsülleme özel durum işleyicilerine bir düzey geçirilmesi gerekiyorsa, döndürür `DISPOSITION_CONTINUE_SEARCH`.

## <a name="remarks"></a>Açıklamalar

Bu yöntem uygun bir özel durum işleyicisi bulursa, özel durumu işleyiciye geçirir. Bu durumda, bu yöntem çağıran koda geri dönmez ve dönüş değeri ilgisiz olur.

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](../c-runtime-library/reference/crt-alphabetical-function-reference.md)
