---
title: Sinyal eylemi sabitleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- SIG_IGN
- SIG_DFL
dev_langs:
- C++
helpviewer_keywords:
- signal action constants
- SIG_IGN constant
- SIG_DFL constant
ms.assetid: c3cb4f15-d39e-4d9d-84f9-0d33e3eb5993
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6b6f645d474e697bf662a5dd63973dd54c329eb9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32409442"
---
# <a name="signal-action-constants"></a>sinyal Eylemi Sabitleri
Gerçekleştirilecek eylemi kesme sinyal alındığında değerine bağlıdır `func`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#include <signal.h>  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `func` Bağımsız değişkeni bir işlev adresi ya da aşağıda listelenen ve SİNYALİN tanımlanmış bildirim sabitleri biri olmalıdır. H.  
  
 `SIG_DFL`  
 Sistem varsayılan yanıt kullanır. Akış g/ç çağıran program kullanıyorsa, çalışma zamanı kitaplığı tarafından oluşturulan arabellekleri atılmış değil.  
  
 `SIG_IGN`  
 Kesme sinyali yok sayar. Bu değer için hiçbir zaman verilmelidir `SIGFPE`, kayan nokta işleminin durumunu sol beri tanımlanmamış.  
  
 `SIG_SGE`  
 Bir hata oluştu sinyalinin gösterir.  
  
 `SIG_ACK`  
 Bir bildirim alındı gösterir.  
  
 `SIG_ERR`  
 Hata belirten bir sinyal dönüş türünden oluştu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sinyal](../c-runtime-library/reference/signal.md)   
 [Global Sabitler](../c-runtime-library/global-constants.md)