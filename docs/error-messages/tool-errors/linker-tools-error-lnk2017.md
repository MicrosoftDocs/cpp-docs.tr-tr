---
title: Bağlayıcı Araçları Hatası LNK2017
ms.date: 11/04/2016
f1_keywords:
- LNK2017
helpviewer_keywords:
- LNK2017
ms.assetid: f7c21733-b0fb-4888-a295-9b453ba6ee77
ms.openlocfilehash: 02e80de5c34809a331003f3b0fb28d32e138a531
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194739"
---
# <a name="linker-tools-error-lnk2017"></a>Bağlayıcı Araçları Hatası LNK2017

' segment ' için ' symbol ' konum değişikliği/LARGEADDRESSAWARE: NO olmadan geçersizdir

32 bit adreslerle 64 bitlik bir görüntü oluşturmaya çalışıyorsunuz. Bunu yapmak için şunları yapmanız gerekir:

- Sabit bir yükleme adresi kullanın.

- Görüntüyü 3 GB ile sınırlayın.

- [/LARGEADDRESSAWARE: No](../../build/reference/largeaddressaware-handle-large-addresses.md)belirtin.
