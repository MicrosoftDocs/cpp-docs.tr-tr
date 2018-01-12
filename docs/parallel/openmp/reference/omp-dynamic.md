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
ms.workload: cplusplus
ms.openlocfilehash: 900f3e4ddd0e9901e72ed65f12bc036d87a6956e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [Ortam Değişkenleri](../../../parallel/openmp/reference/openmp-environment-variables.md)