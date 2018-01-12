---
title: "auto_gcroot sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- msclr::auto_gcroot
- msclr.auto_gcroot
- auto_gcroot
dev_langs: C++
helpviewer_keywords: auto_gcroot
ms.assetid: b5790912-265d-463e-a486-47302e91042a
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: bb203193d1568056c631d90a2e1f5b1cf1d00e5a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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