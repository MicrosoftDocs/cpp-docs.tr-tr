---
title: auto_gcroot sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- msclr::auto_gcroot
- msclr.auto_gcroot
- auto_gcroot
dev_langs:
- C++
helpviewer_keywords:
- auto_gcroot
ms.assetid: b5790912-265d-463e-a486-47302e91042a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b6afad3450aff2a9243b3e4a480a374fbcd14fc7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33103872"
---
# <a name="autogcroot-class"></a>auto_gcroot Sınıfı
Otomatik kaynak yönetimi (gibi [auto_ptr sınıfı](../standard-library/auto-ptr-class.md)) yerel tür içinde sanal bir işleyiciyi katıştırmak için kullanılabilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename _element_type>  
class auto_gcroot;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `_element_type`  
 Katıştırılmış yönetilen türü.  
  
## <a name="requirements"></a>Gereksinimler  
 **Üstbilgi dosyası** \<msclr\auto_gcroot.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [auto_gcroot](../dotnet/auto-gcroot.md)   
 [auto_gcroot üyeleri](../dotnet/auto-gcroot-members.md)   
 [Nasıl yapılır: yerel türlerde işleyicileri bildirme](../dotnet/how-to-declare-handles-in-native-types.md)   
 [auto_handle Class](../dotnet/auto-handle-class.md)