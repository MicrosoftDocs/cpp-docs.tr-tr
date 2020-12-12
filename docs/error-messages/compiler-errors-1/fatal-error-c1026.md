---
description: 'Daha fazla bilgi edinin: önemli hata C1026'
title: Önemli hata C1026
ms.date: 11/04/2016
f1_keywords:
- C1026
helpviewer_keywords:
- C1026
ms.assetid: 89bb9d40-673a-44aa-a9f4-b42c07b49d44
ms.openlocfilehash: 08816f21879cf6dfbeb0389700d9a8ffdc7a40d5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345517"
---
# <a name="fatal-error-c1026"></a>Önemli hata C1026

Ayrıştırıcı yığını taştı, program çok karmaşık

Programı ayrıştırmak için gereken alan, bir derleyici yığını taşmasına neden oldu.

İfadelerin karmaşıklığını şu şekilde azaltın:

- **`for`** Ve deyimlerine iç içe geçme **`switch`** . Daha derin iç içe geçmiş deyimlerini ayrı işlevlere koyun.

- Virgül işleçleri veya işlev çağrıları içeren uzun ifadeleri bölmek.
