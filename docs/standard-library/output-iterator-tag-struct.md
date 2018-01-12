---
title: "output_iterator_tag yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: xutility/std::output_iterator_tag
dev_langs: C++
helpviewer_keywords:
- output_iterator_tag class
- output_iterator_tag struct
ms.assetid: c23a4331-b069-4fa0-9c3a-1c9be7095553
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a45dd68f5788244c7d7f1ea72b22af5f96c1a0d8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="outputiteratortag-struct"></a>output_iterator_tag Yapısı
Dönüş türü için sağlayan bir sınıf **iterator_category** çıkış yineleyici temsil eden bir işlev.  
  
## <a name="syntax"></a>Sözdizimi  
  
Yapı output_iterator_tag {};  
  
## <a name="remarks"></a>Açıklamalar  
 Kategori etiket sınıflarını algoritması seçimi için etiketler derleme gibi kullanılır. Derleme zamanında en verimli algoritması kullanabilmeleri en özel kategori yineleyici bağımsız değişkeninin değerini bulmak şablon işlevi gerekir. Her yineleyici türü için `Iterator`, `iterator_traits` <  `Iterator` >  **:: iterator_category** yineleyici'nin davranışını tanımlar en özel kategori etiketi olarak tanımlanması gerekir.  
  
 Aynı türdür **yineleyici** \< **Iter**> **:: iterator_category** zaman **Iter** açıklayan bir bir çıkış yineleyici hizmet verebilir nesnesi.  
  
 Bu etiket üzerinde parametreli değil `value_type` veya `difference_type` yineleyici için etiketlerle diğer yineleyici gibi çıktı yineleyiciler ya da olmadığı için bir `value_type` veya `difference_type`.  
  
## <a name="example"></a>Örnek  
 Bkz: [iterator_traits](../standard-library/iterator-traits-struct.md) veya [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md) nasıl kullanılacağına ilişkin bir örnek **iterator_tag**s.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<yineleyici >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)



