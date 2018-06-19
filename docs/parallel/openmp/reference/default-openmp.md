---
title: Varsayılan (OpenMP) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- default
dev_langs:
- C++
helpviewer_keywords:
- default OpenMP clause
- defaults, OpenMP clause
ms.assetid: 96055106-a8f0-40b3-8319-e412b6e07bf8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9fc39951270138e9bd243172b289e7bd96190f14
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692327"
---
# <a name="default-openmp"></a>default (OpenMP)
Paralel bir bölgede dizininden kapsam dışı değişkenleri davranışını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
default(shared | none)  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `shared`, geçerli olduğu varsa `default` yan tümcesi belirtilmezse, ile belirtilmiş olması durumunda gibi paralel bir bölgedeki herhangi bir değişken kabul edilecek anlamına gelir [paylaşılan](../../../parallel/openmp/reference/shared-openmp.md) yan tümcesi. `none` ile kapsamlı olmayan paralel bir bölgede kullanılan değişkenler anlamına [özel](../../../parallel/openmp/reference/private-openmp.md), [paylaşılan](../../../parallel/openmp/reference/shared-openmp.md), [azaltma](../../../parallel/openmp/reference/reduction.md), [firstprivate](../../../parallel/openmp/reference/firstprivate.md), veya [lastprivate](../../../parallel/openmp/reference/lastprivate.md) yan tümcesi derleyici hatası neden olur.  
  
 `default` Aşağıdaki yönergeleri için geçerlidir:  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [Bölümler](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Daha fazla bilgi için bkz: [2.7.2.5 varsayılan](../../../parallel/openmp/2-7-2-5-default.md).  
  
## <a name="example"></a>Örnek  
 Bkz: [özel](../../../parallel/openmp/reference/private-openmp.md) kullanma örneği için `default`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yan Tümceler](../../../parallel/openmp/reference/openmp-clauses.md)