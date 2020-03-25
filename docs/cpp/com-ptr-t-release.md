---
title: _com_ptr_t::Release
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t.Release
- _com_ptr_t::Release
helpviewer_keywords:
- Release method [C++]
ms.assetid: db448b34-0efa-4f02-b701-ad1ca3ae6ca5
ms.openlocfilehash: f455e855e782a939e79898ee46e445f65d25d37a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80170598"
---
# <a name="_com_ptr_trelease"></a>_com_ptr_t::Release

**Microsoft 'a özgü**

Kapsüllenmiş arabirim işaretçisindeki `IUnknown` **serbest bırakma** işlevini çağırır.

## <a name="syntax"></a>Sözdizimi

```
void Release( );
```

## <a name="remarks"></a>Açıklamalar

Bu arabirim işaretçisi NULL ise, kapsüllenmiş arabirim İşaretçisinde `IUnknown::Release` çağırır, `E_POINTER` hatasını ortaya koyar.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_ptr_t Sınıfı](../cpp/com-ptr-t-class.md)
