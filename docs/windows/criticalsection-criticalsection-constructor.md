---
title: "CriticalSection::CriticalSection Oluşturucusu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::CriticalSection::CriticalSection
dev_langs: C++
helpviewer_keywords: CriticalSection, constructor
ms.assetid: 930b89be-4d74-46bd-8879-5dd4d15bcbd0
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bf4e9cd4d4fde31f1809e7d583e662188558d5b3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="criticalsectioncriticalsection-constructor"></a>CriticalSection::CriticalSection Oluşturucusu
Mutex nesnesine benzer, ancak yalnızca tek bir işlem iş parçacığı tarafından kullanılan bir eşitleme nesnesini başlatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
explicit CriticalSection(  
   ULONG spincount = 0  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `spincount`  
 Kritik bölüm nesnesi için döndürme sayısı. Varsayılan değer 0’dır.  
  
## <a name="remarks"></a>Açıklamalar  
 Crticial bölümler ve spincounts hakkında daha fazla bilgi için bkz: **InitializeCriticalSectionAndSpinCount** Windows API belgelerine eşitleme bölümünde işlevi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CriticalSection sınıfı](../windows/criticalsection-class.md)