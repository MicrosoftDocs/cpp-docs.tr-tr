---
title: _unlock | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _unlock
apilocation:
- msvcrt.dll
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr80.dll
- msvcr120.dll
- msvcr90.dll
- msvcr120_clr0400.dll
apitype: DLLExport
f1_keywords:
- unlock
- _unlock
dev_langs:
- C++
helpviewer_keywords:
- unlock function
- _unlock function
ms.assetid: 2eda2507-a134-4997-aa12-f2f8cb319e14
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fcc842ef134d5f61cf634debe9dd16449b48bbb8
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45724028"
---
# <a name="unlock"></a>_unlock
Çoklu iş parçacığı kilidi serbest bırakır.  
  
> [!IMPORTANT]
>  Bu işlev artık kullanılmıyor. Visual Studio 2015'te başlayarak, CRT içinde kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void __cdecl _unlock(  
   int locknum  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
*locknum*<br/>
[in] Serbest bırakmak için kilit tanımlayıcısı.  
  
## <a name="requirements"></a>Gereksinimler  
 **Kaynak:** mlock.c  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Alfabetik işlev başvurusu](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [_lock](../c-runtime-library/lock.md)