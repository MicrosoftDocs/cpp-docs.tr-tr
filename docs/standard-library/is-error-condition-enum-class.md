---
title: is_error_condition_enum sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- system_error/std::is_error_condition_enum
dev_langs:
- C++
helpviewer_keywords:
- is_error_condition_enum class
ms.assetid: 752bb87a-c61c-4304-9254-5aaf228b59c0
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 43959823df01187961fbb9e113160b026e4d31d4
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="iserrorconditionenum-class"></a>is_error_condition_enum Sınıfı

İçin test türü koşulu temsil eden [error_condition](../standard-library/error-condition-class.md) numaralandırması.

## <a name="syntax"></a>Sözdizimi

```cpp
template <_Enum>
class is_error_condition_enum;
```

## <a name="remarks"></a>Açıklamalar

Bu örneği [türü koşulu](../standard-library/type-traits.md) ise true ayrı tutma türü `_Enum` bir numaralandırma değeri türünde bir nesne depolamak için uygun olan `error_condition`.

Bu türü kullanıcı tanımlı türler için özelleştirmeleri eklemek için izin verilir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<system_error >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[<system_error>](../standard-library/system-error.md)<br/>
