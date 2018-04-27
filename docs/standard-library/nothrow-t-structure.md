---
title: nothrow_t yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- nothrow_t
dev_langs:
- C++
helpviewer_keywords:
- nothrow_t class
ms.assetid: dc7d5d42-ed5a-4919-88fe-bbad519b7a1d
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 28ed3502c60b53ac0f4f3f532eadad6f4ef61d17
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
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
