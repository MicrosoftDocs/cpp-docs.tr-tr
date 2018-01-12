---
title: "Önemli hata C1019 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C1019
dev_langs: C++
helpviewer_keywords: C1019
ms.assetid: c4f8968b-bc62-4200-b3ca-69d06c163236
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 77374884efcb7aee367e436f9dc07c8df9c398d5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1019"></a>Önemli hata C1019
Beklenmeyen #else  
  
 `#else` Yönergesi görünür dışında bir `#if`, `#ifdef`, veya `#ifndef` oluşturun. Kullanım `#else` yalnızca bu yapıları birini içinde.  
  
 Aşağıdaki örnek C1019 oluşturur:  
  
```  
// C1019.cpp  
#else   // C1019  
#endif  
  
int main() {}  
```  
  
 Olası çözüm:  
  
```  
// C1019b.cpp  
#if 1  
#else  
#endif  
  
int main() {}  
```