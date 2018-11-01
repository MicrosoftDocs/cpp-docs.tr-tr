---
title: Bağlayıcı Araçları Hatası LNK2017
ms.date: 11/04/2016
f1_keywords:
- LNK2017
helpviewer_keywords:
- LNK2017
ms.assetid: f7c21733-b0fb-4888-a295-9b453ba6ee77
ms.openlocfilehash: ce5332c2812740ef0b8c7d8e9c64a095d20a4e2b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50641476"
---
# <a name="linker-tools-error-lnk2017"></a>Bağlayıcı Araçları Hatası LNK2017

'symbol' yerleştirme 'kesimi': No geçersiz

32 bit adresli 64 bit bir görüntü oluşturmaya çalıştığınız. Bunu yapmak için şunları yapmalısınız:

- Bir sabit yük adresi kullanın.

- Görüntüyü 3 GB ile kısıtlayın.

- Belirtin [: No](../../build/reference/largeaddressaware-handle-large-addresses.md).