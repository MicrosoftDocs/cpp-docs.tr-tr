---
title: "ctype_base sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: locale/std::ctype_base
dev_langs: C++
helpviewer_keywords: ctype_base class
ms.assetid: ccffe891-d7ab-4d22-baf8-8eb6d438a96d
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: dc45c762c4abe772164f2db365361b9f2277a260
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ctypebase-class"></a>ctype_base Sınıfı
Sınıf şablonu sınıfı modelleri için temel bir sınıf olarak hizmet veren [ctype](../standard-library/ctype-class.md). Karakterleri tek tek veya aralığın tamamında sınıflandırmak veya sınamak için kullanılan numaralandırma türleri tanımlamak için kullanılan ctype sınıfı için temel sınıf.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
struct ctype_base : public locale::facet
{
    enum
 {
    alnum,
 alpha,
    cntrl,
 digit,
    graph,
 lower,
    print,
 punct,
    space,
 upper,
    xdigit
 };
    typedef short mask;
    ctype_base(
 size_t _Refs = 0);

 ~ctype_base();

};
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bir numaralandırma maskesi tanımlar. Her numaralandırma sabiti karakterleri, sınıflandırmak için farklı bir şekilde üstbilgisinde bildirilen benzer adları olan işlevler tarafından tanımlandığı şekilde belirtir \<ctype.h >. Sabitler şunlardır:  
  
- **alan** (işlevi [isspace](../standard-library/locale-functions.md#isspace))  
  
- **Yazdırma** (işlevi [isprint](../standard-library/locale-functions.md#isprint))  
  
- **Dnt** (işlevi [iscntrl](../standard-library/locale-functions.md#iscntrl))  
  
- **üst** (işlevi [isupper](../standard-library/locale-functions.md#isupper))  
  
- **daha düşük** (işlevi [islower](../standard-library/locale-functions.md#islower))  
  
- **basamak** (işlevi [isdigit](../standard-library/locale-functions.md#isdigit))  
  
- **noktalama işareti** (işlevi [ispunct](../standard-library/locale-functions.md#ispunct))  
  
- **xdigit** (işlevi [isxdigit](../standard-library/locale-functions.md#isxdigit))  
  
- **Alpha** (işlevi [isalpha](../standard-library/locale-functions.md#isalpha))  
  
- **alnum** (işlevi [isalnum](../standard-library/locale-functions.md#isalnum))  
  
- **Grafik** (işlevi [isgraph](../standard-library/locale-functions.md#isgraph))  
  
 Bu sabitleri ORing tarafından sınıflandırmaları bileşimini ayırt edebilirsiniz. Özellikle, her zaman, true olan **alnum** == ( **alfa** &#124; **basamaklı** \) ve **grafik** \= \= \( **alnum** &#124; **noktalama işareti**).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<yerel ayar >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)



