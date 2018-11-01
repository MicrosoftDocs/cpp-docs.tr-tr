---
title: Çıkarsanan Bağımlılıklar
ms.date: 11/04/2016
helpviewer_keywords:
- inferred dependents in NMAKE
- dependents, inferred
ms.assetid: 9303045c-69b3-4f35-bffc-19d5cd6ea3c3
ms.openlocfilehash: 958a33c29be0d68fee1044fff1d81235ea9370c6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50641382"
---
# <a name="inferred-dependents"></a>Çıkarsanan Bağımlılıklar

Çıkarsanan bir bağımlı bir çıkarma kuralı türetilir ve açık bağımlıları önce değerlendirilir. Çıkarsanan bir bağımlı hedefine göre güncel değil, bağımlılık komutları blok NMAKE çağırır. Çıkarsanan bir bağımlı yok veya kendi bağımlıları göre güncel değilse NMAKE çıkarsanan bağımlı ilk güncelleştirir. Çıkarsanan bağımlılıklar hakkında daha fazla bilgi için bkz: [çıkarım kuralları](../build/inference-rules.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Bağımlılıklar](../build/dependents.md)