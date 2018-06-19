---
title: Reprivatization A.30 kullanımını | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 26529090-6c39-40f2-b806-e12374d6b5f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6026bba31fcc0db4e28ced14b3e847ac0cf8bf58
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33689616"
---
# <a name="a30---use-of-reprivatization"></a>A.30   Yeniden Özelleştirmenin Kullanımı
Aşağıdaki örnek, değişkenlerin reprivatization gösterir. Özel değişkenler işaretlenir `private` iç içe geçmiş yönergesi içinde yeniden. Kapsayan paralel bölgede paylaşılan gerekmez.  
  
```  
int i, a;  
...  
#pragma omp parallel private(a)  
{  
  ...  
  #pragma omp parallel for private(a)  
  for (i=0; i<10; i++)  
     {  
       ...  
     }  
}  
```