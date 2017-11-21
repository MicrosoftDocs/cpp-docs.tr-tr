---
title: _com_ptr_t::QueryInterface | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::QueryInterface
- _com_ptr_t.QueryInterface
dev_langs: C++
helpviewer_keywords: QueryInterface method [C++]
ms.assetid: d03292f1-6b02-40db-9756-8b0837a97319
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1dd546da4730bfd2995b4d97be8017807d2ae161
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="comptrtqueryinterface"></a>_com_ptr_t::QueryInterface
**Microsoft özel**  
  
 Çağrıları `QueryInterface` üye işlevini **IUnknown** kapsüllenmiş arabirim işaretçisi üzerinde.  
  
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
 `iid`  
 **IID** arabirimi işaretçisi.  
  
 `p`  
 Ham arabirim işaretçisi.  
  
## <a name="remarks"></a>Açıklamalar  
 Çağrıları **IUnknown::QueryInterface** kapsüllenmiş arabirim işaretçisi ile belirtilen üzerinde **IID** ve sonuçta elde edilen ham arabirimi işaretçinin döndürür `p`. Bu yordam, başarıyı veya başarısızlığı göstermek için `HRESULT` döndürür.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_com_ptr_t sınıfı](../cpp/com-ptr-t-class.md)