---
description: 'Hakkında daha fazla bilgi edinin: type_index Sınıfı'
title: type_index Sınıfı
ms.date: 11/04/2016
f1_keywords:
- typeindex/std::type_index
helpviewer_keywords:
- type_index class
ms.assetid: db366119-74cb-43e8-aacf-9679e561fa2f
ms.openlocfilehash: 4e9156420811d2712a5b9331d0ece0e7847103e9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142694"
---
# <a name="type_index-class"></a>type_index Sınıfı

`type_index`Sınıfı, bu tür nesneler tarafından dizin oluşturmaya yardımcı olmak için [type_info sınıfa](../cpp/type-info-class.md) yönelik bir işaretçi sarmalar.

sınıf type_index {public: type_index (const type_info& tInfo); const char * Name () const; size_t hash_code () const; bool işleç = = (const type_info& right) const; bool işleci! = (const type_info& right) const; bool işleci< (const type_info& right) const; bool işleci \<=(const type_info& right) const;
   bool operator> (const type_info& right) const; bool işleci>= (const type_info& right) const;};

Oluşturucu öğesine başlatılır `ptr` `&tinfo` .

`name` döndürür `ptr->name()` .

`hash_code` döndürdüğü `ptr->hash_code().`

`operator==` döndürür `*ptr == right.ptr` .

`operator!=` döndürür `!(*this == right)` .

`operator<` döndürür `*ptr->before(*right.ptr)` .

`operator<=` döndürdüğü `!(right < *this).`

`operator>` döndürür `right < *this` .

`operator>=` döndürür `!(*this < right)` .

## <a name="see-also"></a>Ayrıca bkz.

[Çalışma zamanı tür bilgileri](../cpp/run-time-type-information.md)\
[\<typeindex>](../standard-library/typeindex.md)
