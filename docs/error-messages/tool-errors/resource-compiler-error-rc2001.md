---
title: Kaynak Derleyicisi Hatası RC2001
ms.date: 11/04/2016
f1_keywords:
- RC2001
helpviewer_keywords:
- RC2001
ms.assetid: 92bfb4c0-1879-4606-bb9f-ef7368707b4a
ms.openlocfilehash: f4755e04a744d94636b4b37aaf727e0d733008ef
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50602117"
---
# <a name="resource-compiler-error-rc2001"></a>Kaynak Derleyicisi Hatası RC2001

Sabitte

Bir dize sabitine olmadan ya da ikinci satırında bir ters eğik çizgi devam edildi (**\\**) veya kapatma ve açma çift tırnak (**"**).

Kaynak dosyada iki satıra olan bir dize sabitine ayırmak için aşağıdakilerden birini yapın:

- İlk satır satır devamlılığı karakteri olan ters eğik çizgi ile bitmelidir.

- Çift tırnak işareti ile ilk satırdaki dize kapatın ve başka bir tırnak işareti ile dizeyi sonraki satıra açın.

\N, yeni satır karakteri bir dize sabiti ekleme için çıkış dizisi ile ilk satırın sonunda için yeterli değil.