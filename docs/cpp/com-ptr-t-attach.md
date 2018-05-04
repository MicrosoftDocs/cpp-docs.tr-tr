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
ms.openlocfilehash: 7341695ad0cbc8384da859b80a72a63d8d52215f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="comptrtattach"></a>_com_ptr_t::Attach
**Microsoft özel**  
  
 Bu akıllı işaretçinin türü ham arabirim işaretçisi yalıtır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      void Attach(  
   Interface* pInterface   
) throw( );  
void Attach(  
   Interface* pInterface,  
   bool fAddRef   
) throw( );  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pInterface`  
 Ham arabirim işaretçisi.  
  
 `fAddRef`  
 Eğer öyleyse **true**, ardından `AddRef` olarak adlandırılır. Eğer öyleyse **false**, `_com_ptr_t` nesnesini alır çağırmadan ham arabirim işaretçisi sahipliğini `AddRef`.  
  
## <a name="remarks"></a>Açıklamalar  
  
-   **Ekleme (**`pInterface`**)** `AddRef` çağrılmaz.     Arabirim sahipliğini için geçirilen `_com_ptr_t` nesnesi. **Yayın** önceden kapsüllenmiş işaretçi başvuru sayısı azaltma için çağrılır.  
  
-   **Ekleme (** `pInterface` **,**`fAddRef`**)** varsa `fAddRef` olan **true**, `AddRef` başvuru artırmak için çağrılır Kapsüllenmiş arabirim işaretçisi için sayısı.       Varsa `fAddRef` olan **false**, bu `_com_ptr_t` nesnesini alır çağırmadan ham arabirim işaretçisi sahipliğini `AddRef`. **Yayın** önceden kapsüllenmiş işaretçi başvuru sayısı azaltma için çağrılır.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_com_ptr_t Sınıfı](../cpp/com-ptr-t-class.md)