---
title: "Giriş akışı nesneleri oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: input stream objects
ms.assetid: ab94866e-6ffe-4f15-b4db-0bd23e636075
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d284452e7b6c9983a751117ad6c2290b267c6994
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="constructing-input-stream-objects"></a>Giriş Akışı Oluşturma Nesneleri
Yalnızca kullanıyorsanız `cin` nesnesi, bir giriş akışı oluşturmak gerekmez. Kullanırsanız, bir giriş akışı oluşturmalıdır:  
  
- [Giriş dosyası akış oluşturucular](#vclrfinputfilestreamconstructorsanchor8)  
  
- [Giriş dizesi akış oluşturucular](#vclrfinputstringstreamconstructorsanchor9)  
  
##  <a name="vclrfinputfilestreamconstructorsanchor8"></a>Giriş dosyası akış oluşturucular  
 Bir giriş dosya akışı oluşturmanın iki yolu vardır:  
  
-   Kullanım `void` bağımsız değişkeni oluşturucusu,'ı çağırın `open` üye işlevi:  
  
 ```  
    ifstream myFile; // On the stack  
    myFile.open("filename");

 
    ifstream* pmyFile = new ifstream; // On the heap  
    pmyFile->open("filename");
```  
  
-   Böylece oluşturma işlemi sırasında dosya açılırken Oluşturucusu çağrısı filename ve modu bayrakları belirtin:  
  
 ```  
    ifstream myFile("filename");
```  
  
##  <a name="vclrfinputstringstreamconstructorsanchor9"></a>Giriş dizesi akış oluşturucular  
 Giriş dizesi akış oluşturucular ön tahsis, preinitialized depolama adresini gerektirir:  
  
```  
string s("123.45");

double amt;  
istringstream myString(s);

//istringstream myString("123.45") also works  
myString>> amt; // amt contains 123.45  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Giriş Akışları](../standard-library/input-streams.md)

