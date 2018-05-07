---
title: Derleyici Hatası C2002 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2002
dev_langs:
- C++
helpviewer_keywords:
- C2002
ms.assetid: 91982314-203a-4de1-b884-94e39a623f61
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 01124fc839d6e788ff2dccae325f01f7d4337f5d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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