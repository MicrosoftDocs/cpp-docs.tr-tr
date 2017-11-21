---
title: . FPO | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: .FPO
dev_langs: C++
helpviewer_keywords: .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: fc26358e1da11ada6b23364576bfedb379bc4030
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Yönergeler başvurusu](../../assembler/masm/directives-reference.md)