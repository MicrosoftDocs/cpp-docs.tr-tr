---
title: Profil temelli iyileştirme hatası PG0165 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PG0165
dev_langs:
- C++
helpviewer_keywords:
- PG0165
ms.assetid: e98122e7-ddee-4a2c-96b2-d232e4c65f3e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 332751a123bf7d6414c40b79870b5edf27a3d8a7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46084217"
---
# <a name="profile-guided-optimization-error-pg0165"></a>Profil Temelli İyileştirme Hatası PG0165

'Filename.pgd' okunuyor: ' PGD sürümü desteklenmiyor (sürüm uyuşmazlığı)'.

PGD dosyaları bir belirli derleyici araç takımı için özeldir. Bu hata için kullanılan olandan farklı bir derleyici kullanırken oluşturulur *Filename*.pgd. Bu derleyici araç takımı verilerden kullanamazsınız, bu hatayı gösterir *Filename*geçerli program iyileştirme için .pgd.

Bu sorunu gidermek için yeniden *Filename*.pgd geçerli derleyici araç setini kullanarak.