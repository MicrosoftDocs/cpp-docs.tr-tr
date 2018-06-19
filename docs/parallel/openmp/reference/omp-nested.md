---
title: OMP_NESTED | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- OMP_NESTED
dev_langs:
- C++
helpviewer_keywords:
- OMP_NESTED OpenMP environment variable
ms.assetid: c43f5287-a548-40d0-bd54-0c6b2b9f9a53
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c6b51df88ae700f81cf84250cc06ae24c9131fec
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691228"
---
# <a name="ompnested"></a>OMP_NESTED
İç içe geçmiş paralellik etkin veya ile devre dışı sürece iç içe geçmiş paralellik, etkinleştirilip etkinleştirilmediğini belirtir `omp_set_nested`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
set OMP_NESTED[=TRUE | =FALSE]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `OMP_NESTED` Ortam değişkeni geçersiz kılınmış tarafından [omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md) işlevi.  
  
 Varsayılan değer OpenMP standart Visual C++ uygulamasında `OMP_DYNAMIC=FALSE`.  
  
 Daha fazla bilgi için bkz: [4,4 OMP_NESTED](../../../parallel/openmp/4-4-omp-nested.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki komut kümelerini `OMP_NESTED` true ortam değişkeni:  
  
```  
set OMP_NESTED=TRUE  
```  
  
 Aşağıdaki komut geçerli ayarını görüntüler `OMP_NESTED` ortam değişkeni:  
  
```  
set OMP_NESTED  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ortam Değişkenleri](../../../parallel/openmp/reference/openmp-environment-variables.md)