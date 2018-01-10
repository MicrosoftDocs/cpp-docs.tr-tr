---
title: "Platform::SizeT değer sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: VCCORLIB/PlatformSizeT::SizeT constructor
dev_langs: C++
helpviewer_keywords: Platform::SizeT Struct
ms.assetid: 0803612c-8ba1-430c-9b7b-1bebae88608d
caps.latest.revision: "4"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bf47d911dc348b23e371175cf46fc6d677ce9f36
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="platformsizet-value-class"></a>Platform::SizeT değer sınıfı
Bir nesnenin boyutu temsil eder. SizeT bir imzasız veri türüdür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
public ref class SizeT sealed : ValueType  
```  
  
### <a name="members"></a>Üyeler  
  
|Üye|Açıklama|  
|------------|-----------------|  
|[SizeT::SizeT Oluşturucusu](#ctor)|Belirtilen değerle sınıfının yeni bir örneğini başlatır.|  
  
### <a name="requirements"></a>Gereksinimler  
 **Desteklenen en düşük istemci:** Windows 8  
  
 **Desteklenen en düşük sunucu:** Windows Server 2012  
  
 **Namespace:** Platform  
  
 **Meta veriler:** platform.winmd  

 ## <a name="ctor"></a>SizeT::SizeT Oluşturucusu
Belirtilen değerle SizeT yeni bir örneğini başlatır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
SizeT( uint32 value1 );   SizeT( void* value2 );  
```  
  
### <a name="parameters"></a>Parametreler  
 Değer1  
 İşaretsiz bir 32 bit değer.  
  
 Value2  
 İşaretsiz bir 32 bit değer işaretçi.  
  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform ad alanı](../cppcx/platform-namespace-c-cx.md)