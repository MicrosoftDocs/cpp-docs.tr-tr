---
title: Proje Derleme Hatası PRJ0006
ms.date: 11/04/2016
f1_keywords:
- PRJ0006
helpviewer_keywords:
- PRJ0006
ms.assetid: ce092be4-1652-414f-8cb5-b97ef5841f89
ms.openlocfilehash: d62c774411fda80a3e94044b3272567177328ff5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62359663"
---
# <a name="project-build-error-prj0006"></a>Proje Derleme Hatası PRJ0006

Geçici dosya 'dosyası açılamadı. Dosyanın varolduğundan ve dizinin değil yazma korumalı emin olun.

Visual C++ derleme işlemi sırasında geçici dosya oluşturulamadı. Buna ilişkin nedenler:

- Geçici dizin yok.

- Geçici dizin salt okunur.

- Disk alanı yetersiz.

- $(Intdir) ya da klasördür salt okunur veya salt okunur geçici dosyalar içeriyor.

Bu hata ayrıca şu hatayı PRJ0007 meydana gelir: Çıkış dizini 'dizin' oluşturulamadı. Hatası PRJ0007 $(ıntdir) dizini oluşturulamadı, geçici olarak dosyalarının oluşturulmasını olduğunu belirtmek de başarısız olur anlamına gelir.

Belirttiğiniz her geçici dosyalar oluşturulur:

- Bir yanıt dosyası.

- Özel derleme adımı.

- Bir derleme olay.