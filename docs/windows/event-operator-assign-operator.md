---
title: "Event::operator = işleci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::Event::operator=
dev_langs: C++
helpviewer_keywords: operator= operator
ms.assetid: d8fe9820-8856-4899-9553-56226bdc4945
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b6001462a5618251acc838d1d8fad3bd93968c81
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="eventoperator-operator"></a>Event::operator= İşleci
Geçerli olay örneği belirtilen olay referansı atar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
WRL_NOTHROW Event& operator=(  
   _Inout_ Event&& h  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `h`  
 Bir rvalue-bir olay örneğine başvuru.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Geçerli olay örneği için bir işaretçi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Olay sınıfı (Windows çalışma zamanı C++ Şablon kitaplığı)](../windows/event-class-windows-runtime-cpp-template-library.md)