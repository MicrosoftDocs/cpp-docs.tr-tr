---
title: _com_ptr_t::Attach
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::Attach
helpviewer_keywords:
- COM interfaces, attach pointer
- Attach method [C++]
ms.assetid: 94c18e0a-06be-4ca7-bdaf-cd54ec0a645e
ms.openlocfilehash: 4b4b7a21d12cc645c486dd93d555510c1e716563
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154896"
---
# <a name="comptrtattach"></a>_com_ptr_t::Attach

**Microsoft'a özgü**

Bu akıllı işaretçinin türü ham arabirim işaretçisi kapsüller.

## <a name="syntax"></a>Sözdizimi

```
void Attach( Interface* pInterface ) throw( );
void Attach( Interface* pInterface, bool fAddRef ) throw( );
```

#### <a name="parameters"></a>Parametreler

*pInterface*<br/>
Ham arabirim işaretçisi.

*fAddRef*<br/>
TRUE ise, `AddRef` çağrılır. FALSE ise `_com_ptr_t` Nesne sahipliği çağırmadan ham arabirim işaretçisi alır `AddRef`.

## <a name="remarks"></a>Açıklamalar

- **Ekleme (***pInterface***)** `AddRef` çağrılmaz. Arabirim sahipliğinin için geçirilen `_com_ptr_t` nesne. `Release` daha önce Kapsüllenen işaretçi için başvuru sayısını azaltma için çağrılır.

- **Ekleme (***pInterface* **,***fAddRef***)** varsa *fAddRef* TRUE ise `AddRef`kapsüllenmiş arabirim işaretçisini için başvuru sayısını artırmak için çağrılır. Varsa *fAddRef* yanlış, bu `_com_ptr_t` Nesne sahipliği çağırmadan ham arabirim işaretçisi alır `AddRef`. `Release` daha önce Kapsüllenen işaretçi için başvuru sayısını azaltma için çağrılır.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_ptr_t Sınıfı](../cpp/com-ptr-t-class.md)