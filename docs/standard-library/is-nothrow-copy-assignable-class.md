---
title: is_nothrow_copy_assignable sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::is_nothrow_copy_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_copy_assignable
ms.assetid: baa8abd6-4f53-489f-abba-8d5d5c53bbbc
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 47cfa4d49dce7f7503c9e707d3a2f8787b4f53a3
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="isnothrowcopyassignable-class"></a>is_nothrow_copy_assignable Sınıfı

Derleyiciye değil throw bilinen bir kopya atama işleci türüne sahip olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_nothrow_copy_assignable;
```

### <a name="parameters"></a>Parametreler

`T` Sorgulanacak türü.

## <a name="remarks"></a>Açıklamalar

Türü koşulu örneği önerilebilir türü için doğru kalıp `T` burada `is_nothrow_assignable<T&, const T&>` false tuttuğu true; Aksi halde tutar.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_nothrow_assignable Sınıfı](../standard-library/is-nothrow-assignable-class.md)<br/>
