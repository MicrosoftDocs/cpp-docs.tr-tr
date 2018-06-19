---
title: progress_reporter sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- progress_reporter
- PPLTASKS/concurrency::progress_reporter
- PPLTASKS/concurrency::progress_reporter::progress_reporter
- PPLTASKS/concurrency::progress_reporter::report
dev_langs:
- C++
helpviewer_keywords:
- progress_reporter class
ms.assetid: b836efab-2d05-4649-b6fa-d15236f1f813
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d5d4dc98c4fb411a4d63fdfad5049cf0df723bec
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686571"
---
# <a name="progressreporter-class"></a>progress_reporter Sınıfı
Belirli bir türdeki ilerleme bildirimleri raporlama ilerleme Raporlayıcı sınıf sağlar. Her progress_reporter nesne belirli bir zaman uyumsuz eylem veya işlem için bağlı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<typename _ProgressType>
class progress_reporter;
```  
  
#### <a name="parameters"></a>Parametreler  
 `_ProgressType`  
 İlerleme Raporlayıcı bildirilen her ilerleme bildirimi yük türü.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[progress_reporter](#ctor)||  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Raporu](#report)|Zaman uyumsuz eylem ya da bu ilerleme Raporlayıcı bağlandığı işlemi ilerleme durumu raporu gönderir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu tür, yalnızca Windows çalışma zamanı uygulamaları için kullanılabilir.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `progress_reporter`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** ppltasks.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="ctor"></a> progress_reporter 

```
progress_reporter();
```  
  
##  <a name="report"></a> Raporu 

 Zaman uyumsuz eylem ya da bu ilerleme Raporlayıcı bağlandığı işlemi ilerleme durumu raporu gönderir.  
  
```
void report(const _ProgressType& val) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `val`  
 Rapora bir ilerleme bildirimi aracılığıyla yükü.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı](concurrency-namespace.md)
