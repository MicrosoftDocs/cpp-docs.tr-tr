---
title: Önemli hata C1900
ms.date: 11/04/2016
f1_keywords:
- C1900
helpviewer_keywords:
- C1900
ms.assetid: 3aaa583b-4c1a-45de-aa34-527d806f2cb5
ms.openlocfilehash: 6a802928315126b72397ba6e8cc61b66f46deb41
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80202846"
---
# <a name="fatal-error-c1900"></a>Önemli hata C1900

> '*Tool1*' sürümü '*Sayı1*' ve '*Tool2*' sürümü '*sayı2*' arasında Il uyuşmazlığı

Derleyicinin çeşitli geçişlerinde çalıştırılan araçlar eşleşmez. *Sayı1* ve *sayı2* dosyalardaki tarihlere başvurur. Örneğin, 1. geçişte, derleyici ön ucu (C1. dll) ve pass 2 ' de, derleyici arka ucu (C2. dll) çalıştırılır. Dosyalardaki tarihlerin eşleşmesi gerekir.

Bu sorunu onarmak için tüm güncelleştirmelerin Visual Studio 'ya uygulandığından emin olun. Sorun devam ederse, Visual Studio 'Yu onarmak veya yeniden yüklemek için Windows Denetim Masası 'ndaki **Programlar ve Özellikler** ' i kullanın.
