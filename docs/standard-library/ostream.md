---
title: '&lt;ostream&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <ostream>
- ostream/std::<ostream>
- std::<ostream>
dev_langs: C++
helpviewer_keywords: ostream header
ms.assetid: 90c3b6fb-57cd-4ae7-99b8-8512f24a67d2
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 64af7a36a243fd633af5365b9c2c54b52088ed9d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ltostreamgt"></a>&lt;ostream&gt;
Şablon sınıfı tanımlayan [basic_ostream](../standard-library/basic-ostream-class.md), iostreams eklemeler aracılık. Üstbilgi ayrıca çeşitli ilgili manipülatörleri tanımlar. (Bu başlığı, genellikle başka iostreams üstbilgilerinin eklenmiştir. Nadiren doğrudan içermesi gerekir.)  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#include <ostream>  
  
```  
  
### <a name="typedefs"></a>Tür tanımları  
  
|||  
|-|-|  
|[ostream](../standard-library/ostream-typedefs.md#ostream)|Bir türden oluşturur `basic_ostream` üzerinde özelleştirilmiş `char` ve `char_traits` üzerinde özel `char`.|  
|[wostream](../standard-library/ostream-typedefs.md#wostream)|Bir türden oluşturur `basic_ostream` üzerinde özelleştirilmiş `wchar_t` ve `char_traits` üzerinde özel `wchar_t`.|  
  
### <a name="manipulators"></a>Manipülatörleri  
  
|||  
|-|-|  
|[endl](../standard-library/ostream-functions.md#endl)|Bir satır sonlandırır ve arabelleği temizler.|  
|[sona erer](../standard-library/ostream-functions.md#ends)|Bir dize sonlandırır.|  
|[Temizleme](../standard-library/ostream-functions.md#flush)|Arabelleği temizler.|  
|[değiştirme](../standard-library/ostream-functions.md#swap)|Sol değerlerini alış verişleri `basic_ostream` parametresi bu hakkı nesne `basic_ostream` parametre nesnesi.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[işleç <<](../standard-library/ostream-operators.md#op_lt_lt)|Çeşitli türleri akışa yazar.|  
  
### <a name="classes"></a>Sınıflar  
  
|||  
|-|-|  
|[basic_ostream](../standard-library/basic-ostream-class.md)|Şablon sınıfı öğelerinin ekleme denetimlerini bir nesne ve kodlanmış nesneleri akışı arabelleğe açıklar.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)   
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream programlama](../standard-library/iostream-programming.md)   
 [iostreams kuralları](../standard-library/iostreams-conventions.md)



