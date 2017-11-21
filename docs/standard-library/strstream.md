---
title: '&lt;strstream&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: <strstream>
dev_langs: C++
helpviewer_keywords: strstream header
ms.assetid: eaa9d0d4-d217-4f28-8a68-9b9ad7b1c0f5
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0487fc2aa09568523c6a7d0bbcf4973beee309ed
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ltstrstreamgt"></a>&lt;strstream&gt;
Ayrılmış bir dizi içinde depolanan sıraları iostreams işlemlerini destekleyen birden fazla sınıf tanımlar `char` nesnesi. Bu tür dizileri kolayca C dizeleri gelen ve giden dönüştürülür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#include <strstream>  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Nesne türü `strstream` ile çalışmak `char` *, C dizeleri olduğu. Kullanım [ \<sstream >](../standard-library/sstream.md) türü nesneleriyle çalışmak için [basic_string](../standard-library/basic-string-class.md).  
  
> [!NOTE]
>  Sınıflarda `<strstream>` kullanım dışı bırakılmıştır. Sınıflarda kullanmayı `<sstream>` yerine.  
  
### <a name="classes"></a>Sınıflar  
  
|||  
|-|-|  
|[strstreambuf sınıfı](../standard-library/strstreambuf-class.md)|Öğeleri depolanan öğe dizisi gelen ve giden iletimini denetleyen bir Akış Arabellek sınıf tanımlar bir `char` dizi nesnesi.|  
|[istrstream sınıfı](../standard-library/istrstream-class.md)|Ayıklama öğelerinin denetleyen bir nesne ve akış arabellek sınıfının kodlanmış nesnelerden sınıfı açıklar [strstreambuf](../standard-library/strstreambuf-class.md).|  
|[ostrstream sınıfı](../standard-library/ostrstream-class.md)|Sınıfı ve kodlanmış nesneleri öğelerinin ekleme denetimlerini bir nesne sınıfının bir akışı arabelleğe açıklar [strstreambuf](../standard-library/strstreambuf-class.md).|  
|[strstream sınıfı](../standard-library/strstream-class.md)|Sınıf ekleme ve çıkarma öğelerinin denetleyen bir nesne sınıfının bir Akış Arabellek kullanarak ve kodlanmış nesneleri tanımlar [strstreambuf](../standard-library/strstreambuf-class.md).|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<strstream >](../standard-library/strstream.md)   
 [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)   
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream programlama](../standard-library/iostream-programming.md)   
 [iostreams kuralları](../standard-library/iostreams-conventions.md)



