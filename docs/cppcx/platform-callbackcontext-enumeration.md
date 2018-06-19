---
title: Platform::CallbackContext numaralandırma | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::CallbackContext
dev_langs:
- C++
helpviewer_keywords:
- Platform::CallbackContext Enumeration
ms.assetid: 60e0c7cb-5d8f-482a-bdca-ca9335ae4899
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 757de5f686bb809a5d2fb159a3ee547a20edc982
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33086960"
---
# <a name="platformcallbackcontext-enumeration"></a>Platform::CallbackContext numaralandırması
İçinde bir geri çağırma işlevi (olay işleyicisi) yürüten iş parçacığı içeriği belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum class CallbackContext {};  
```  
  
### <a name="members"></a>Üyeler  
  
|Türü kodu|Açıklama|  
|---------------|-----------------|  
|tüm|Geri çağırma işlevi her iş parçacığı bağlam yürütebilir.|  
|Aynı|Geri çağırma işlevi, zaman uyumsuz işlemi başlatılan iş parçacığı içeriği yürütebilir.|  
  
### <a name="requirements"></a>Gereksinimler  
 **Desteklenen en düşük istemci:** Windows 8  
  
 **Desteklenen en düşük sunucu:** Windows Server 2012  
  
 **Namespace:** Platform  
  
 **Meta veriler:** platform.winmd