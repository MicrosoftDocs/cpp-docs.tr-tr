---
title: "ComPtr::operator Microsoft::WRL::Details::BoolType işleci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: cfba6521-fb30-4fb8-afb2-cfab1cb5e0b8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f98ca8068495be46b795d361c969c4feb2c24169
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [ComPtr::Get Metodu](../windows/comptr-get-method.md)