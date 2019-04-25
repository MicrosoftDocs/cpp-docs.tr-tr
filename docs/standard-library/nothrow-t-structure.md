---
title: nothrow_t Yapısı
ms.date: 11/04/2016
f1_keywords:
- nothrow_t
helpviewer_keywords:
- nothrow_t class
ms.assetid: dc7d5d42-ed5a-4919-88fe-bbad519b7a1d
ms.openlocfilehash: 2313c436a1fd25149fa7ea72f122a6f323b40028
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62223629"
---
# <a name="nothrowt-structure"></a>nothrow_t Yapısı

Struct operatör işlevi parametre olarak yeni işlevi yerine bir ayırma hatası rapor için bir özel durum null bir işaretçi döndürmesi gerektiğini belirtmek için kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
struct std::nothrow_t {};
```

## <a name="remarks"></a>Açıklamalar

Struct Oluşturucu doğru sürümü seçmek için derleyici yardımcı olur. [nothrow](../standard-library/new-functions.md#nothrow) türünden nesnelerin eşanlamlıdır `std::nothrow_t`.

## <a name="example"></a>Örnek

Bkz: [new işleci](../standard-library/new-operators.md#op_new) ve [new işleci&#91; &#93; ](../standard-library/new-operators.md#op_new_arr) örnekleri için `std::nothrow_t` işlevi parametre olarak kullanılır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yeni >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
