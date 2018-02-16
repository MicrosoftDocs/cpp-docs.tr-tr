---
title: towctrans | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- towctrans
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
f1_keywords:
- towctrans
dev_langs:
- C++
helpviewer_keywords:
- towctrans function
ms.assetid: 1ed1e70d-7b31-490f-a7d9-42564b5924ca
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 79bd4c48b5462d0d7b3cc7145a3044da80869af1
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
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
 [Veri Dönüştürme](../../c-runtime-library/data-conversion.md)