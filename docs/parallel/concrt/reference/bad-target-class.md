---
title: bad_target sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- bad_target
- CONCRT/concurrency::bad_target
- CONCRT/concurrency::bad_target::bad_target
dev_langs:
- C++
helpviewer_keywords:
- bad_target class
ms.assetid: e6dcddbf-9217-4fac-ac7f-7b8b4781d2f5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: be10e5e4105dd16a68ad2854538d6181e90bfbe9
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33705347"
---
# <a name="badtarget-class"></a>bad_target Sınıfı
Bu sınıf, bir ileti bloğu gerçekleştirilen işlem için geçersiz bir hedef için bir işaretçi verildiğinde oluşturulan bir özel açıklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class bad_target : public std::exception;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[bad_target](#ctor)|Fazla Yüklendi. Oluşturan bir `bad_target` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu durum genellikle farklı bir hedef için ayrılmış bir ileti kullanma girişiminde veya değil tutan bir ayırma serbest hedef gibi nedenlerle oluşturulur.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `exception`  
  
 `bad_target`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="ctor"></a> bad_target 

 Oluşturan bir `bad_target` nesnesi.  
  
```
explicit _CRTIMP bad_target(_In_z_ const char* _Message) throw();

bad_target() throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `_Message`  
 Hata açıklayıcı bir ileti.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [Zaman Uyumsuz İleti Blokları](../../../parallel/concrt/asynchronous-message-blocks.md)



