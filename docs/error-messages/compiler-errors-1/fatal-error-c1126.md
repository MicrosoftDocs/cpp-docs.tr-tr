---
title: Önemli hata C1126
ms.date: 11/04/2016
f1_keywords:
- C1126
helpviewer_keywords:
- C1126
ms.assetid: f22b26a6-8ad7-47cf-a237-196c8ea60aca
ms.openlocfilehash: 3f4d152163d3b21ddf99644c34e63f35ca15e6e9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50457787"
---
# <a name="fatal-error-c1126"></a>Önemli hata C1126

'identifier': otomatik ayırma boyutu aşıyor

Bir işlev (artı swappable işlevleri için ek bir 20 bayt gibi derleyici tarafından kullanılan alanı sınırlı miktarda) yerel değişkenler için ayrılan alanı sınırını aşıyor.

Bu hatayı düzeltmek için `malloc` veya `new` büyük miktarlarda verinin ayrılamıyor.