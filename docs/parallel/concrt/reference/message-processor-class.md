---
title: "message_processor sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- message_processor
- AGENTS/concurrency::message_processor
- AGENTS/concurrency::message_processor::async_send
- AGENTS/concurrency::message_processor::sync_send
- AGENTS/concurrency::message_processor::wait
- AGENTS/concurrency::message_processor::process_incoming_message
dev_langs: C++
helpviewer_keywords: message_processor class
ms.assetid: 23afb052-daa7-44ed-bf24-d2513db748da
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9f93763a3d29e19feaa110b336c4cc9bb832539d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="messageprocessor-class"></a>message_processor Sınıfı
`message_processor` Sınıftır işlenmesi için Özet temel sınıf `message` nesneleri. İletilerin sıralama üzerinde garantisi yoktur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class T>
class message_processor;
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Yükü iletileri içinde veri türünü bu tarafından işlenen `message_processor` nesnesi.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`type`|İçin bir tür diğer adı `T`.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[async_send](#async_send)|Türetilen bir sınıfta geçersiz kılındığında, iletileri bloğuna zaman uyumsuz olarak yerleştirir.|  
|[sync_send](#sync_send)|Türetilen bir sınıfta geçersiz kılındığında, iletileri bloğuna zaman uyumlu olarak yerleştirir.|  
|[bekleme](#wait)|Türetilen bir sınıfta geçersiz kılındığında, tamamlamak tüm zaman uyumsuz işlemleri için bekler.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[process_incoming_message](#process_incoming_message)|Türetilen bir sınıfta geçersiz kılındığında, iletme iletilerinin işlenmesini bloğuna gerçekleştirir. Yeni bir ileti eklenir ve sıranın boş olmasını bulunan her zaman bir kez çağrılır.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `message_processor`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** agents.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="async_send"></a>async_send 

 Türetilen bir sınıfta geçersiz kılındığında, iletileri bloğuna zaman uyumsuz olarak yerleştirir.  
  
```
virtual void async_send(_Inout_opt_ message<T>* _Msg) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Msg`  
 A `message` zaman uyumsuz olarak göndermek için nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlemci uygulamaları bu yöntemin üzerine yazması gerekir.  
  
##  <a name="process_incoming_message"></a>process_incoming_message 

 Türetilen bir sınıfta geçersiz kılındığında, iletme iletilerinin işlenmesini bloğuna gerçekleştirir. Yeni bir ileti eklenir ve sıranın boş olmasını bulunan her zaman bir kez çağrılır.  
  
```
virtual void process_incoming_message() = 0;
```  
  
### <a name="remarks"></a>Açıklamalar  
 İleti bloğu uygulamalarında bu yöntemin üzerine yazması gerekir.  
  
##  <a name="sync_send"></a>sync_send 

 Türetilen bir sınıfta geçersiz kılındığında, iletileri bloğuna zaman uyumlu olarak yerleştirir.  
  
```
virtual void sync_send(_Inout_opt_ message<T>* _Msg) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Msg`  
 A `message` zaman uyumlu olarak göndermek için nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlemci uygulamaları bu yöntemin üzerine yazması gerekir.  
  
##  <a name="wait"></a>bekleme 

 Türetilen bir sınıfta geçersiz kılındığında, tamamlamak tüm zaman uyumsuz işlemleri için bekler.  
  
```
virtual void wait() = 0;
```  
  
### <a name="remarks"></a>Açıklamalar  
 İşlemci uygulamaları bu yöntemin üzerine yazması gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [ordered_message_processor sınıfı](ordered-message-processor-class.md)
