---
title: Önemli hata C1383
ms.date: 11/04/2016
f1_keywords:
- C1383
helpviewer_keywords:
- C1383
ms.assetid: ca224d14-d687-4fd6-80c2-8b82f28924ea
ms.openlocfilehash: 6c0be830cb56b760f1397ea2b2f81b42a87e9ba6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80203092"
---
# <a name="fatal-error-c1383"></a>Önemli hata C1383

/GL derleyici seçeneği yüklü olan ortak dil çalışma zamanının sürümüyle uyumsuz

C1383, daha yeni bir derleyicisi olan ortak dil çalışma zamanının önceki bir sürümünü kullanırken ve **/clr** ve **/glile** derlerken oluşur.

Çözümlemek için, **/clr** ile **/GL** kullanmayın veya derleyicinizle birlikte gelen ortak dil çalışma zamanının sürümünü yükleyemezsiniz.

Daha fazla bilgi için bkz. [/clr (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) ve [/GL (tüm program iyileştirmesi)](../../build/reference/gl-whole-program-optimization.md).
