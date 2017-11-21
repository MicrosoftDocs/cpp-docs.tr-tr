---
title: "progress_reporter sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- progress_reporter
- PPLTASKS/concurrency::progress_reporter
- PPLTASKS/concurrency::progress_reporter::progress_reporter
- PPLTASKS/concurrency::progress_reporter::report
dev_langs: C++
helpviewer_keywords: progress_reporter class
ms.assetid: b836efab-2d05-4649-b6fa-d15236f1f813
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a72250bcb35b625276d0b8692ce1ec9d13a20ade
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
|[raporu](#report)|Zaman uyumsuz eylem ya da bu ilerleme Raporlayıcı bağlandığı işlemi ilerleme durumu raporu gönderir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu tür, yalnızca Windows mağazası uygulamaları için kullanılabilir.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `progress_reporter`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** ppltasks.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="ctor"></a>progress_reporter 

```
progress_reporter();
```  
  
##  <a name="report"></a>raporu 

 Zaman uyumsuz eylem ya da bu ilerleme Raporlayıcı bağlandığı işlemi ilerleme durumu raporu gönderir.  
  
```
void report(const _ProgressType& val) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `val`  
 Rapora bir ilerleme bildirimi aracılığıyla yükü.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)
