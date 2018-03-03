---
title: "HString::HString Oluşturucusu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::HString
dev_langs:
- C++
ms.assetid: 6da12785-ed01-4720-a004-667db60298f1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d13f532484cc071744b9b823546052d92c6f6b78
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="hstringhstring-constructor"></a>HString::HString Oluşturucusu
HString sınıfının yeni bir örneğini başlatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HString(HSTRING hstr = nullptr) throw();  
HString(HString&& other) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 `hstr`  
 Bir HSTRING tanıtıcısı.  
  
 `other`  
 Varolan bir HString nesne.  
  
## <a name="remarks"></a>Açıklamalar  
 İlk Oluşturucusu boş yeni bir HString nesnesini başlatır.  
  
 İkinci Oluşturucu, var olan değerin yeni HString nesnesine başlatır `other` parametresi ve ardından bozar `other` parametresi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [HString Sınıfı](../windows/hstring-class.md)