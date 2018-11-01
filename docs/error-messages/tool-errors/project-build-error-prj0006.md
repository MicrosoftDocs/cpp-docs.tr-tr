---
title: Proje Derleme Hatası PRJ0006
ms.date: 11/04/2016
f1_keywords:
- PRJ0006
helpviewer_keywords:
- PRJ0006
ms.assetid: ce092be4-1652-414f-8cb5-b97ef5841f89
ms.openlocfilehash: d62c774411fda80a3e94044b3272567177328ff5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50451565"
---
# <a name="project-build-error-prj0006"></a>Proje Derleme Hatası PRJ0006

Geçici dosya 'dosyası açılamadı. Dosyanın varolduğundan ve dizinin değil yazma korumalı emin olun.

Visual C++ derleme işlemi sırasında geçici dosya oluşturulamadı. Buna ilişkin nedenler:

- Geçici dizin yok.

- Geçici dizin salt okunur.

- Disk alanı yetersiz.

- $(Intdir) ya da klasördür salt okunur veya salt okunur geçici dosyalar içeriyor.

Bu hata ayrıca şu hatayı PRJ0007 meydana gelir: çıkış dizini 'dizin' oluşturulamadı. Hatası PRJ0007 $(ıntdir) dizini oluşturulamadı, geçici olarak dosyalarının oluşturulmasını olduğunu belirtmek de başarısız olur anlamına gelir.

Belirttiğiniz her geçici dosyalar oluşturulur:

- Bir yanıt dosyası.

- Özel derleme adımı.

- Bir derleme olay.