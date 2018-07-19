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
ms.openlocfilehash: c455ce81a869d64b3a9019088028e384c6a06217
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37947999"
---
# <a name="comptrtqueryinterface"></a>_com_ptr_t::QueryInterface
**Microsoft'a özgü**  
  
 Çağrıları `QueryInterface` üye işlevinin `IUnknown` kapsüllenmiş arabirim işaretçisini üzerinde.  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_com_ptr_t Sınıfı](../cpp/com-ptr-t-class.md)