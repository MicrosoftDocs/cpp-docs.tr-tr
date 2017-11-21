---
title: "Derleyici Hatası C3624 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3624
dev_langs: C++
helpviewer_keywords: C3624
ms.assetid: eaac6a4f-eb11-4e4d-ab12-124ba995c5cf
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8ce571a05b801361f8e0a5f21c9dba1c159bbf88
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3624"></a>Derleyici Hatası C3624
'type': Böyle bir kullanımını gerektirir 'assembly' derlemesine başvuru  
  
 Kodunuzu derleyin için gereken bir derleme (başvuru) belirtilmedi; derlemeye geçirmek [#using](../../preprocessor/hash-using-directive-cpp.md) yönergesi.  
  
## <a name="example"></a>Örnek  
Aşağıdaki örnek C3624 oluşturur:  
  
```  
// C3624.cpp  
// compile with: /clr /c  
#using <System.Windows.Forms.dll>  
  
// Uncomment the following 2 lines to resolve.  
// #using <System.dll>  
// #using <System.Drawing.dll>  
  
using namespace System;  
  
public ref class MyForm : public Windows::Forms::Form {};   // C3624  
```  
