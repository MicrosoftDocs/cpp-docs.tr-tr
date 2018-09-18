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
ms.openlocfilehash: 12e035a27693fcad095cd83880aba99c37ba1c1f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46027641"
---
# <a name="badtarget-class"></a>bad_target Sınıfı
Bu sınıf, bir özel durum gerçekleştirilmekte olan işlem için geçersiz bir hedefe bir ileti bloğu bir işaretçi verildiğinde, durum açıklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class bad_target : public std::exception;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[bad_target](#ctor)|Fazla Yüklendi. Oluşturur bir `bad_target` nesne.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu özel durum, genellikle bir hedef için farklı bir hedef ayrılmış olan bir iletiyi kullanmak çalışan veya değil tutan bir ayırma serbest gibi nedenlerle oluşturulur.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `exception`  
  
 `bad_target`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="ctor"></a> bad_target 

 Oluşturur bir `bad_target` nesne.  
  
```
explicit _CRTIMP bad_target(_In_z_ const char* _Message) throw();

bad_target() throw();
```  
  
### <a name="parameters"></a>Parametreler  
*İl_eti*<br/>
Hatanın açıklayıcı bir iletisi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [Zaman Uyumsuz İleti Blokları](../../../parallel/concrt/asynchronous-message-blocks.md)



