---
title: srand | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: srand
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords: srand
dev_langs: C++
helpviewer_keywords:
- random starting point
- random starting point, setting
- random numbers, generating
- srand function
- numbers, pseudorandom
- numbers, random
- pseudorandom numbers
- starting points, setting random
- starting points
ms.assetid: 7bf56dc5-5692-4182-a3c1-18af98d2dd1a
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 99847da3be2e311ac9cb0da301ed4729705ad9fb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="srand"></a>srand
Sözde rastgele sayı üretici için başlangıç çekirdek değerini ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void srand(  
   unsigned int seed   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `seed`  
 Sözde rastgele sayı üretimi için çekirdek  
  
## <a name="remarks"></a>Açıklamalar  
 `srand` işlevi, geçerli iş parçacığında bir sözde rastgele tamsayı dizisi oluşturmak için başlangıç noktasını ayarlar. Üreticiyi, aynı sonuç dizisini oluşturmak amacıyla yeniden başlatmak için, `srand` işlevini çağırın ve aynı `seed` bağımsız değişkeni yeniden kullanın. `seed` için herhangi başka bir değer, üreticiyi, sözde rastgele dizi içinde farklı bir başlatma noktasına ayarlar. `rand`, oluşturulan sözde rastgele sayıları alır. `rand`, herhangi bir `srand` çağrısından önce çağrıldığında, `srand`'ın `seed` ile çağrılmasının 1 olarak geçmesiyle aynı dizi üretilir.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`srand`|\<stdlib.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [rand](../../c-runtime-library/reference/rand.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)   
 [rand](../../c-runtime-library/reference/rand.md)