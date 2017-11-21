---
title: towctrans | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: towctrans
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords: towctrans
dev_langs: C++
helpviewer_keywords: towctrans function
ms.assetid: 1ed1e70d-7b31-490f-a7d9-42564b5924ca
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: fcd97b3af0bb7e469db18b1a7ff8290af5df1bc4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="towctrans"></a>towctrans
Bir karakter dönüştürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
wint_t towctrans(  
   wint_t c,  
   wctrans_t category   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `c`  
 Dönüştürmek istediğiniz karakter.  
  
 `category`  
 Dönüş değerini içeren bir tanımlayıcı [wctrans](../../c-runtime-library/reference/wctrans.md).  
  
## <a name="return-value"></a>Dönüş Değeri  
 Karakter `c`, sonra `towctrans` dönüştürme kuralda kullanılan `category`.  
  
## <a name="remarks"></a>Açıklamalar  
 Değeri `category` başarılı bir önceki çağrısı tarafından Döndürülmüş gerekir [wctrans](../../c-runtime-library/reference/wctrans.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`towctrans`|\<wctype.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
 Bkz: `wctrans` kullanan bir örnek için `towctrans`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri dönüştürme](../../c-runtime-library/data-conversion.md)