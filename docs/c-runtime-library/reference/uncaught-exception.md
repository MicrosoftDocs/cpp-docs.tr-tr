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
ms.workload: cplusplus
ms.openlocfilehash: 25d2e84bb6d336b2e530b833252b2b4a05dce4e0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [try, throw ve catch Deyimleri (C++)](../../cpp/try-throw-and-catch-statements-cpp.md)