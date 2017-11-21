---
title: "Derleyici Hatası C2002 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2002
dev_langs: C++
helpviewer_keywords: C2002
ms.assetid: 91982314-203a-4de1-b884-94e39a623f61
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d8f6fc5983a462850581f69ca32dd7c305f9e847
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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