---
title: Önemli hata C1026
ms.date: 11/04/2016
f1_keywords:
- C1026
helpviewer_keywords:
- C1026
ms.assetid: 89bb9d40-673a-44aa-a9f4-b42c07b49d44
ms.openlocfilehash: b1a659967a9a62cb79e1084f7d1fa1729bae14da
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50666208"
---
# <a name="fatal-error-c1026"></a>Önemli hata C1026

Ayrıştırıcı yığını taştı, program çok karmaşık

Program ayrıştırmak için gereken alanı, bir derleyici yığın taşmasına neden oldu.

İfadeleri tarafından karmaşıklığını azaltın:

- İç içe geçme azalan `for` ve `switch` deyimleri. Daha derin şekilde iç içe geçmiş deyimler içinde ayrı işlevler yerleştirin.

- Virgül işleçleri veya işlev çağrıları içeren uzun ifadeleri ayırma.