---
title: "ComPtr::operator Microsoft::WRL::Details::BoolType işleci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
ms.assetid: cfba6521-fb30-4fb8-afb2-cfab1cb5e0b8
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 010979a0a72fc1d522a921b20df4579bc6efa159
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="comptroperator-microsoftwrldetailsbooltype-operator"></a>ComPtr::operator Microsoft::WRL::Details::BoolType İşleci
Bir ComPtr bir arabirim nesne ömrü yönetme olup olmadığını gösterir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
WRL_NOTHROW operator Microsoft::WRL::Details::BoolType() const;  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Arabirim bu ComPtr adresini ilişkili olup olmadığını [BoolStruct::Member](../windows/boolstruct-member-data-member.md) veri üyesi; Aksi halde, `nullptr`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ComPtr sınıfı](../windows/comptr-class.md)   
 [ComPtr::Get yöntemi](../windows/comptr-get-method.md)