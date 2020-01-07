---
title: ML Önemli Hatası A1007
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A1007
helpviewer_keywords:
- A1007
ms.assetid: bcf9c826-beb3-4e93-91fe-1ffd34995fbf
ms.openlocfilehash: c9527769e0d9397de90f49cbce98b2cca42bed50
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75317129"
---
# <a name="ml-fatal-error-a1007"></a>ML Önemli Hatası A1007

**iç içe geçme düzeyi çok derin**

Derleyici, iç içe geçmiş sınırına ulaştı. Sınır, aksi belirtilmedikçe 20 düzeydir.

Aşağıdakilerden biri çok derin iç içe geçmiş:

- Gibi üst düzey bir yönerge [. Ise](dot-if.md), [. Veya TEKRARLAYıN](dot-repeat.md) [. WHILE](dot-while.md).

- Bir yapı tanımı.

- Koşullu derleme yönergesi.

- Bir yordam tanımı.

- Bir [PushContext](pushcontext.md) yönergesi (sınır 10 ' dur).

- Bir segment tanımı.

- Bir içerme dosyası.

- Bir makro.

## <a name="see-also"></a>Ayrıca bkz.

[ML Hata İletileri](ml-error-messages.md)
