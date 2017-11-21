---
title: __uncaught_exception | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: __uncaught_exception
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
f1_keywords: __uncaught_exception
dev_langs: C++
helpviewer_keywords: __uncaught_exception
ms.assetid: 4d9b75c6-c9c7-4876-b761-ea9ab1925e96
caps.latest.revision: "2"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2b43a6b08087dcaeeda7959eaadbee9c250f4de9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="uncaughtexception"></a>__uncaught_exception
Bir veya daha fazla özel durum, ancak henüz karşılık gelen tarafından işlenmemiş olup olmadığını gösterir `catch` , engelleme bir [try-catch](../../cpp/try-throw-and-catch-statements-cpp.md) deyimi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
bool __uncaught_exception(  
   );  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 `true`saati özel durum oluşur bir `try` eşleştirme kadar blok `catch` blok başlatılmış; Aksi takdirde `false`.  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|__uncaught_exception|EH.h|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [deneyin, throw ve catch deyimleri (C++)](../../cpp/try-throw-and-catch-statements-cpp.md)