---
title: "Çıkış akış nesnelerini oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- output stream objects
ms.assetid: 93c8eab6-610c-4f48-b76d-1d960cac7641
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cf40e6683462803fcf81a9be915a4672baefd3e9
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="constructing-output-stream-objects"></a>Çıkış Akış Nesnelerini Oluşturma
Yalnızca önceden tanımlanmış kullanırsanız `cout`, `cerr`, veya `clog` nesneleri, çıkış akışına oluşturmak gerekmez. Oluşturucuları için kullanmanız gerekir:  
  
- [Çıkış dosya akışı oluşturucular](#vclrfoutputfilestreamconstructorsanchor1)  
  
- [Çıkış dizesi akış oluşturucular](#vclrfoutputstringstreamconstructorsanchor2)  
  
##  <a name="vclrfoutputfilestreamconstructorsanchor1">Çıkış dosya akışı oluşturucular</a>  
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
  
##  <a name="vclrfoutputstringstreamconstructorsanchor2">Çıkış dizesi akış oluşturucular</a>  
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

