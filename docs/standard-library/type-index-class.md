---
title: type_index Sınıfı
ms.date: 11/04/2016
f1_keywords:
- typeindex/std::type_index
helpviewer_keywords:
- type_index class
ms.assetid: db366119-74cb-43e8-aacf-9679e561fa2f
ms.openlocfilehash: 8807a041ab1c6ef47a9c3c12dac2688f121f6cfa
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50650498"
---
# <a name="typeindex-class"></a>type_index Sınıfı

`type_index` Sınıfı için bir işaretçi sarar [type_info sınıfı](../cpp/type-info-class.md) bu tür nesneler tarafından dizin oluşturma işleminde yardımcı olmak için.

type_index sınıfı {public: type_index (const type_info & tinfo); const char *name() const; size_t hash_code() const bool işleci (const type_info & sağa) == const; bool işleci! (const type_info & sağa) = const; bool işleci <(const type_ bilgi & sağa) const; bool işleci\<(const type_info & sağa) = const; bool işleci > (const type_info & sağa) const; bool işleci > (const type_info & sağa) = const;};

Oluşturucu başlatır `ptr` için `&tinfo`.

`name` döndürür `ptr->name()`.

`hash_code` döndürür `ptr->hash_code().`

`operator==` döndürür `*ptr == right.ptr`.

`operator!=` döndürür `!(*this == right)`.

`operator<` döndürür `*ptr->before(*right.ptr)`.

`operator<=` döndürür `!(right < *this).`

`operator>` döndürür `right < *this`.

`operator>=` döndürür `!(*this < right)`.

## <a name="see-also"></a>Ayrıca bkz.

[Çalışma Zamanı Tür Bilgileri](../cpp/run-time-type-information.md)<br/>
[\<typeindex >](../standard-library/typeindex.md)<br/>
