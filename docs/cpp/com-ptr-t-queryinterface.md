---
title: _com_ptr_t::QueryInterface | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::QueryInterface
- _com_ptr_t.QueryInterface
dev_langs:
- C++
helpviewer_keywords:
- QueryInterface method [C++]
ms.assetid: d03292f1-6b02-40db-9756-8b0837a97319
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 20d22fac89b151a28e856ac4eaf61021faa6bfd5
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39407438"
---
# <a name="comptrtqueryinterface"></a>_com_ptr_t::QueryInterface
**Microsoft'a özgü**  
  
 Çağrıları **QueryInterface** üye işlevinin `IUnknown` kapsüllenmiş arabirim işaretçisini üzerinde.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename _InterfaceType> HRESULT QueryInterface (  
   const IID& iid,  
   _InterfaceType*& p   
) throw ( );  
template<typename _InterfaceType> HRESULT QueryInterface (  
   const IID& iid,  
   _InterfaceType** p  
) throw( );  
```  
  
#### <a name="parameters"></a>Parametreler  
 *IID*  
 `IID` bir arabirim işaretçisi.  
  
 *p*  
 Ham arabirim işaretçisi.  
  
## <a name="remarks"></a>Açıklamalar  
 Çağrıları `IUnknown::QueryInterface` kapsüllenmiş arabirim işaretçisini belirli üzerinde `IID` ve içinde elde edilen ham arabirim işaretçisi döndüren *p*. Bu yordam, başarıyı veya başarısızlığı göstermek için HRESULT döndürür.  
  
 **END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [_com_ptr_t Sınıfı](../cpp/com-ptr-t-class.md)