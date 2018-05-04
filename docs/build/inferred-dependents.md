---
title: Çıkarımı yapılan bağımlılıklar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inferred dependents in NMAKE
- dependents, inferred
ms.assetid: 9303045c-69b3-4f35-bffc-19d5cd6ea3c3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a86ed1a8fe6c97ae11af50f59cb639ef6fd7c1da
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="inferred-dependents"></a>Çıkarsanan Bağımlılıklar
Çıkarsanan bağımlı bir çıkarım kuralından türetilmiş ve açık bağımlıları önce değerlendirilir. NMAKE oluşturulursa bağımlı hedefine göre güncel ise, bağımlılık komutları bloğunu çağırır. Çıkarsanan bağımlı yok veya kendi bağımlıları göre güncel değilse NMAKE oluşturulursa bağımlı ilk güncelleştirir. Çıkarsanan bağımlılıklar hakkında daha fazla bilgi için bkz: [çıkarım kuralları](../build/inference-rules.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağımlılıklar](../build/dependents.md)