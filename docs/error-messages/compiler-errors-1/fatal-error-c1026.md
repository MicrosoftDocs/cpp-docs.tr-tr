---
title: Önemli hata C1026
ms.date: 11/04/2016
f1_keywords:
- C1026
helpviewer_keywords:
- C1026
ms.assetid: 89bb9d40-673a-44aa-a9f4-b42c07b49d44
ms.openlocfilehash: 9ea97bef16bebb8fc0e765ed708e54baee9a64de
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220346"
---
# <a name="fatal-error-c1026"></a>Önemli hata C1026

Ayrıştırıcı yığını taştı, program çok karmaşık

Programı ayrıştırmak için gereken alan, bir derleyici yığını taşmasına neden oldu.

İfadelerin karmaşıklığını şu şekilde azaltın:

- **`for`** Ve deyimlerine iç içe geçme **`switch`** . Daha derin iç içe geçmiş deyimlerini ayrı işlevlere koyun.

- Virgül işleçleri veya işlev çağrıları içeren uzun ifadeleri bölmek.
