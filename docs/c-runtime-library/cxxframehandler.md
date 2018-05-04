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
ms.openlocfilehash: 53659b462f811bca79209dd141d90527401cbc95
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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
 `pExcept`  
 Olası geçirilen özel durum kaydı `catch` deyimleri.  
  
 `pRN`  
 Özel durumu işlemek için kullanılan yığın çerçevesi hakkında dinamik bilgi sağlar. Daha fazla bilgi için ehdata.h bakın.  
  
 `pContext`  
 Bağlamı. (Intel işlemcileri üzerinde kullanılmaz.)  
  
 `pDC`  
 İşlev giriş ve yığın çerçevesi hakkında ek bilgi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Aşağıdakilerden birini *filtre ifadesi* tarafından kullanılan değerleri [deneyin-except deyimi](../cpp/try-except-statement.md).  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|__CxxFrameHandler|excpt.h, ehdata.h|