---
title: "Platform::ValueType sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 02/03/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: VCCORLIB/Platform::ValueType::ToString
dev_langs: C++
helpviewer_keywords: Platform::ValueType Class
ms.assetid: 79aa8754-b140-4974-a5b1-be046938a10a
caps.latest.revision: "5"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4dba418e74affb2531e3ebbd43d95c35601e9a26
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="platformvaluetype-class"></a>Platform::ValueType sınıfı
Taban sınıfı için değer türleri örnekleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
public ref class ValueType : Object  
```  
  
## <a name="public-methods"></a>Genel yöntemler  
  
|||  
|-|-|  
|[ValueType::ToString](#tostring)|Nesnenin dize gösterimini döndürür. Devralınan [Platform::Object](../cppcx/platform-object-class.md).|  
  
### <a name="remarks"></a>Açıklamalar  
 ValueType sınıf değer türleri oluşturmak için kullanılır. ValueType temel üyelere sahip nesnesinden türetilir. Ancak, derleyici ValueType sınıfından türetilen türlerin temel bu üyelerinden ayırır. Değer türü Kutulu zaman derleyici bu temel üyeler reattaches.  
  
### <a name="requirements"></a>Gereksinimler  
 **Desteklenen en düşük istemci:** Windows 8  
  
 **Desteklenen en düşük sunucu:** Windows Server 2012  
  
 **Namespace:** Platform  
  
 **Meta veriler:** platform.winmd  

## <a name="tostring"></a>ValueType::ToString yöntemi
Nesnenin dize gösterimini döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
Platform::String ToString();  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Değerin temsil eden Platform::String.  
    
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform ad alanı](../cppcx/platform-namespace-c-cx.md)