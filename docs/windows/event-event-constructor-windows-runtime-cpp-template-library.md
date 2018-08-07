---
title: Event::Event yapıcı (Windows çalışma zamanı C++ Şablon kitaplığı) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Event::Event
dev_langs:
- C++
ms.assetid: 21495297-9612-4095-9256-16e168cc0021
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: de0f68ee3e27f2ac3a7f87e64489a05a16dcdc91
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39571418"
---
# <a name="eventevent-constructor-windows-runtime-c-template-library"></a>Event::Event Yapıcı (Windows Çalışma Zamanı C++ Şablon Kitaplığı)
Olay sınıfının yeni bir örneğini başlatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
explicit Event(  
   HANDLE h = HandleT::Traits::GetInvalidValue()  
);  
WRL_NOTHROW Event(  
   _Inout_ Event&& h  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *h*  
 Bir olay tanıtıcısı olarak ekleyin. Varsayılan olarak, *h* değerine ayarlanır **nullptr**.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Olay Sınıfı (Windows Çalışma Zamanı C++ Şablon Kitaplığı)](../windows/event-class-windows-runtime-cpp-template-library.md)