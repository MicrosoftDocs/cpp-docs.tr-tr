---
title: _com_ptr_t::Attach
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::Attach
helpviewer_keywords:
- COM interfaces, attach pointer
- Attach method [C++]
ms.assetid: 94c18e0a-06be-4ca7-bdaf-cd54ec0a645e
ms.openlocfilehash: 057d784bb495aefaeec1b86697a7421f6464cbd7
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81745075"
---
# <a name="_com_ptr_tattach"></a>_com_ptr_t::Attach

**Microsoft'a Özgü**

Bu akıllı işaretçinin türüne ait ham arabirim işaretçisini kapsüller.

## <a name="syntax"></a>Sözdizimi

```cpp
void Attach( Interface* pInterface ) throw( );
void Attach( Interface* pInterface, bool fAddRef ) throw( );
```

#### <a name="parameters"></a>Parametreler

*pInterface*<br/>
Ham arabirim işaretçisi.

*fAddRef*<br/>
Doğru ise, o `AddRef` zaman denir. FALSE ise, `_com_ptr_t` nesne çağırmadan `AddRef`ham arabirim işaretçisinin sahipliğini alır.

## <a name="remarks"></a>Açıklamalar

- **Ekle***(pInterface)***)** `AddRef` çağrılmaz.     Arabirimin sahipliği bu `_com_ptr_t` nesneye aktarılır. `Release`daha önce kapsüllenmiş işaretçi için başvuru sayısını ertelemek için çağrılır.

- **Ekle(**  *pInterface* **,**  *fAddRef*  **)** *fAddRef* TRUE ise, `AddRef` kapsüllü arabirim işaretçisi için başvuru sayısını arttırmak için çağrılır. *fAddRef* FALSE ise, `_com_ptr_t` bu nesne çağırmadan `AddRef`ham arabirim işaretçisinin sahipliğini alır. `Release`daha önce kapsüllenmiş işaretçi için başvuru sayısını ertelemek için çağrılır.

**END Microsoft Özel**

## <a name="see-also"></a>Ayrıca bkz.

[_com_ptr_t Sınıfı](../cpp/com-ptr-t-class.md)
