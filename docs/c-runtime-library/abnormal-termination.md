---
title: _abnormal_termination | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _abnormal_termination
apilocation:
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr120.dll
- msvcrt.dll
- msvcr80.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- _abnormal_termination
dev_langs:
- C++
helpviewer_keywords:
- _abnormal_termination
ms.assetid: 952970a4-9586-4c3d-807a-db729448c91c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f70520b60ccfaf1af5b223bcb4ea1a90639aa484
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32385559"
---
# <a name="abnormaltermination"></a>_abnormal_termination
Gösterir olup olmadığını `__finally` , engelleme bir [try-finally deyimi](../cpp/try-finally-statement.md) sistem sonlandırma işleyicileri iç listesine yürütülürken girilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
int   _abnormal_termination(  
   );  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 `true` Sistem ise *unwinding* yığın; Aksi halde, `false`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu unwinding özel durumları yönetmek için kullanılan bir iç işlevidir ve kullanıcı kodundan çağrılmak üzere tasarlanmamıştır.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|_abnormal_termination|excpt.h|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [try-finally Deyimi](../cpp/try-finally-statement.md)