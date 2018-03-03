---
title: "Derleyici Hatası C2002 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2002
dev_langs:
- C++
helpviewer_keywords:
- C2002
ms.assetid: 91982314-203a-4de1-b884-94e39a623f61
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9a2cbd21c27cff3effad69b19f42eeaecacf20d6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2002"></a>Derleyici Hatası C2002
Geçersiz joker karakter sabiti  
  
 Çok baytlı karakter sabiti geçerli değil.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için  
  
1.  Joker karakter sabiti beklenenden daha fazla bayt içerir.  
  
2.  Standart üstbilgi STDDEF.h dahil değildir.  
  
3.  Geniş karakterler sıradan dize değişmez değerleri ile birleştirilmiş olamaz.  
  
4.  Joker karakter sabiti 'L' karakteriyle gelmelidir:  
  
    ```  
    L'mbconst'  
    ```  
  
5.  Microsoft C++ için ASCII önişlemci yönergesi metin bağımsız olması gerekir. Örneğin, yönergesi `#pragma message(L"string")`, geçerli değil.