---
title: Önemli hata C1026
ms.date: 11/04/2016
f1_keywords:
- C1026
helpviewer_keywords:
- C1026
ms.assetid: 89bb9d40-673a-44aa-a9f4-b42c07b49d44
ms.openlocfilehash: a7c7a5da01c8b4a44c307a00f53530acb12a8009
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80204659"
---
# <a name="fatal-error-c1026"></a>Önemli hata C1026

Ayrıştırıcı yığını taştı, program çok karmaşık

Programı ayrıştırmak için gereken alan, bir derleyici yığını taşmasına neden oldu.

İfadelerin karmaşıklığını şu şekilde azaltın:

- `for` ve `switch` deyimlerine iç içe geçme. Daha derin iç içe geçmiş deyimlerini ayrı işlevlere koyun.

- Virgül işleçleri veya işlev çağrıları içeren uzun ifadeleri bölmek.
