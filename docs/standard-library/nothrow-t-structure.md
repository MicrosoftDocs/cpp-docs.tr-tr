---
title: nothrow_t yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- nothrow_t
dev_langs:
- C++
helpviewer_keywords:
- nothrow_t class
ms.assetid: dc7d5d42-ed5a-4919-88fe-bbad519b7a1d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7a34d9b4e87e2a9036afe7dc12b85fa6d4354209
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="nothrowt-structure"></a>nothrow_t Yapısı

Yapı işleci işlevi parametre olarak yeni işlevi yerine bir ayırma hatası rapor için bir özel durum null işaretçi döndürmesi gerektiğini belirtmek için kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
struct std::nothrow_t {};
```

## <a name="remarks"></a>Açıklamalar

Yapı Oluşturucusu doğru sürümü seçmek için derleyici yardımcı olur. [nothrow](../standard-library/new-functions.md#nothrow) türündeki nesneler için eş anlamlı olduğundan `std::nothrow_t`.

## <a name="example"></a>Örnek

Bkz: [new işleci](../standard-library/new-operators.md#op_new) ve [new işleci&#91; &#93; ](../standard-library/new-operators.md#op_new_arr) örnekleri için `std::nothrow_t` işlevi parametre olarak kullanılır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yeni >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
