---
title: "DontUseNewUseMake::operator new işleci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::DontUseNewUseMake::operator new
dev_langs: C++
helpviewer_keywords: operator new operator
ms.assetid: 6af07a0d-2271-430c-9d9b-5a4223fed049
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ea5cfa85dcf2873dcb8fe287e251511e3e48dbb8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="dontusenewusemakeoperator-new-operator"></a>DontUseNewUseMake::operator new İşleci
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void* operator new(  
   size_t,  
   _In_ void* placement  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `__unnamed0`  
 Bir adlandırılmamış parametre ayrılacak bellek bayt sayısını belirtir.  
  
 `placement`  
 Ayrılacak türü.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşleç aşırı yüklemesi, ek bağımsız değişkenler geçirmek için bir yol sağlar `new`.  
  
## <a name="remarks"></a>Açıklamalar  
 İşleç aşırı yüklemeler `new` ve RuntimeClass içinde kullanılan engeller.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DontUseNewUseMake sınıfı](../windows/dontusenewusemake-class.md)   
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)