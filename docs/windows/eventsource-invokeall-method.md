---
title: EventSource::ınvokeall yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource::InvokeAll
dev_langs:
- C++
helpviewer_keywords:
- InvokeAll method
ms.assetid: 1506618f-0421-4428-a4d0-4ea2b10a3bf6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 04a31c7d080ff4fbfae094e07ab02d912966f4b1
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570664"
---
# <a name="eventsourceinvokeall-method"></a>EventSource::InvokeAll Yöntemi
Geçerli ile ilgili her olay işleyicisini çağırır [EventSource](../windows/eventsource-class.md) belirtilen bağımsız değişken türleri ve bağımsız değişkenleri kullanarak nesne.  
  
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
  
### <a name="parameters"></a>Parametreler  
 *T0*  
 Sıfırıncı olay işleyicisi bağımsız değişken türü.  
  
 *T1*  
 İlk olay işleyicisi bağımsız değişken türü.  
  
 *T2*  
 İkinci olay işleyicisi bağımsız değişken türü.  
  
 *T3*  
 Üçüncü olay işleyicisi bağımsız değişken türü.  
  
 *T4*  
 Dördüncü olay işleyicisi bağımsız değişken türü.  
  
 *T5*  
 Beşinci olay işleyicisi bağımsız değişken türü.  
  
 *T6*  
 Altıncı olay işleyicisi bağımsız değişken türü.  
  
 *T7*  
 Yedinci olay işleyicisi bağımsız değişken türü.  
  
 *T8*  
 Sekizinci olay işleyicisi bağımsız değişken türü.  
  
 *T9*  
 Dokuzuncu olay işleyicisi bağımsız değişken türü.  
  
 *arg0*  
 Sıfırıncı olay işleyicisi bağımsız değişken.  
  
 *arg1*  
 İlk olay işleyicisi bağımsız değişken.  
  
 *arg2*  
 İkinci olay işleyicisi bağımsız değişken.  
  
 *Arg3*  
 Üçüncü olay işleyicisi bağımsız değişken.  
  
 *Arg4*  
 Dördüncü olay işleyicisi bağımsız değişken.  
  
 *arg5*  
 Beşinci olay işleyicisi bağımsız.  
  
 *arg6*  
 Altıncı olay işleyicisi bağımsız değişken.  
  
 *arg7*  
 Yedinci olay işleyicisi bağımsız değişken.  
  
 *arg8*  
 Sekizinci olay işleyicisi bağımsız değişken.  
  
 *arg9*  
 Dokuzuncu olay işleyicisi bağımsız değişken.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** event.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Ayrıca Bkz.
 [EventSource Sınıfı](../windows/eventsource-class.md)