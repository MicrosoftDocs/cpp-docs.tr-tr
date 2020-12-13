---
description: 'Daha fazla bilgi edinin: ML Önemli Hatası A1007'
title: ML Önemli Hatası A1007
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A1007
helpviewer_keywords:
- A1007
ms.assetid: bcf9c826-beb3-4e93-91fe-1ffd34995fbf
ms.openlocfilehash: c26d5de1c1b44fb37d4a95f51b2cb9480d2ba664
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97129551"
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
