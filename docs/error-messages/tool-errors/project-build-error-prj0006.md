---
title: Proje derleme hatası PRJ0006 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0006
dev_langs:
- C++
helpviewer_keywords:
- PRJ0006
ms.assetid: ce092be4-1652-414f-8cb5-b97ef5841f89
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 264b2f90a2d778b1545117ce5c3b1272626ebad6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46073258"
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