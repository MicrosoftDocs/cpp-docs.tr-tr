---
title: "type_index sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- typeindex/std::type_index
dev_langs:
- C++
helpviewer_keywords:
- type_index class
ms.assetid: db366119-74cb-43e8-aacf-9679e561fa2f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 384a3387110d1de51ec32735ad23280ddc60bf70
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="typeindex-class"></a>type_index Sınıfı
`type_index` Sınıfı için bir işaretçi sarmalar [type_info sınıfı](../cpp/type-info-class.md) bu tür nesneler tarafından dizin yardımcı olmak için.  
  
sınıf type_index {ortak: type_index (const type_info & tinfo); const char *name() const; size_t hash_code() const bool işleci (const type_info & sağa) == const; bool işleci! = (const type_info & sağa) const; bool işleci <(const type_ bilgi & sağa) const; bool işleci\<(const type_info & sağa) = const; bool işleci > (const type_info & sağa) const; bool işleci > = (const type_info & sağa) const;};  
  
 Oluşturucu başlatır `ptr` için `&tinfo`.  
  
 `name` döndürür `ptr->name()`.  
  
 `hash_code` döndürür `ptr->hash_code().`  
  
 `operator==` döndürür `*ptr == right.ptr`.  
  
 `operator!=` döndürür `!(*this == right)`.  
  
 `operator<` döndürür `*ptr->before(*right.ptr)`.  
  
 `operator<=` döndürür `!(right < *this).`  
  
 `operator>` döndürür `right < *this`.  
  
 `operator>=` döndürür `!(*this < right)`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma zamanı türü bilgileri](../cpp/run-time-type-information.md)   
 [\<typeindex>](../standard-library/typeindex.md)



