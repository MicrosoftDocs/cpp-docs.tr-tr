---
title: _com_ptr_t::Attach | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::Attach
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, attach pointer
- Attach method [C++]
ms.assetid: 94c18e0a-06be-4ca7-bdaf-cd54ec0a645e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f8e982ebd9a09d4dfcb5e4b5e150b42a1e8d5c75
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37948192"
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
 *pInterface*  
 Ham arabirim işaretçisi.  
  
 *fAddRef*  
 TRUE ise, `AddRef` çağrılır. FALSE ise `_com_ptr_t` Nesne sahipliği çağırmadan ham arabirim işaretçisi alır `AddRef`.  
  
## <a name="remarks"></a>Açıklamalar  
  
-   **Ekleme (***pInterface***)** `AddRef` çağrılmaz.     Arabirim sahipliğinin için geçirilen `_com_ptr_t` nesne. `Release` daha önce Kapsüllenen işaretçi için başvuru sayısını azaltma için çağrılır.  
  
-   **Ekleme (***pInterface* **,***fAddRef***)** varsa *fAddRef* TRUE ise `AddRef`kapsüllenmiş arabirim işaretçisini için başvuru sayısını artırmak için çağrılır.       Varsa *fAddRef* yanlış, bu `_com_ptr_t` Nesne sahipliği çağırmadan ham arabirim işaretçisi alır `AddRef`. `Release` daha önce Kapsüllenen işaretçi için başvuru sayısını azaltma için çağrılır.  
  
 **END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_com_ptr_t Sınıfı](../cpp/com-ptr-t-class.md)