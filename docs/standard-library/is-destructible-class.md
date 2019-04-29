---
title: is_destructible sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_destructible
helpviewer_keywords:
- is_destructible
ms.assetid: 3bb9b718-1ad5-49ae-93cc-92b93b546b4d
ms.openlocfilehash: 1036a3756a736ee3916ed9fca84aa935bb0ba2cf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62336835"
---
# <a name="isdestructible-class"></a>is_destructible sınıfı

Yıkıcı türü olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_destructible;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Karşılaştırmasının bir örneği true tutan türü *T* tuttuğu yanlış bir yıkıcı, aksi takdirde türüdür. Yıkıcı türleridir başvuru türleri, nesne türleri ve türleri burada bazı türü için `U` eşit `remove_all_extents_t<T>` değerlendirilmemiş işlenen `std::declval<U&>.~U()` doğru oluşturulmamış. Eksik türler dahil olmak üzere diğer türleri **void**ve işlev türlerini, yıkıcı türler değildir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
