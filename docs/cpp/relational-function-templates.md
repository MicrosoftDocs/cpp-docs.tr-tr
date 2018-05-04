---
title: İlişkisel işlev şablonları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- relational function templates
ms.assetid: 57893a51-9adb-41fc-941d-2ca97687db2a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3a3147ae06e4deedf48415b4ae605e524458343c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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
 *i*  
 Ham arabirim işaretçisi.  
  
 `p`  
 Akıllı bir işaretçi.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev şablonları karşılaştırma işlecinin sağ tarafta karşılaştırma akıllı işaretçiyle izin verin. Bu üye işlevlerini olmayan `_com_ptr_t`.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_com_ptr_t Sınıfı](../cpp/com-ptr-t-class.md)