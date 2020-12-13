---
description: 'Hakkında daha fazla bilgi edinin: _except_handler3'
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
ms.openlocfilehash: c6253152559516ea7162f887618df0bcbb4bc8ac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331126"
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

Bir özel durum kapatıldıktan sonra, döndürür `DISPOSITION_DISMISS` . Özel durumun kapsülleme özel durum işleyicilerine bir düzey geçirilmesi gerekiyorsa, döndürür `DISPOSITION_CONTINUE_SEARCH` .

## <a name="remarks"></a>Açıklamalar

Bu yöntem uygun bir özel durum işleyicisi bulursa, özel durumu işleyiciye geçirir. Bu durumda, bu yöntem çağıran koda geri dönmez ve dönüş değeri ilgisiz olur.

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](../c-runtime-library/reference/crt-alphabetical-function-reference.md)
