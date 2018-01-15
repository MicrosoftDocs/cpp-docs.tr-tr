---
title: "Implementshelper yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::ImplementsHelper
dev_langs: C++
helpviewer_keywords: ImplementsHelper structure
ms.assetid: b857ba80-81bd-4e53-92b6-210991954243
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1a51de59278e476be1e99b60ef1b0ab8a6e3f3cd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="implementshelper-structure"></a>ImplementsHelper Yapısı
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <  
   typename RuntimeClassFlagsT,  
   typename ILst,  
   bool IsDelegateToClass  
>  
friend struct Details::ImplementsHelper;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `RuntimeClassFlagsT`  
 Bir veya daha fazla belirten bayrakları alanı [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) numaralandırıcılar.  
  
 `ILst`  
 Arabirim kimlikleri listesi.  
  
 `IsDelegateToClass`  
 Belirtin `true` uygular, geçerli örneğini bir taban sınıf içinde ilk arabirimi kimliğinin ise `ILst`; Aksi halde, `false`.  
  
## <a name="remarks"></a>Açıklamalar  
 Uygulama yardımcı [uygulayan](../windows/implements-structure.md) yapısı.  
  
 Bu şablon arabirimleri listesine erişir ve temel sınıflar ve QueryInterface etkinleştirmek gerekli olan bilgileri olarak ekler.  
  
## <a name="members"></a>Üyeler  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `ImplementsHelper`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (Windows çalışma zamanı kitaplığı)](http://msdn.microsoft.com/en-us/00000000-0000-0000-0000-000000000000)   
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)