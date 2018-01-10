---
title: "Önemli hata C1021 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C1021
dev_langs: C++
helpviewer_keywords: C1021
ms.assetid: e23171f4-ca6b-40c0-a913-a2edc6fa3766
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cc291812a582332ec281a3bead2a9b0fede88869
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1021"></a>Önemli hata C1021
Geçersiz önişlemci komut 'string'  
  
 `string`Geçerli bir değil [önişlemci yönergesi](../../preprocessor/preprocessor-directives.md). Hatayı gidermek için geçerli bir önişlemci ad kullanmak `string`.  
  
 Aşağıdaki örnek C1021 oluşturur:  
  
```  
// C1021.cpp  
#BadPreProcName    // C1021 delete line  
```