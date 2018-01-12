---
title: "Çıkış akış nesnelerini oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: output stream objects
ms.assetid: 93c8eab6-610c-4f48-b76d-1d960cac7641
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 04cbb5ae7433dc31e99136c11c4022e60ad4808e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="constructing-output-stream-objects"></a>Çıkış Akış Nesnelerini Oluşturma
Yalnızca önceden tanımlanmış kullanırsanız `cout`, `cerr`, veya `clog` nesneleri, çıkış akışına oluşturmak gerekmez. Oluşturucuları için kullanmanız gerekir:  
  
- [Çıkış dosya akışı oluşturucular](#vclrfoutputfilestreamconstructorsanchor1)  
  
- [Çıkış dizesi akış oluşturucular](#vclrfoutputstringstreamconstructorsanchor2)  
  
##  <a name="vclrfoutputfilestreamconstructorsanchor1"></a>Çıkış dosya akışı oluşturucular  
 Çıkış dosya akışı iki yoldan biriyle oluşturabileceğiniz:  
  
-   Varsayılan bir oluşturucu kullanın ve ardından arama `open` üye işlevi.  
  
 ```  
    ofstream myFile; // Static or on the stack  
    myFile.open("filename");

 
    ofstream* pmyFile = new ofstream; // On the heap  
    pmyFile->open("filename");
```  
  
-   Bir dosya adı ve modu bayrakları Oluşturucusu çağrısında belirtin.  
  
 ```  
    ofstream myFile("filename", ios_base::out);
```  
  
##  <a name="vclrfoutputstringstreamconstructorsanchor2"></a>Çıkış dizesi akış oluşturucular  
 Bir çıkış dizesi akışı oluşturmak için kullanabileceğiniz `ostringstream` şu şekilde:  
  
```  
    using namespace std;  
string sp;  
ostringstream myString;  
myString <<"this is a test" <<ends;  
sp = myString.str();
// Obtain string  
cout <<sp <endl;   
```  
  
 `ends` "Manipulator" gerekli sonlandırma null karakter dizesi olarak ekler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çıkış Akışları](../standard-library/output-streams.md)

