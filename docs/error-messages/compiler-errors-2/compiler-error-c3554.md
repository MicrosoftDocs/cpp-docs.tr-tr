---
title: Derleyici Hatası C3554 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3554
dev_langs:
- C++
helpviewer_keywords:
- C3554
ms.assetid: aede18d5-fefc-4da9-9b69-adfe90bfa742
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4fb374e028097157ae72b621593a899af9fe2f91
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33255459"
---
# <a name="compiler-error-c3554"></a>Derleyici Hatası C3554
'decltype' tüm diğer tür-belirteci ile birlikte kullanılamaz  
  
 Nitelemek olamaz `decltype()` anahtar sözcüğüyle hiçbir tür belirteci. Örneğin, aşağıdaki kod parçası C3554 hata verir.  
  
```  
int x;  
unsigned decltype(x); // C3554  
```