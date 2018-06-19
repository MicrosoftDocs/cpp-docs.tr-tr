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
ms.openlocfilehash: 2a3ff02d69679074186e593d5e1c16bdf56d1052
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33225920"
---
# <a name="fatal-error-c1126"></a>Önemli hata C1126
'tanımlayıcısı': otomatik ayırma boyutu aşıyor.  
  
 Bir işlev (artı swappable işlevleri için ek bir 20 bayt gibi derleyici tarafından kullanılan alanı sınırlı miktarda) yerel değişkenler için ayrılan alanı sınırını aşıyor.  
  
 Bu hatayı düzeltmek için kullanmak `malloc` veya `new` büyük miktarlarda verinin ayrılamadı.