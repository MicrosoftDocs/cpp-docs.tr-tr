---
title: ML önemli hatası A1007 | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A1007
dev_langs:
- C++
helpviewer_keywords:
- A1007
ms.assetid: bcf9c826-beb3-4e93-91fe-1ffd34995fbf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 539ab431510d5dc721e6531c11069a87e27c287a
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43693607"
---
# <a name="ml-fatal-error-a1007"></a>ML Önemli Hatası A1007

**çok derin iç içe geçme düzeyi**

Derleyici iç içe geçme sınırına ulaşıldı. Tersi belirtilmedikçe hariç 20 düzeyleri sınırlıdır.

Aşağıdakilerden biri çok derin iç içe geçmiş:

- Gibi üst düzey bir yönerge [. Eğer](../../assembler/masm/dot-if.md), [. Yineleme](../../assembler/masm/dot-repeat.md), veya [. SIRADA](../../assembler/masm/dot-while.md).

- Bir yapı tanımı.

- Bir koşullu derleme yönergesi.

- Bir yordamı tanımı.

- A [PUSHCONTEXT](../../assembler/masm/pushcontext.md) yönergesi (sınır: 10).

- Segment tanımı.

- Bir ekleme dosyası.

- Makro.

## <a name="see-also"></a>Ayrıca bkz.

[ML Hata İletileri](../../assembler/masm/ml-error-messages.md)<br/>