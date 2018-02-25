---
title: "progress_reporter sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 122a5b5c402e356863c40e2fb7d461dbe3f0b7b9
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
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
  
##  <a name="report">Raporu</a> 

 Zaman uyumsuz eylem ya da bu ilerleme Raporlayıcı bağlandığı işlemi ilerleme durumu raporu gönderir.  
  
```
void report(const _ProgressType& val) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `val`  
 Rapora bir ilerleme bildirimi aracılığıyla yükü.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı](concurrency-namespace.md)
