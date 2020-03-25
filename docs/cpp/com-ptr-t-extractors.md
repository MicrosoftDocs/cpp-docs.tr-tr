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
ms.openlocfilehash: 31ac39104c041d1d119f6cd06de5f9c4a620dac0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190033"
---
# <a name="_com_ptr_t-extractors"></a>_com_ptr_t Ayıklayıcıları

**Microsoft 'a özgü**

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

- **Işleç arabirimi** <strong>\*</strong> , kapsüllenmiş arabirim IŞARETÇISINI döndürür ve bu null olabilir.

- **operatör arabirimi &** Kapsüllenmiş arabirim işaretçisine bir başvuru döndürür ve işaretçi NULL ise bir hata verir.

- **işleç** <strong>\*</strong> , bir akıllı işaretçi nesnesinin, başvura başvurulması sırasında gerçek kapsüllenmiş arabirimiymiş gibi davranmasını sağlar.

- **operator->** Bir akıllı işaretçi nesnesinin, başvura başvurulması halinde gerçek kapsüllenmiş arabirimiymiş gibi davranmasını sağlar.

- **işleç &** Herhangi bir kapsüllenmiş arabirim işaretçisini serbest bırakır, NULL ile değiştirir ve kapsüllenmiş işaretçinin adresini döndürür. Bu, akıllı işaretçinin, bir arabirim işaretçisi döndürdüğü bir *Out* parametresi olan bir işleve adres ile geçirilmesini sağlar.

- **işleç bool** Bir koşullu ifadede akıllı işaretçi nesnesinin kullanılmasına izin verir. İşaretçi NULL değilse bu işleç TRUE değerini döndürür.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_ptr_t Sınıfı](../cpp/com-ptr-t-class.md)
