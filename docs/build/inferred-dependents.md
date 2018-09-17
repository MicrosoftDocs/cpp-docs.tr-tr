---
title: Çıkarsanan bağımlılıklar | Microsoft Docs
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
ms.openlocfilehash: 631c5631b60f0e05dd1f1541facc767f35944d3d
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45701486"
---
# <a name="inferred-dependents"></a>Çıkarsanan Bağımlılıklar

Çıkarsanan bir bağımlı bir çıkarma kuralı türetilir ve açık bağımlıları önce değerlendirilir. Çıkarsanan bir bağımlı hedefine göre güncel değil, bağımlılık komutları blok NMAKE çağırır. Çıkarsanan bir bağımlı yok veya kendi bağımlıları göre güncel değilse NMAKE çıkarsanan bağımlı ilk güncelleştirir. Çıkarsanan bağımlılıklar hakkında daha fazla bilgi için bkz: [çıkarım kuralları](../build/inference-rules.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Bağımlılıklar](../build/dependents.md)