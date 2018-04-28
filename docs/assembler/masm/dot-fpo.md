---
title: . FPO | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .FPO
dev_langs:
- C++
helpviewer_keywords:
- .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: df5185c0dc699764427989b2f46345d90ded1729
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
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