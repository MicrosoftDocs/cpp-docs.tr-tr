---
title: "Varsayılan (OpenMP) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: default
dev_langs: C++
helpviewer_keywords:
- default OpenMP clause
- defaults, OpenMP clause
ms.assetid: 96055106-a8f0-40b3-8319-e412b6e07bf8
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: caafb7818c32dad7b21ac7a05d10f77753c1da73
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="default-openmp"></a>default (OpenMP)
Paralel bir bölgede dizininden kapsam dışı değişkenleri davranışını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
default(shared | none)  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `shared`, geçerli olduğu varsa `default` yan tümcesi belirtilmezse, ile belirtilmiş olması durumunda gibi paralel bir bölgedeki herhangi bir değişken kabul edilecek anlamına gelir [paylaşılan](../../../parallel/openmp/reference/shared-openmp.md) yan tümcesi. `none`ile kapsamlı olmayan paralel bir bölgede kullanılan değişkenler anlamına [özel](../../../parallel/openmp/reference/private-openmp.md), [paylaşılan](../../../parallel/openmp/reference/shared-openmp.md), [azaltma](../../../parallel/openmp/reference/reduction.md), [firstprivate](../../../parallel/openmp/reference/firstprivate.md), veya [lastprivate](../../../parallel/openmp/reference/lastprivate.md) yan tümcesi derleyici hatası neden olur.  
  
 `default`Aşağıdaki yönergeleri için geçerlidir:  
  
-   [Paralel](../../../parallel/openmp/reference/parallel.md)  
  
-   [için](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [bölümler](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Daha fazla bilgi için bkz: [2.7.2.5 varsayılan](../../../parallel/openmp/2-7-2-5-default.md).  
  
## <a name="example"></a>Örnek  
 Bkz: [özel](../../../parallel/openmp/reference/private-openmp.md) kullanma örneği için `default`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yan tümceleri](../../../parallel/openmp/reference/openmp-clauses.md)