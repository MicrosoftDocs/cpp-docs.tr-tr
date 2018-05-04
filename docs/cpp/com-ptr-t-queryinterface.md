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
ms.openlocfilehash: 7c046f1b1d14b7e7dbd44ca9f5f012e632efef6e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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
 [_com_ptr_t Sınıfı](../cpp/com-ptr-t-class.md)