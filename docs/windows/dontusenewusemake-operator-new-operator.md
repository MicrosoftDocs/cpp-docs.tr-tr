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
ms.openlocfilehash: 5424108692bd97bdea890aff85ab7428276dd430
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Microsoft::wrl:: details Namespace](../windows/microsoft-wrl-details-namespace.md)