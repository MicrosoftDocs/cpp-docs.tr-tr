---
title: Derleyici Hatası C3087 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3087
dev_langs:
- C++
helpviewer_keywords:
- C3087
ms.assetid: 4f5bdd52-a853-4f02-b160-6868e9190b9d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6e1446d8d062f97e9161e62fae5052580174c83
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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