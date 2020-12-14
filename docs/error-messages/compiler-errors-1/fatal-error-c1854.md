---
description: 'Daha fazla bilgi edinin: önemli hata C1854'
title: Önemli hata C1854
ms.date: 11/04/2016
f1_keywords:
- C1854
helpviewer_keywords:
- C1854
ms.assetid: 8c21a9cc-1737-475c-9e57-8725cd8937c1
ms.openlocfilehash: 1c08db55089853545afa511213fc164c978bd4ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276211"
---
# <a name="fatal-error-c1854"></a>Önemli hata C1854

> nesne dosyasındaki ön derlenmiş üstbilginin oluşturulması sırasında oluşturulan bilgilerin üzerine yazılamıyor: '*filename*'

Aynı dosya için [/i (ön](../../build/reference/yc-create-precompiled-header-file.md) derlenmiş üstbilgi dosyası oluştur) seçeneğini belirttikten sonra [/yu (ön derlenmiş üstbilgi dosyası kullan](../../build/reference/yu-use-precompiled-header-file.md) ) seçeneğini belirttiniz.

Bu sorunu onarmak için, genel olarak, projenizdeki yalnızca bir dosyayı **/Yıc** seçeneği kullanılarak derlenecek şekilde ayarlayın ve **/yu** seçeneğini kullanarak diğer tüm dosyaları derlemek için ayarlayın. **/İ** seçeneğinin kullanımıyla ilgili ayrıntılar ve VISUAL Studio IDE 'de nasıl ayarlanacağı hakkında daha fazla bilgi için bkz. [/rivc (önceden derlenmiş üst bilgi dosyası oluştur)](../../build/reference/yc-create-precompiled-header-file.md). Önceden derlenmiş üstbilgileri kullanma hakkında daha fazla bilgi için bkz. [önceden derlenmiş üst bilgi dosyaları oluşturma](../../build/creating-precompiled-header-files.md).
