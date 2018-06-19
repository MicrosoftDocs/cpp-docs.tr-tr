---
title: __dllonexit | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- __dllonexit
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
f1_keywords:
- __dllonexit
dev_langs:
- C++
helpviewer_keywords:
- __dllonexit
ms.assetid: 708f2ceb-f95c-46b0-a58d-d68b3fa36f12
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1c0105ccc5a40c4e5fe789814adfabe6c9749650
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2018
ms.locfileid: "34450725"
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
 Başarılı olursa, kullanıcının işlev işaretçisi. Aksi halde, bir **NULL** işaretçi.  
  
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