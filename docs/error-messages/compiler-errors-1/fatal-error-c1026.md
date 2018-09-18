---
title: Önemli hata C1026 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1026
dev_langs:
- C++
helpviewer_keywords:
- C1026
ms.assetid: 89bb9d40-673a-44aa-a9f4-b42c07b49d44
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: db9167383df48dad274ef8941defaa53f51d3bfa
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068994"
---
# <a name="fatal-error-c1026"></a>Önemli hata C1026

Ayrıştırıcı yığını taştı, program çok karmaşık

Program ayrıştırmak için gereken alanı, bir derleyici yığın taşmasına neden oldu.

İfadeleri tarafından karmaşıklığını azaltın:

- İç içe geçme azalan `for` ve `switch` deyimleri. Daha derin şekilde iç içe geçmiş deyimler içinde ayrı işlevler yerleştirin.

- Virgül işleçleri veya işlev çağrıları içeren uzun ifadeleri ayırma.