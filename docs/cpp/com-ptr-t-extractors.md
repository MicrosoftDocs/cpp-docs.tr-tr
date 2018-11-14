---
title: _com_ptr_t Ayıklayıcıları
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::operatorInterface&
- _com_ptr_t::operatorbool
- _com_ptr_t::operator->
- _com_ptr_t::operator*
helpviewer_keywords:
- operator Interface& [C++]
- '* operator [C++], with specific objects'
- operator& [C++]
- operator* [C++]
- -> operator [C++], with specific objects
- '& operator [C++], with specific objects'
- operator Interface* [C++]
- operator * [C++]
- operator->
- operator bool
- extractors, _com_ptr_t class
- extractors [C++]
ms.assetid: 194b9e0e-123c-49ff-a187-0a7fcd68145a
ms.openlocfilehash: bac1f9a139d2fb0092ef0869587ae8b54342fe82
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51330326"
---
# <a name="comptrt-extractors"></a>_com_ptr_t Ayıklayıcıları

**Microsoft'a özgü**

Kapsüllenmiş COM arabirimi işaretçisini ayıklayın.

## <a name="syntax"></a>Sözdizimi

```
operator Interface*( ) const throw( );
operator Interface&( ) const;
Interface& operator*( ) const;
Interface* operator->( ) const;
Interface** operator&( ) throw( );
operator bool( ) const throw( );
```

## <a name="remarks"></a>Açıklamalar

- **işleç arabirimi** <strong>\*</strong> NULL olabilecek kapsüllenmiş arabirim işaretçisini döndürür.

- **işleç arabirimi &** kapsüllenmiş arabirim işaretçisini bir başvuru döndürür ve işaretçi NULL ise, bir hata verir.

- **İşleç** <strong>\*</strong> akıllı işaretçi nesnesinin gibi başvurusu kaldırıldığında gerçek bir kapsüllenmiş arabirim davranmasını sağlar.

- **operator ->** akıllı işaretçi nesnesinin gibi başvurusu kaldırıldığında gerçek bir kapsüllenmiş arabirim davranmasını sağlar.

- **işleç &** NULL'ile değiştirerek, herhangi bir kapsüllenmiş arabirim işaretçisini serbest bırakır ve kapsüllenmiş işaretçiye adresini döndürür. Bu akıllı işaretçinin sahip bir işleve adres tarafından geçirilecek sağlar bir *kullanıma* bir arabirim işaretçisi döndürmesini parametresi.

- **işleç bool değeri** akıllı işaretçi nesnesinin koşullu ifadede kullanılmasını sağlar. Bu işleç, işaretçi NULL değilse, TRUE döndürür.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_ptr_t Sınıfı](../cpp/com-ptr-t-class.md)