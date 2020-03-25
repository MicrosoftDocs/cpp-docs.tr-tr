---
title: _com_ptr_t::Attach
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::Attach
helpviewer_keywords:
- COM interfaces, attach pointer
- Attach method [C++]
ms.assetid: 94c18e0a-06be-4ca7-bdaf-cd54ec0a645e
ms.openlocfilehash: 870e3580ed23ce994d832f7c59b951680d725e41
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180504"
---
# <a name="_com_ptr_tattach"></a>_com_ptr_t::Attach

**Microsoft 'a özgü**

Bu akıllı işaretçinin türünün ham arabirim işaretçisini kapsüller.

## <a name="syntax"></a>Sözdizimi

```
void Attach( Interface* pInterface ) throw( );
void Attach( Interface* pInterface, bool fAddRef ) throw( );
```

#### <a name="parameters"></a>Parametreler

*Pınterface*<br/>
Ham arabirim işaretçisi.

*fAddRef*<br/>
DOĞRU ise `AddRef` çağrılır. YANLıŞ ise `_com_ptr_t` nesnesi, `AddRef`çağrılmadan ham arabirim işaretçisinin sahipliğini alır.

## <a name="remarks"></a>Açıklamalar

- **Attach (**  *pınterface*  **)** `AddRef` çağrılmadı. Arabirimin sahipliği bu `_com_ptr_t` nesnesine geçirilir. `Release`, daha önce kapsüllenmiş işaretçinin başvuru sayısını azaltmak için çağrılır.

- **Attach (**  *pınterface* **,**  *fAddRef*  **)** *FAddRef* true ise, kapsüllenmiş arabirim işaretçisinin başvuru sayısını artırmak için `AddRef` çağırılır. *FAddRef* yanlış ise, bu `_com_ptr_t` nesnesi, `AddRef`çağrılmadan ham arabirim işaretçisinin sahipliğini alır. `Release`, daha önce kapsüllenmiş işaretçinin başvuru sayısını azaltmak için çağrılır.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_ptr_t Sınıfı](../cpp/com-ptr-t-class.md)
