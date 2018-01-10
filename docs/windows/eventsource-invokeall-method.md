---
title: "EventSource::ınvokeall yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: event/Microsoft::WRL::EventSource::InvokeAll
dev_langs: C++
helpviewer_keywords: InvokeAll method
ms.assetid: 1506618f-0421-4428-a4d0-4ea2b10a3bf6
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 45835b6929ae73559c427d374430b64e7ff21a61
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="eventsourceinvokeall-method"></a>EventSource::InvokeAll Yöntemi
Geçerli ilişkili her olay işleyici çağırması [EventSource](../windows/eventsource-class.md) belirtilen bağımsız değişken türleri ve bağımsız değişkenler kullanarak nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void InvokeAll();  
template <  
   typename T0  
>  
void InvokeAll(  
   T0arg0  
);  
template <  
   typename T0,  
   typename T1  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2,  
   typename T3  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2,  
   T3arg3  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2,  
   typename T3,  
   typename T4  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2,  
   T3arg3,  
   T4arg4  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2,  
   typename T3,  
   typename T4,  
   typename T5  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2,  
   T3arg3,  
   T4arg4,  
   T5arg5  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2,  
   typename T3,  
   typename T4,  
   typename T5,  
   typename T6  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2,  
   T3arg3,  
   T4arg4,  
   T5arg5,  
   T6arg6  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2,  
   typename T3,  
   typename T4,  
   typename T5,  
   typename T6,  
   typename T7  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2,  
   T3arg3,  
   T4arg4,  
   T5arg5,  
   T6arg6,  
   T7arg7  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2,  
   typename T3,  
   typename T4,  
   typename T5,  
   typename T6,  
   typename T7,  
   typename T8  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2,  
   T3arg3,  
   T4arg4,  
   T5arg5,  
   T6arg6,  
   T7arg7,  
   T8arg8  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2,  
   typename T3,  
   typename T4,  
   typename T5,  
   typename T6,  
   typename T7,  
   typename T8,  
   typename T9  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2,  
   T3arg3,  
   T4arg4,  
   T5arg5,  
   T6arg6,  
   T7arg7,  
   T8arg8,  
   T9arg9  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T0`  
 Sıfırıncı olay işleyicisi bağımsız değişken türü.  
  
 `T1`  
 İlk olay işleyicisi bağımsız değişken türü.  
  
 `T2`  
 İkinci olay işleyicisi bağımsız değişken türü.  
  
 `T3`  
 Üçüncü olay işleyicisi bağımsız değişken türü.  
  
 `T4`  
 Dördüncü olay işleyicisi bağımsız değişken türü.  
  
 `T5`  
 Beşinci olay işleyicisi bağımsız değişken türü.  
  
 `T6`  
 Altıncı olay işleyicisi bağımsız değişken türü.  
  
 `T7`  
 Yedinci olay işleyicisi bağımsız değişken türü.  
  
 `T8`  
 Alt olay işleyicisi bağımsız değişken türü.  
  
 `T9`  
 Dokuzuncu olay işleyicisi bağımsız değişken türü.  
  
 `arg0`  
 Sıfırıncı olay işleyicisi bağımsız değişken.  
  
 `arg1`  
 İlk olay işleyicisi bağımsız değişken.  
  
 `arg2`  
 İkinci olay işleyicisi bağımsız değişken.  
  
 `arg3`  
 Üçüncü olay işleyicisi bağımsız değişken.  
  
 `arg4`  
 Dördüncü olay işleyicisi bağımsız değişken.  
  
 `arg5`  
 Beşinci olay işleyicisi bağımsız değişken.  
  
 `arg6`  
 Altıncı olay işleyicisi bağımsız değişken.  
  
 `arg7`  
 Yedinci olay işleyicisi bağımsız değişken.  
  
 `arg8`  
 Alt olay işleyicisi bağımsız değişken.  
  
 `arg9`  
 Dokuzuncu olay işleyicisi bağımsız değişken.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** event.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Ayrıca Bkz.
 [EventSource Sınıfı](../windows/eventsource-class.md)