---
title: _CxxThrowException | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _CxxThrowException
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
- CxxThrowException
- _CxxThrowException
dev_langs: C++
helpviewer_keywords:
- _CxxThrowException function
- CxxThrowException function
ms.assetid: 0b90bef5-b7d2-46e0-88e2-59e531e01a4d
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d1c66f35a61a1b3f8577ac7a1432423906f091ab
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cxxthrowexception"></a>_CxxThrowException
Özel durum kaydı oluşturur ve özel durum işleme başlayabilmesi için çalışma zamanı ortamı çağırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
extern "C" void __stdcall _CxxThrowException(  
   void* pExceptionObject  
   _ThrowInfo* pThrowInfo  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in]`pExceptionObject`  
 Özel durum oluşturdu nesne.  
  
 [in]`pThrowInfo`  
 Özel durum işlemek için gereken bilgiler.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem derleyici özel durumları işlemek için kullandığı bir salt derleyici dosyasına dahil edilir. Doğrudan kodunuzdan yöntemi çağırmanız gerekmez.  
  
## <a name="requirements"></a>Gereksinimler  
 **Kaynak:** Throw.cpp  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Alfabetik İşlev Başvurusu](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)