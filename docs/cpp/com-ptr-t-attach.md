---
description: ': _Com_ptr_t:: Attach hakkında daha fazla bilgi edinin'
title: _com_ptr_t::Attach
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::Attach
helpviewer_keywords:
- COM interfaces, attach pointer
- Attach method [C++]
ms.assetid: 94c18e0a-06be-4ca7-bdaf-cd54ec0a645e
ms.openlocfilehash: 5b27a4bd6572f2f1429766328c01f377672ee11d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295659"
---
# <a name="_com_ptr_tattach"></a>_com_ptr_t::Attach

**Microsoft'a Özgü**

Bu akıllı işaretçinin türünün ham arabirim işaretçisini kapsüller.

## <a name="syntax"></a>Sözdizimi

```cpp
void Attach( Interface* pInterface ) throw( );
void Attach( Interface* pInterface, bool fAddRef ) throw( );
```

#### <a name="parameters"></a>Parametreler

*Pınterface*<br/>
Ham arabirim işaretçisi.

*fAddRef*<br/>
Varsa **`true`** , `AddRef` çağrılır. Eğer ise **`false`** , nesnesi, `_com_ptr_t` çağrısı yapmadan ham arabirim işaretçisinin sahipliğini alır `AddRef` .

## <a name="remarks"></a>Açıklamalar

- **Attach (**  *pınterface*  **)** `AddRef` çağrılmadı. Arabirimin sahipliği bu `_com_ptr_t` nesneye geçirilir. `Release` , daha önce kapsüllenmiş işaretçinin başvuru sayısını azaltmak için çağırılır.

- **Attach (**  *pınterface* **,**  *fAddRef*  **)** *FAddRef* ise **`true`** , `AddRef` kapsüllenmiş arabirim işaretçisinin başvuru sayısını artırmak için çağırılır. *FAddRef* ise **`false`** , bu `_com_ptr_t` nesne çağrı yapmadan ham arabirim işaretçisinin sahipliğini alır `AddRef` . `Release` , daha önce kapsüllenmiş işaretçinin başvuru sayısını azaltmak için çağırılır.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_ptr_t sınıfı](../cpp/com-ptr-t-class.md)
