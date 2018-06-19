---
title: OMP_DYNAMIC | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- OMP_DYNAMIC
dev_langs:
- C++
helpviewer_keywords:
- OMP_DYNAMIC OpenMP environment variable
ms.assetid: e306049d-b644-4b73-8b63-46c835bff98b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: de4a81d861bf72943a67356577da37c36df63f69
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33695817"
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