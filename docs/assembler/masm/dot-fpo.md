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
ms.openlocfilehash: 234ec5bd703a390d1e2ee60e48d99d346d4aad95
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43203119"
---
# <a name="fpo"></a>.FPO
. FPO yönergesi, hata ayıklama kayıtlarını .debug$ F segment veya bölüm yayımlanmasını denetler.  
  
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
 Yerel değişkenler, bir işaretsiz 32 bit değeri sayısı.  
  
 `cdwParams`  
 DWORD, işaretsiz 16 bit değeri parametrelerinde boyutu.  
  
 *cbProlog*  
 İmzalanmamış 8 bit bir değer işlev giriş kodunun bayt sayısı.  
  
 `cbRegs`  
 Kaydedilmiş Yazmaçlar numarası.  
  
 `fUseBP`  
 EBP kayıt ayrılmış olup olmadığını gösterir. 0 veya 1.  
  
 *cbFrame*  
 Çerçeve türünü gösterir.  Bkz: [FPO_DATA](/windows/desktop/api/winnt/ns-winnt-_fpo_data) daha fazla bilgi için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)