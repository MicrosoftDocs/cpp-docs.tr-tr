---
title: "Platform::ChangedStateException sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- VCCORLIB/Platform::ChangedStateException
- VCCORLIB/Platform::ChangedStateException::ChangedStateException
dev_langs: C++
helpviewer_keywords: Platform::ChangedStateException
ms.assetid: f894beac-9e80-4fac-ac25-89f1dbc0a6a4
caps.latest.revision: "4"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e874cb1ca3db5741d2974499c53e23816e204186
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="platformchangedstateexception-class"></a>Platform::ChangedStateException sınıfı
Bir nesnenin iç durumu değiştiğinde, böylece yöntemi sonuçlarını geçersiz kılmalarını oluşturulur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
public ref class ChangedStateException : COMException,    IException,    IPrintable,    IEquatable  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir koleksiyon yineleyici veya bir koleksiyon görünümü yöntemlerini yöntemi sonuçlarını geçersiz kılmalarını üst koleksiyon değiştikten sonra çağrıldığında, bu özel durum bir örnektir.  
  
 Daha fazla bilgi için bkz: [COMException](../cppcx/platform-comexception-class.md) sınıfı.  
  
### <a name="requirements"></a>Gereksinimler  
 **Desteklenen en düşük istemci:** Windows 8  
  
 **Desteklenen en düşük sunucu:** Windows Server 2012  
  
 **Namespace:** Platform  
  
 **Meta veriler:** platform.winmd  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform::COMException Sınıfı](../cppcx/platform-comexception-class.md)