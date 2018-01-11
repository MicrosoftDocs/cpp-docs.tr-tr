---
title: __max | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: __max
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
- max
- __max
dev_langs: C++
helpviewer_keywords:
- max macro
- maximum macro
- __max macro
ms.assetid: 05c936f6-0e22-45d6-a58d-4bc102e9dae2
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 585d2a295bedb8b0ba49a893d5089bc682a1debd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="max"></a>__max
İki değerden daha büyük döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
type __max(  
   type a,  
   type b   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `type`  
 Herhangi bir sayısal veri türü.  
  
 `a, b`  
 Karşılaştırılacak herhangi bir sayısal tür değerleri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `__max`bağımsız değişkenlerini daha büyük döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 `__max` Makrosu iki değeri karşılaştırır ve daha büyük bir değer döndürür. Bağımsız değişken veri türü, imzalı veya imzasız herhangi sayı olabilir. Bağımsız değişkenleri ve dönüş değeri aynı veri türünde olmalıdır.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`__max`|\<stdlib.h >|  
  
## <a name="example"></a>Örnek  
 Daha fazla bilgi için örneğin bkz [__min](../../c-runtime-library/reference/min.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)   
 [__min](../../c-runtime-library/reference/min.md)