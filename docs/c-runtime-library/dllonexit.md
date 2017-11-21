---
title: __dllonexit | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: __dllonexit
apilocation:
- msvcrt.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr80.dll
- msvcr120.dll
- msvcr90.dll
- msvcr120_clr0400.dll
apitype: DLLExport
f1_keywords: __dllonexit
dev_langs: C++
helpviewer_keywords: __dllonexit
ms.assetid: 708f2ceb-f95c-46b0-a58d-d68b3fa36f12
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9e59acec12c90d101ef385c379c092c7034f1ed0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="dllonexit"></a>__dllonexit
Çıkış zaman çağrılacak bir yordam kaydeder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
_onexit_t __dllonexit(   _onexit_t func,  
   _PVFV **  pbegin,   
   _PVFV **  pend   
   )  
```  
  
#### <a name="parameters"></a>Parametreler  
 `func`  
 Çıkış yürütülmek üzere bir işlev işaretçisi.  
  
 `pbegin`  
 İşaretçi başlangıç noktalarına yürütmek işlevlerin listesi detach bir değişkene.  
  
 `pend`  
 İşaretçi bir listesinin sonuna noktalarına yürütmek işlevlerin detach değişkenine.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, kullanıcının işlev işaretçisi. Aksi takdirde NULL işaretçi.  
  
## <a name="remarks"></a>Açıklamalar  
 `__dllonexit` İşlevidir benzer [_onexit](../c-runtime-library/reference/onexit-onexit-m.md) bu işlev tarafından kullanılan genel değişkenler için bu yordamı görünür değildir ancak bu işlev. Global değişkenler yerine bu işlevi kullanan `pbegin` ve `pend` parametreleri.  
  
 `_onexit` Ve `atexit` DLL işlevlerini MSVCRT ile bağlantılı. LIB kendi atexit/_onexit listesi bulundurmanız gerekir. Bu tür DLL'leri tarafından çağrılır çalışan yordamdır.  
  
 `_PVFV` Türü olarak tanımlanmış `typedef void (__cdecl *_PVFV)(void)`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli dosya|  
|-------------|-------------------|  
|__dllonexit|OnExit.c|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_onexit, _onexit_m](../c-runtime-library/reference/onexit-onexit-m.md)