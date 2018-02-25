---
title: "bidirectional_iterator_tag yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- xutility/std::bidirectional_iterator_tag
dev_langs:
- C++
helpviewer_keywords:
- bidirectional_iterator_tag class
- bidirectional_iterator_tag struct
ms.assetid: 9ac06066-b8ae-44b6-bee4-b05855f6a31a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 40eb496203b43f7e71c0ec0b69b561c478e83092
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="bidirectionaliteratortag-struct"></a>bidirectional_iterator_tag Yapısı
Dönüş türü için sağlayan bir sınıf **iterator_category** çift yönlü yineleyici temsil eden bir işlev.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
struct bidirectional_iterator_tag    : public forward_iterator_tag {};
```  
  
## <a name="remarks"></a>Açıklamalar  
 Kategori etiket sınıflarını algoritması seçimi için etiketler derleme gibi kullanılır. Derleme zamanında en verimli algoritması kullanabilmeleri şablon işlevi yineleyici bağımsız değişkeni, en belirgin kategorisini bulması gerekir. Her yineleyici türü için `Iterator`, `iterator_traits` <  `Iterator`>:: **iterator_category** yineleyici'nin davranışını tanımlar en özel kategori etiketi olarak tanımlanması gerekir.  
  
 Aynı türdür **yineleyici** \< **Iter**>:: **iterator_category** zaman **Iter** için bir nesne açıklar çift yönlü yineleyici görev yapar.  
  
## <a name="example"></a>Örnek  
 Bkz: [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md) nasıl kullanılacağına ilişkin bir örnek `bidirectional_iterator_tag`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<yineleyici >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [forward_iterator_tag yapısı](../standard-library/forward-iterator-tag-struct.md)   
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)



