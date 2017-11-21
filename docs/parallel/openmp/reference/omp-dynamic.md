---
title: OMP_DYNAMIC | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: OMP_DYNAMIC
dev_langs: C++
helpviewer_keywords: OMP_DYNAMIC OpenMP environment variable
ms.assetid: e306049d-b644-4b73-8b63-46c835bff98b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b5c416919678cd7b0f80bd1299c7682fe159cd19
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ompdynamic"></a>OMP_DYNAMIC
Çalışma zamanı OpenMP paralel bir bölgede iş parçacığı sayısını ayarlayabilirsiniz olup olmadığını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
set OMP_DYNAMIC[=TRUE | =FALSE]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `OMP_DYNAMIC` Ortam değişkeni geçersiz kılınmış tarafından [omp_set_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md) işlevi.  
  
 Varsayılan değer OpenMP standart Visual C++ uygulamasında `OMP_DYNAMIC=FALSE`.  
  
 Daha fazla bilgi için bkz: [4.3 omp_dynamıc](../../../parallel/openmp/4-3-omp-dynamic.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki komut kümelerini `OMP_DYNAMIC` true ortam değişkeni:  
  
```  
set OMP_DYNAMIC=TRUE  
```  
  
 Aşağıdaki komut geçerli ayarını görüntüler `OMP_DYNAMIC` ortam değişkeni:  
  
```  
set OMP_DYNAMIC  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ortam değişkenleri](../../../parallel/openmp/reference/openmp-environment-variables.md)