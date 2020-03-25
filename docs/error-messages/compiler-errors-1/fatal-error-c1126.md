---
title: Önemli hata C1126
ms.date: 11/04/2016
f1_keywords:
- C1126
helpviewer_keywords:
- C1126
ms.assetid: f22b26a6-8ad7-47cf-a237-196c8ea60aca
ms.openlocfilehash: a6c9d06cd087eb4462ae475cc1f6d64ba451887f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80203672"
---
# <a name="fatal-error-c1126"></a>Önemli hata C1126

' tanımlayıcı ': Otomatik ayırma boyutu aşıyor

Bir işlevin yerel değişkenleri için ayrılan alan (ek olarak, takas edilebilir işlevler için fazladan 20 bayt) sınırı aşarak derleyici tarafından kullanılan sınırlı miktarda alan.

Bu hatayı düzeltmek için, büyük miktarlarda veri ayırmak üzere `malloc` veya `new` kullanın.
