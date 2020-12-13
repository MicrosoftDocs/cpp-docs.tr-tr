---
description: ': _Com_ptr_t:: Release hakkında daha fazla bilgi edinin'
title: _com_ptr_t::Release
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t.Release
- _com_ptr_t::Release
helpviewer_keywords:
- Release method [C++]
ms.assetid: db448b34-0efa-4f02-b701-ad1ca3ae6ca5
ms.openlocfilehash: a1b81295ab249b1826ea6d373f782d91765df3b7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344724"
---
# <a name="_com_ptr_trelease"></a>_com_ptr_t::Release

**Microsoft'a Özgü**

Kapsüllenmiş arabirim işaretçisindeki **yayın** üye işlevini çağırır `IUnknown` .

## <a name="syntax"></a>Syntax

```cpp
void Release( );
```

## <a name="remarks"></a>Açıklamalar

`IUnknown::Release` `E_POINTER` Bu ARABIRIM işaretçisi null ise, kapsüllenmiş arabirim işaretçisindeki çağrılar bir hata ortaya koyar.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_ptr_t sınıfı](../cpp/com-ptr-t-class.md)
