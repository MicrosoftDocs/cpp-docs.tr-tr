---
title: "Çıkarımı yapılan bağımlılıklar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- inferred dependents in NMAKE
- dependents, inferred
ms.assetid: 9303045c-69b3-4f35-bffc-19d5cd6ea3c3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 410e52dd9ee9605f6e29b81491bda0f4883e1cf9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="inferred-dependents"></a>Çıkarsanan Bağımlılıklar
Çıkarsanan bağımlı bir çıkarım kuralından türetilmiş ve açık bağımlıları önce değerlendirilir. NMAKE oluşturulursa bağımlı hedefine göre güncel ise, bağımlılık komutları bloğunu çağırır. Çıkarsanan bağımlı yok veya kendi bağımlıları göre güncel değilse NMAKE oluşturulursa bağımlı ilk güncelleştirir. Çıkarsanan bağımlılıklar hakkında daha fazla bilgi için bkz: [çıkarım kuralları](../build/inference-rules.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağımlılıklar](../build/dependents.md)