---
title: HANDLETraits::Close yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::Close
dev_langs:
- C++
helpviewer_keywords:
- Close method
ms.assetid: 3c631a7c-ccce-472a-b1da-aab8fa815c13
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 581c7b8447b800d9a3401cd76f3adc5ada25994d
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569836"
---
# <a name="handletraitsclose-method"></a>HANDLETraits::Close Yöntemi
Belirtilen tanıtıcı kapatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
inline static bool Close(  
   _In_ Type h  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 *h*  
 Kapatmak için tanıtıcı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 **doğru** , tanıtıcı *h* kapalı başarıyla; Aksi takdirde **false**.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [HANDLETraits Yapısı](../windows/handletraits-structure.md)