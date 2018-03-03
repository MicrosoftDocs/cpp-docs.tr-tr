---
title: "Derleyici Hatası C3087 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3087
dev_langs:
- C++
helpviewer_keywords:
- C3087
ms.assetid: 4f5bdd52-a853-4f02-b160-6868e9190b9d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8553611e131904df8c2a67928cc695456598fe8c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3087"></a>Derleyici Hatası C3087
'named_argument': 'öznitelik' çağrısı zaten bu üye başlatır  
  
 Adlandırılmış bağımsız değişken için aynı değeri adlandırılmamış bağımsız değişken olarak aynı öznitelik bloğundaki belirtildi. Yalnızca bir adlandırılmış veya adlandırılmamış bağımsız değişkenini belirtin.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3087 oluşturur.  
  
```  
// C3087.cpp  
// compile with: /c  
[idl_quote("quote1", text="quote2")];   // C3087  
[idl_quote(text="quote3")];   // OK  
[idl_quote("quote4")];   // OK  
```