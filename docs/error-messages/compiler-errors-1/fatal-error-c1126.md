---
title: Önemli hata C1126 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1126
dev_langs:
- C++
helpviewer_keywords:
- C1126
ms.assetid: f22b26a6-8ad7-47cf-a237-196c8ea60aca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f014aafc60a36bfbb4edad50e7e3ceede6e3c8b2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062481"
---
# <a name="fatal-error-c1126"></a>Önemli hata C1126

'identifier': otomatik ayırma boyutu aşıyor

Bir işlev (artı swappable işlevleri için ek bir 20 bayt gibi derleyici tarafından kullanılan alanı sınırlı miktarda) yerel değişkenler için ayrılan alanı sınırını aşıyor.

Bu hatayı düzeltmek için `malloc` veya `new` büyük miktarlarda verinin ayrılamıyor.