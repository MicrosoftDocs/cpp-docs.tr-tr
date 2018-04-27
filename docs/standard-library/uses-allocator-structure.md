---
title: uses_allocator yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- future/std::uses_allocator
dev_langs:
- C++
ms.assetid: c418f002-62e9-4806-b70c-41c663cae583
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c053fa3b1bd653864ed440def9f7049da519d093
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="usesallocator-structure"></a>uses_allocator Yapısı

Özelleştirmeleri her zaman true tutun.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty, class Alloc>
struct uses_allocator<promise<Ty>, Alloc> : true_type;
template <class Ty, class Alloc>
struct uses_allocator<packaged_task<Ty>, Alloc> : true_type;
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<gelecekteki >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<sonraki >](../standard-library/future.md)<br/>
