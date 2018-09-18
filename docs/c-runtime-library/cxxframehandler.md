---
title: __CxxFrameHandler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- __CxxFrameHandler
apilocation:
- msvcr110.dll
- msvcrt.dll
- msvcr80.dll
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- __CxxFrameHandler
dev_langs:
- C++
helpviewer_keywords:
- __CxxFrameHandler
ms.assetid: b79ac97f-425a-42ae-9b91-8beaef935333
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4a4141d932cfad78ca9c563334ebbe51f711153e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088728"
---
# <a name="cxxframehandler"></a>__CxxFrameHandler

İç CRT işlevi. Yapılandırılmış özel durum çerçeveler işlemek için CRT tarafından kullanılır.

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
Olası için geçirilen özel durum kaydını `catch` deyimleri.

*PRN*<br/>
Özel durumu işlemek için kullanılan yığın çerçevesi hakkında dinamik bilgi sağlar. Daha fazla bilgi için ehdata.h bakın.

*pContext*<br/>
Bağlamı. (Intel işlemci üzerinde kullanılmıyor.)

*pDC*<br/>
İşlev giriş ve yığın çerçevesi hakkında ek bilgi.

## <a name="return-value"></a>Dönüş Değeri

Aşağıdakilerden birini *filtre ifadesi* tarafından kullanılan değerleri [deneyin-except deyimi](../cpp/try-except-statement.md).

## <a name="remarks"></a>Açıklamalar

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|__CxxFrameHandler|excpt.h, ehdata.h|