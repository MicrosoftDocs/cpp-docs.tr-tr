---
title: accelerator_view_removed sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- accelerator_view_removed
- AMPRT/accelerator_view_removed
- AMPRT/Concurrency::accelerator_view_removed:accelerator_view_removed
- AMPRT/Concurrency::accelerator_view_removed:get_view_removed_reason
dev_langs:
- C++
helpviewer_keywords:
- AMPRT/Concurrency::accelerator_view_removed:accelerator_view_removed Class
ms.assetid: 262446de-311c-454e-a5ed-e2aaced0d88a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0426dd44cfcb8f655f3981802dfe23adcd436a0d
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="acceleratorviewremoved-class"></a>accelerator_view_removed Sınıfı
Windows zaman aşımı algılama ve kurtarma mekanizması nedeniyle bir temel alınan DirectX araması başarısız olmadığında oluşan özel durum.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class accelerator_view_removed : public runtime_exception;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[accelerator_view_removed Oluşturucusu](#ctor)|Yeni bir örneğini başlatır `accelerator_view_removed` sınıfı.|  

### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[get_view_removed_reason](#get_view_removed_reason)|Nedenini belirten bir HRESULT hata kodu döndürüyor `accelerator_view` nesnenin kaldırma.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `exception`  
  
 `runtime_exception`  
  
 `out_of_memory`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** amprt.h  
  
 **Namespace:** eşzamanlılık  

## <a name="ctor"></a> accelerator_view_removed 

Yeni bir örneğini başlatır [accelerator_view_removed](accelerator-view-removed-class.md) sınıfı.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
explicit accelerator_view_removed(  
    const char * _Message,  
    HRESULT _View_removed_reason ) throw();  
  
explicit accelerator_view_removed(  
    HRESULT _View_removed_reason ) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 `_Message`  
 Hatanın açıklaması.  
  
 `_View_removed_reason`  
 Kaldırma nedenini belirten bir HRESULT hata kodu `accelerator_view` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Accelerator_view_removed sınıfının yeni bir örneği.  
  
## <a name="get_view_removed_reason_method"></a> get_view_removed_reason 

Nedenini belirten bir HRESULT hata kodu döndürüyor `accelerator_view` nesnenin kaldırma.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT get_view_removed_reason() const throw();  
```  
  
 
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
