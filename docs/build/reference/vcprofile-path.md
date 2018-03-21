---
title: VCPROFILE_PATH | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VCPROFILE_PATH
dev_langs:
- C++
helpviewer_keywords:
- VCPROFILE_PATH environment variable
ms.assetid: 25217aa4-7e86-4eba-854d-10b3c457e4df
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ea682b70f4417ef49bfca530af5f12f21699a389
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [Profil Temelli İyileştirmeler için Ortam Değişkenleri](../../build/reference/environment-variables-for-profile-guided-optimizations.md)