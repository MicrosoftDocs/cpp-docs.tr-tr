---
title: _ismbbpunct, _ismbbpunct_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _ismbbpunct
- _ismbbpunct_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- ismbbpunct
- ismbbpunct_l
- _ismbbpunct_l
- _ismbbpunct
dev_langs:
- C++
helpviewer_keywords:
- ismbbpunct function
- _ismbbpunct function
- ismbbpunct_l function
- _ismbbpunct_l function
ms.assetid: 1976c9d3-7d1a-415f-ac52-2715c7bb56eb
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cd6e7eb83752a8848ba6ff0ffb39309cd01e8679
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="ismbbpunct-ismbbpunctl"></a>_ismbbpunct, _ismbbpunct_l
Belirli bir karakterin bir noktalama karakteri olup olmadığını belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _ismbbpunct(  
   unsigned int c   
);  
int _ismbbpunct_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `c`  
 Sınanacak tamsayı.  
  
 `locale`  
 Kullanılacak yerel ayar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `_ismbbpunct` sıfır olmayan bir değer döndürür tamsayı `c` ASCII olmayan noktalama simgesi. `_ismbbpunct` Geçerli yerel ayar için herhangi bir yerel ayara bağımlı karakter ayarı kullanır. `_ismbbpunct_l` geçirilen yerel kullanır ancak bu aynıdır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_ismbbpunct`|\<Mbctype.h >|  
|`_ismbbpunct_l`|\<Mbctype.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bayt sınıflandırması](../../c-runtime-library/byte-classification.md)   
 [_ismbb Yordamları](../../c-runtime-library/ismbb-routines.md)