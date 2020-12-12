---
description: 'Hakkında daha fazla bilgi edinin: _com_ptr_t::D etach'
title: _com_ptr_t::Detach
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::Detach
helpviewer_keywords:
- Detach method [C++]
ms.assetid: 0652053e-af37-44e9-a278-2522212ebfed
ms.openlocfilehash: ec2a18a04b8c32e373225235fd0d6f520e768af0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295516"
---
# <a name="_com_ptr_tdetach"></a>_com_ptr_t::Detach

**Microsoft'a Özgü**

Kapsüllenmiş arabirim işaretçisini ayıklar ve döndürür.

## <a name="syntax"></a>Syntax

```
Interface* Detach( ) throw( );
```

## <a name="remarks"></a>Açıklamalar

Kapsüllenmiş arabirim işaretçisini ayıklar ve döndürür ve sonra kapsüllenmiş işaretçi depolama alanını NULL olarak temizler. Bu, arabirim işaretçisini kapsüllemeden kaldırır. Bu, `Release` döndürülen arabirim işaretçisi üzerinde arama yapmak için kullanılır.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_ptr_t sınıfı](../cpp/com-ptr-t-class.md)
