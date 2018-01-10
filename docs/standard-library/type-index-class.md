---
title: "type_index sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: typeindex/std::type_index
dev_langs: C++
helpviewer_keywords: type_index class
ms.assetid: db366119-74cb-43e8-aacf-9679e561fa2f
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e27a626a7371c0358f05c49b33d0a9c1a019e72e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="typeindex-class"></a>type_index Sınıfı
`type_index` Sınıfı için bir işaretçi sarmalar [type_info sınıfı](../cpp/type-info-class.md) bu tür nesneler tarafından dizin yardımcı olmak için.  
  
sınıf type_index {ortak: type_index (const type_info & tinfo); const char *name() const; size_t hash_code() const bool işleci (const type_info & sağa) == const; bool işleci! = (const type_info & sağa) const; bool işleci <(const type_ bilgi & sağa) const; bool işleci\<(const type_info & sağa) = const; bool işleci > (const type_info & sağa) const; bool işleci > = (const type_info & sağa) const;};  
  
 Oluşturucu başlatır `ptr` için `&tinfo`.  
  
 `name`döndürür `ptr->name()`.  
  
 `hash_code`döndürür`ptr->hash_code().`  
  
 `operator==`döndürür `*ptr == right.ptr`.  
  
 `operator!=`döndürür `!(*this == right)`.  
  
 `operator<`döndürür `*ptr->before(*right.ptr)`.  
  
 `operator<=`döndürür`!(right < *this).`  
  
 `operator>`döndürür `right < *this`.  
  
 `operator>=`döndürür `!(*this < right)`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma zamanı türü bilgileri](../cpp/run-time-type-information.md)   
 [\<typeindex >](../standard-library/typeindex.md)



