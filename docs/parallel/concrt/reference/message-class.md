---
title: "message sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- message
- AGENTS/concurrency::message
- AGENTS/concurrency::message::message
- AGENTS/concurrency::message::add_ref
- AGENTS/concurrency::message::msg_id
- AGENTS/concurrency::message::remove_ref
- AGENTS/concurrency::message::payload
dev_langs: C++
helpviewer_keywords: message class
ms.assetid: 3e1f3505-6c0c-486c-8191-666d0880ec62
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 55d1744d67156bcfcf6f76c757fc97ab0d4fd380
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="message-class"></a>message Sınıfı
İleti blokları geçirilen veri yükü içeren temel ileti Zarf.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class T>
class message : public ::Concurrency::details::_Runtime_object;
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Yükü ileti içinde veri türü.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`type`|İçin bir tür diğer adı `T`.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[message](#ctor)|Fazla Yüklendi. Oluşturan bir `message` nesnesi.|  
|[~ message yok Edicisi](#dtor)|Bozar `message` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[add_ref](#add_ref)|İçin başvuru sayısı ekler `message` nesnesi. Başvuru sayım ileti yaşam süresi belirlemek için gereken ileti blokları için kullanılır.|  
|[msg_id](#msg_id)|Kimliğini döndürür `message` nesnesi.|  
|[remove_ref](#remove_ref)|Başvuru sayısı için gelen çıkarır `message` nesnesi. Başvuru sayım ileti yaşam süresi belirlemek için gereken ileti blokları için kullanılır.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Yükü](#payload)|Yükü `message` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [zaman uyumsuz ileti blokları](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `message`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** agents.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="add_ref"></a>add_ref 

 İçin başvuru sayısı ekler `message` nesnesi. Başvuru sayım ileti yaşam süresi belirlemek için gereken ileti blokları için kullanılır.  
  
```
long add_ref();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başvuru sayısı yeni değeri.  
  
##  <a name="ctor"></a>İleti 

 Oluşturan bir `message` nesnesi.  
  
```
message(
    T const& _P);

message(
    T const& _P,
    runtime_object_identity _Id);

message(
    message const& _Msg);

message(
    _In_ message const* _Msg);
```  
  
### <a name="parameters"></a>Parametreler  
 `_P`  
 Bu iletinin yükü.  
  
 `_Id`  
 Bu iletinin benzersiz kimliği.  
  
 `_Msg`  
 Bir başvuru veya işaretçi bir `message` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir işaretçi alan oluşturucu bir `message` nesne bir değişken oluşturur gibi bir [invalid_argument](../../../standard-library/invalid-argument-class.md) özel durum, parametre `_Msg` olan `NULL`.  
  
##  <a name="dtor"></a>~ iletisi 

 Bozar `message` nesnesi.  
  
```
virtual ~message();
```  
  
##  <a name="msg_id"></a>msg_id 

 Kimliğini döndürür `message` nesnesi.  
  
```
runtime_object_identity msg_id() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `runtime_object_identity` , `message` Nesnesi.  
  
##  <a name="payload"></a>Yükü 

 Yükü `message` nesnesi.  
  
```
T const payload;
```  
  
##  <a name="remove_ref"></a>remove_ref 

 Başvuru sayısı için gelen çıkarır `message` nesnesi. Başvuru sayım ileti yaşam süresi belirlemek için gereken ileti blokları için kullanılır.  
  
```
long remove_ref();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başvuru sayısı yeni değeri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı](concurrency-namespace.md)
