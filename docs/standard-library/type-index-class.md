---
title: type_index Sınıfı
ms.date: 11/04/2016
f1_keywords:
- typeindex/std::type_index
helpviewer_keywords:
- type_index class
ms.assetid: db366119-74cb-43e8-aacf-9679e561fa2f
ms.openlocfilehash: b30c9719957b9ffc5f3ce17692eb90c1b266ae0f
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447050"
---
# <a name="typeindex-class"></a>type_index Sınıfı

Sınıfı `type_index` , bu tür nesneler tarafından dizin oluşturmaya yardımcı olmak için bir işaretçi [type_info sınıfına](../cpp/type-info-class.md) kaydırılır.

Class type_index {public: type_index (const type_info & tInfo); const char * Name () const; size_t hash_code () const; bool işleç = = (const type_info & Right) const; bool işleci! = (const type_info & Right) const; bool işleci < (const type_ bilgi & Right) const; bool işleç\<= (const type_info & Right) const; bool işleci > (const type_info & Right) const; bool işleci > = (const type_info & Right) const;};

Oluşturucu öğesine `ptr` `&tinfo`başlatılır.

`name`döndürür `ptr->name()`.

`hash_code`döndürdüğü`ptr->hash_code().`

`operator==`döndürür `*ptr == right.ptr`.

`operator!=`döndürür `!(*this == right)`.

`operator<`döndürür `*ptr->before(*right.ptr)`.

`operator<=`döndürdüğü`!(right < *this).`

`operator>`döndürür `right < *this`.

`operator>=`döndürür `!(*this < right)`.

## <a name="see-also"></a>Ayrıca bkz.

[Çalışma zamanı tür bilgileri](../cpp/run-time-type-information.md)\
[\<typeındex >](../standard-library/typeindex.md)
