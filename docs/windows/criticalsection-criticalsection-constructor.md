---
title: CriticalSection::CriticalSection Oluşturucusu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::CriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CriticalSection, constructor
ms.assetid: 930b89be-4d74-46bd-8879-5dd4d15bcbd0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 866159a4b3cbacae8b7ad09154fb93707fe4baac
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39467358"
---
# <a name="criticalsectioncriticalsection-constructor"></a>CriticalSection::CriticalSection Oluşturucusu
Mutex nesnesine benzer, ancak yalnızca tek bir işlem iş parçacığı tarafından kullanılan bir eşitleme nesnesi başlatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
explicit CriticalSection(  
   ULONG spincount = 0  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *spincount*  
 Kritik bölüm nesnenin dönüş sayısı. Varsayılan değer 0’dır.  
  
## <a name="remarks"></a>Açıklamalar  
 Kritik bölümler ve spincounts hakkında daha fazla bilgi için bkz: `InitializeCriticalSectionAndSpinCount` işlevi **eşitleme** Windows API platformlarının bölümü.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CriticalSection Sınıfı](../windows/criticalsection-class.md)