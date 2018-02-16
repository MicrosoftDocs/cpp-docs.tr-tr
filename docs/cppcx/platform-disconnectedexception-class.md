---
title: "Platform::DisconnectedException sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::DisconnectedException
- VCCORLIB/Platform::DisconnectedException::DisconnectedException
dev_langs:
- C++
helpviewer_keywords:
- Platform::DisconnectedException
ms.assetid: c25e0d64-5bff-4c21-88e5-c4ec2776fa7f
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 175d132f2c6734f5f8328baee8cbdc4ea7e1b4c3
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="platformdisconnectedexception-class"></a>Platform::DisconnectedException sınıfı
Bir COM proxy nesnesi artık mevcut bir COM sunucusu başvuru girişiminde bulunduğunda oluşur  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
public ref class DisconnectedException : COMException,    IException,    IPrintable,    IEquatable  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ne zaman sınıf b tutan sınıf A başvurularını, sınıf A gibi ayrı bir işlem içinde başka bir sınıf (sınıf B) işlem dışı COM sunucusu ile iletişim kurmak için bir proxy nesnesi gerektirir Bazen sunucu sınıfı olmadan bellek yetersiz hakkında bilmek gidebilirsiniz. Bu durumda RPC_E_DISCONNECTED özel durum oluşur ve Platform::DisconnectedException için çevrilir. Bir senaryoda olduğu oluşur bir olay kaynağı kendisine geçirilen bir temsilcisini çağırır ancak olayına abone sonra temsilci noktada yok edildi durumdur. Bu durumda, olay kaynağı kendi çağırma listesinden bu temsilciyi kaldırır.  
  
 Daha fazla bilgi için bkz: [COMException](../cppcx/platform-comexception-class.md) sınıfı.  
  
### <a name="requirements"></a>Gereksinimler  
 **Desteklenen en düşük istemci:** Windows 8  
  
 **Desteklenen en düşük sunucu:** Windows Server 2012  
  
 **Namespace:** Platform  
  
 **Meta veriler:** platform.winmd  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform::COMException Sınıfı](../cppcx/platform-comexception-class.md)