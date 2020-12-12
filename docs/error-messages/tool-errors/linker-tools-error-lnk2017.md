---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları hata LNK2017'
title: Bağlayıcı Araçları Hatası LNK2017
ms.date: 11/04/2016
f1_keywords:
- LNK2017
helpviewer_keywords:
- LNK2017
ms.assetid: f7c21733-b0fb-4888-a295-9b453ba6ee77
ms.openlocfilehash: e4215d7c1730f85f43c2440163fa03ad97c741e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338445"
---
# <a name="linker-tools-error-lnk2017"></a>Bağlayıcı Araçları Hatası LNK2017

' segment ' için ' symbol ' konum değişikliği/LARGEADDRESSAWARE: NO olmadan geçersizdir

32 bit adreslerle 64 bitlik bir görüntü oluşturmaya çalışıyorsunuz. Bunu yapmak için şunları yapmanız gerekir:

- Sabit bir yükleme adresi kullanın.

- Görüntüyü 3 GB ile sınırlayın.

- [/LARGEADDRESSAWARE: No](../../build/reference/largeaddressaware-handle-large-addresses.md)belirtin.
