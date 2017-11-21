---
title: "İlişkisel işlev şablonları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords: relational function templates
ms.assetid: 57893a51-9adb-41fc-941d-2ca97687db2a
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 73925a124c341f1a9e76ce7a17f34608b10a8936
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="relational-function-templates"></a>İlişkisel İşlev Şablonları
**Microsoft özel**  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      template<typename _InterfaceType> bool operator==(  
   int NULL,  
   _com_ptr_t<_InterfaceType>& p   
);  
template<typename _Interface,  
   typename _InterfacePtr> bool operator==(  
   _Interface* i,  
   _com_ptr_t<_InterfacePtr>& p   
);  
template<typename _Interface> bool operator!=(  
   int NULL,  
   _com_ptr_t<_Interface>& p   
);  
template<typename _Interface,  
   typename _InterfacePtr> bool operator!=(  
   _Interface* i,  
   _com_ptr_t<_InterfacePtr>& p   
);  
template<typename _Interface> bool operator<(  
   int NULL,  
   _com_ptr_t<_Interface>& p   
);  
template<typename _Interface,  
   typename _InterfacePtr> bool operator<(  
   _Interface* i,  
   _com_ptr_t<_InterfacePtr>& p   
);  
template<typename _Interface> bool operator>(  
   int NULL,  
   _com_ptr_t<_Interface>& p   
);  
template<typename _Interface,  
   typename _InterfacePtr> bool operator>(  
   _Interface* i,  
   _com_ptr_t<_InterfacePtr>& p   
);  
template<typename _Interface> bool operator<=(  
   int NULL,  
   _com_ptr_t<_Interface>& p   
);  
template<typename _Interface,  
   typename _InterfacePtr> bool operator<=(  
   _Interface* i,  
   _com_ptr_t<_InterfacePtr>& p   
);  
template<typename _Interface> bool operator>=(  
   int NULL,  
   _com_ptr_t<_Interface>& p   
);  
template<typename _Interface,  
   typename _InterfacePtr> bool operator>=(  
   _Interface* i,  
   _com_ptr_t<_InterfacePtr>& p   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *t*  
 Ham arabirim işaretçisi.  
  
 `p`  
 Akıllı bir işaretçi.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev şablonları karşılaştırma işlecinin sağ tarafta karşılaştırma akıllı işaretçiyle izin verin. Bu üye işlevlerini olmayan `_com_ptr_t`.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_com_ptr_t sınıfı](../cpp/com-ptr-t-class.md)