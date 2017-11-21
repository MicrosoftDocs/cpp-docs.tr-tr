---
title: "Çıkarımı yapılan bağımlılıklar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- inferred dependents in NMAKE
- dependents, inferred
ms.assetid: 9303045c-69b3-4f35-bffc-19d5cd6ea3c3
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: eaf75c067b2e96e5ae4a893b56376bfc1b9bd1e7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="inferred-dependents"></a>Çıkarsanan Bağımlılıklar
Çıkarsanan bağımlı bir çıkarım kuralından türetilmiş ve açık bağımlıları önce değerlendirilir. NMAKE oluşturulursa bağımlı hedefine göre güncel ise, bağımlılık komutları bloğunu çağırır. Çıkarsanan bağımlı yok veya kendi bağımlıları göre güncel değilse NMAKE oluşturulursa bağımlı ilk güncelleştirir. Çıkarsanan bağımlılıklar hakkında daha fazla bilgi için bkz: [çıkarım kuralları](../build/inference-rules.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağımlılıklar](../build/dependents.md)