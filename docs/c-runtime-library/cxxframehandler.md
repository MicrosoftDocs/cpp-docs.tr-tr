---
description: 'Hakkında daha fazla bilgi edinin: __CxxFrameHandler'
title: __CxxFrameHandler
ms.date: 11/04/2016
api_name:
- __CxxFrameHandler
api_location:
- msvcr110.dll
- msvcrt.dll
- msvcr80.dll
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr120.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __CxxFrameHandler
helpviewer_keywords:
- __CxxFrameHandler
ms.assetid: b79ac97f-425a-42ae-9b91-8beaef935333
ms.openlocfilehash: 3ebd4cefb303661b4b0293f3b4b3d42a915ddd56
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326369"
---
# <a name="__cxxframehandler"></a>__CxxFrameHandler

İç CRT işlevi. Yapılandırılmış özel durum çerçevelerini işlemek için CRT tarafından kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
EXCEPTION_DISPOSITION __CxxFrameHandler(
      EHExceptionRecord  *pExcept,
      EHRegistrationNode *pRN,
      void               *pContext,
      DispatcherContext  *pDC
   )
```

#### <a name="parameters"></a>Parametreler

*pExcept*<br/>
Olası deyimlere geçirilen özel durum kaydı **`catch`** .

*pRN*<br/>
Özel durumu işlemek için kullanılan yığın çerçevesiyle ilgili dinamik bilgiler. Daha fazla bilgi için bkz. ehdata. h.

*pContext*<br/>
Bağlam. (Intel işlemcilerde kullanılmaz.)

*Kökündeki*<br/>
İşlev girişi ve yığın çerçevesi hakkında ek bilgiler.

## <a name="return-value"></a>Dönüş Değeri

[Try-except deyimi](../cpp/try-except-statement.md)tarafından kullanılan *filtre ifadesi* değerlerinden biri.

## <a name="remarks"></a>Açıklamalar

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|__CxxFrameHandler|excpt. h, ehdata. h|
