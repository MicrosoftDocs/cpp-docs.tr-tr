---
title: _CxxThrowException | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _CxxThrowException
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
dev_langs:
- C++
helpviewer_keywords:
- _CxxThrowException function
- CxxThrowException function
ms.assetid: 0b90bef5-b7d2-46e0-88e2-59e531e01a4d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fb59e3e81a9e92d3a692e91c9c25a92fd09603cd
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
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
 [in] `pExceptionObject`  
 Özel durum oluşturdu nesne.  
  
 [in] `pThrowInfo`  
 Özel durum işlemek için gereken bilgiler.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem derleyici özel durumları işlemek için kullandığı bir salt derleyici dosyasına dahil edilir. Doğrudan kodunuzdan yöntemi çağırmanız gerekmez.  
  
## <a name="requirements"></a>Gereksinimler  
 **Kaynak:** Throw.cpp  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Alfabetik İşlev Başvurusu](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)