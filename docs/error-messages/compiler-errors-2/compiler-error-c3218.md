---
title: "Derleyici Hatası C3218 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3218
dev_langs: C++
helpviewer_keywords: C3218
ms.assetid: 0eea19e0-503e-4e07-ae8b-2cb2e95922cd
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 69ee49ece7354ce713fcfb86368aaca35b06cda7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3218"></a>Derleyici Hatası C3218
'type': türü bir kısıtlama olarak izin verilmiyor  
  
 Bir kısıtlaması olmasını türü için bir değer türü veya bir yönetilen sınıf veya arabirim başvurusu olmalıdır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3218 oluşturur.  
  
```  
// C3218.cpp  
// compile with: /clr /c  
class A {};  
ref class B {};  
  
// Delete the following 3 lines to resolve.  
generic <class T>  
where T : A   // C3218  
ref class C {};  
  
// OK  
generic <class T>  
where  T : B  
ref class D {};  
```