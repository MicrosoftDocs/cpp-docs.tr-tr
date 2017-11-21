---
title: "forward_iterator_tag yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: xutility/std::forward_iterator_tag
dev_langs: C++
helpviewer_keywords:
- forward_iterator_tag struct
- forward_iterator_tag class
ms.assetid: 68b633ac-b135-4e9e-837d-14248a262ec5
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2a6d48940faf4645421a863411058ebfce1949aa
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="forwarditeratortag-struct"></a>forward_iterator_tag Yapısı
Dönüş türü için sağlayan bir sınıf **iterator_category** iletme yineleyici gösteren işlev.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
struct forward_iterator_tag    : public input_iterator_tag {};
```  
  
## <a name="remarks"></a>Açıklamalar  
 Kategori etiket sınıflarını algoritması seçimi için etiketler derleme gibi kullanılır. Derleme zamanında en verimli algoritması kullanabilmeleri ne yineleyici bağımsız değişkeni en belirli kategorisi olduğunu bulmak şablon işlevi gerekir. Her yineleyici türü için `Iterator`, `iterator_traits` <  `Iterator` >  **:: iterator_category** yineleyici'nin davranışını tanımlar en özel kategori etiketi olarak tanımlanması gerekir.  
  
 Aynı türdür **yineleyici** \< **Iter**> **:: iterator_category** zaman **Iter** açıklayan bir bir iletme yineleyici hizmet verebilir nesnesi.  
  
## <a name="example"></a>Örnek  
 Bkz: [iterator_traits](../standard-library/iterator-traits-struct.md) veya [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md) nasıl kullanılacağına ilişkin bir örnek **iterator_tag**s.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<yineleyici >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [input_iterator_tag yapısı](../standard-library/input-iterator-tag-struct.md)   
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)



