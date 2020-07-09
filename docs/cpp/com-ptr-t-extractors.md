---
title: _com_ptr_t Ayıklayıcıları
description: _Com_ptr_t sınıfı için ayıklama işleçlerini açıklar.
ms.date: 07/07/2020
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
ms.openlocfilehash: e7b06bb11ab34a1a1a7f6fab98d177821f60b20c
ms.sourcegitcommit: e17cc8a478b51739d67304d7d82422967b35f716
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/08/2020
ms.locfileid: "86127849"
---
# <a name="_com_ptr_t-extractors"></a>`_com_ptr_t`Ayıklayıcıları

**Microsoft'a özgü**

Kapsüllenmiş COM arabirimi işaretçisini ayıklayın.

## <a name="syntax"></a>Sözdizimi

```c++
operator Interface*( ) const throw( );
operator Interface&( ) const;
Interface& operator*( ) const;
Interface* operator->( ) const;
Interface** operator&( ) throw( );
operator bool( ) const throw( );
```

## <a name="remarks"></a>Açıklamalar

- **`operator Interface*`** NULL olabilecek kapsüllenmiş arabirim işaretçisini döndürür.

- **`operator Interface&`** Kapsüllenmiş arabirim işaretçisine bir başvuru döndürür ve işaretçi NULL ise bir hata verir.

- **`operator*`** Bir akıllı işaretçi nesnesinin, başvura başvurulması halinde gerçek kapsüllenmiş arabirimiymiş gibi davranmasını sağlar.

- **`operator->`** Bir akıllı işaretçi nesnesinin, başvura başvurulması halinde gerçek kapsüllenmiş arabirimiymiş gibi davranmasını sağlar.

- **`operator&`** Herhangi bir kapsüllenmiş arabirim işaretçisini serbest bırakır, NULL ile değiştirir ve kapsüllenmiş işaretçinin adresini döndürür. Bu işleç, bir arabirim işaretçisi döndürdüğü bir *Out* parametresi olan bir işleve adrese göre akıllı işaretçiyi geçirmenize olanak sağlar.

- **`operator bool`** Bir koşullu ifadede akıllı işaretçi nesnesinin kullanılmasına izin verir. İşaretçi NULL değilse bu işleç TRUE değerini döndürür.

  > [!NOTE]
  > **`operator bool`** Olarak bildirildiği **`explicit`** `_com_ptr_t` için, **`bool`** herhangi bir skalar türe dönüştürülebilir olan öğesine örtük olarak dönüştürülebilir. Bu, kodunuzda beklenmedik sonuçlara sahip olabilir. Bu dönüştürmenin istenmeden kullanımını engellemek için [derleyici uyarısını etkinleştirin (düzey 4) C4800](../error-messages/compiler-warnings/compiler-warning-level-3-c4800.md) .

## <a name="see-also"></a>Ayrıca bkz.

[_com_ptr_t sınıfı](../cpp/com-ptr-t-class.md)
