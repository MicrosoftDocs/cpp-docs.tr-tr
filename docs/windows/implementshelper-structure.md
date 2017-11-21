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
ms.openlocfilehash: 5bb328b93231646cd3b0ceeea42382d8f8857e21
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Microsoft::wrl:: details Namespace](../windows/microsoft-wrl-details-namespace.md)