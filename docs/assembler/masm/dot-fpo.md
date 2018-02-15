---
title: . FPO | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- .FPO
dev_langs:
- C++
helpviewer_keywords:
- .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 76f3fb3d06e3d09cdd63e48ef2ab8a6ce95c81e6
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="fpo"></a>.FPO
. FPO yönergesi .debug$ F segment veya bölüm hata ayıklama kayıtlarını yayımlanmasını denetler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
FPO (  
cdwLocals  
,   
cdwParams  
,   
cbProlog  
,   
cbRegs  
,   
fUseBP  
,   
cbFrame  
)  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 `cdwLocals`  
 Yerel değişkenler, imzasız 32 bit değeri sayısı.  
  
 `cdwParams`  
 DWORD, imzasız 16 bit değeri parametrelerinde boyutu.  
  
 *cbProlog*  
 İmzasız 8 bit değeri işlevi giriş kodu bayt sayısı.  
  
 `cbRegs`  
 Kaydedilmiş kayıtları numara.  
  
 `fUseBP`  
 EBP kayıt ayrılmış olup olmadığını gösterir. 0 veya 1.  
  
 *cbFrame*  
 Çerçeve türünü gösterir.  Bkz: [FPO_DATA](http://msdn.microsoft.com/library/windows/desktop/ms679352) daha fazla bilgi için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)