---
title: VCPROFILE_PATH | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VCPROFILE_PATH
dev_langs: C++
helpviewer_keywords: VCPROFILE_PATH environment variable
ms.assetid: 25217aa4-7e86-4eba-854d-10b3c457e4df
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d5b4a2bbb46e906883f3f0c99c84d3b12cc0f104
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="vcprofilepath"></a>VCPROFILE_PATH
.PGC dosyaları oluşturmak için bir dizini belirtin.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
VCPROFILE_PATH=path  
```  
  
#### <a name="parameters"></a>Parametreler  
 `path`  
 Dizin yolu hangi .pgc dosyaları eklenir.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, .pgc dosyaları profili oluşturuluyor ikili olarak aynı dizinde oluşturulur.  Ancak, ikili burada oluşturulmuş başka bir makine profili senaryoları çalıştırdığınızda durumda olabileceğinden ikili mutlak yolu, mevcut değilse, ayarlayabileceğiniz `VCPROFILE_PATH` mevcut bir yolu.  
  
## <a name="example"></a>Örnek  
  
```  
set VCPROFILE_PATH=c:\  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Profil temelli iyileştirmeler için ortam değişkenleri](../../build/reference/environment-variables-for-profile-guided-optimizations.md)