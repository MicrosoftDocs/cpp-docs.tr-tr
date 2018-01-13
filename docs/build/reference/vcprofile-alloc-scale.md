---
title: VCPROFILE_ALLOC_SCALE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VCPROFILE_ALLOC_SCALE
dev_langs: C++
helpviewer_keywords: VCPROFILE_ALLOC_SCALE environment variable
ms.assetid: 5cb5ce27-f9b8-489b-b46c-d6e9bcab2d34
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b7b441f41106544633bd691c409fa04c989146f0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="vcprofileallocscale"></a>VCPROFILE_ALLOC_SCALE
Profil verileri tutmak için ayrılmış bellek miktarı değiştirin.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
VCPROFILE_ALLOC_SCALE=scale_value  
```  
  
#### <a name="parameters"></a>Parametreler  
 `scale_value`  
 Sınama senaryolarını çalıştırmak için istediğiniz bellek miktarı için ölçek değeri.  Varsayılan değer 1'dir.  
  
## <a name="remarks"></a>Açıklamalar  
 Nadir durumlarda olmayacaktır desteklemek için yeterli kullanılabilir bellek sınama senaryolarını çalıştırırken profil verilerini toplama.  Bu gibi durumlarda, bellek miktarını artırın `VCPROFILE_ALLOC_SCALE`.  
  
 Yeterli bellek yok gösteren testi sırasında bir hata iletisi alırsanız, daha büyük bir değer atadığınız `VCPROFILE_ALLOC_SCALE`, test bellek yetersiz hatasız tam çalıştırılana kadar.  
  
## <a name="example"></a>Örnek  
  
```  
set VCPROFILE_ALLOC_SCALE=2  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Profil Temelli İyileştirmeler için Ortam Değişkenleri](../../build/reference/environment-variables-for-profile-guided-optimizations.md)