---
title: A.29 iş paylaşım yapıları içindeki critical yapı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: d5c8a83f-2f51-4f23-8ddf-d267e347507f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8574687d8fa037e0adca908e3aa761a2619d26a8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46424150"
---
# <a name="a29---use-of-work-sharing-constructs-inside-a-critical-construct"></a>A.29   İş Paylaşım Yapılarının critical Yapı İçinde Kullanımı

Aşağıdaki örnek, bir iş paylaşımı yapısı içinde kullanarak gösterir. bir `critical` oluşturun. İş paylaşım oluşturmak için bu örnek uyumludur ve `critical` yapısı paralel aynı bölgeye bağlama.

```
void f()
{
  int i = 1;
  #pragma omp parallel sections
  {
    #pragma omp section
    {
      #pragma omp critical (name)
      {
        #pragma omp parallel
        {
          #pragma omp single
          {
            i++;
          }
        }
      }
    }
  }
}
```