---
title: "Implements::cancastto yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Implements::CanCastTo
dev_langs: C++
helpviewer_keywords: CanCastTo method
ms.assetid: a8e85c7d-4dcd-446d-bebc-a97da46ce44a
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 83d217cb749c350da45bcae2159e6b46d03f68cc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="implementscancastto-method"></a>Implements::CanCastTo Yöntemi
Bir işaretçi belirtilen arabirime alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
__forceinline HRESULT CanCastTo(  
   REFIID riid,  
   _Deref_out_ void **ppv  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `riid`  
 Bir arabirim kimliği başvurusu  
  
 `ppv`  
 Başarılı, arayüzü için bir işaretçi olarak belirttiyseniz `riid`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde, HRESULT E_NOINTERFACE gibi hatayı gösterir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu QueryInterface işlemi gerçekleştiren bir iç yardımcı işlevdir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Implements yapısı](../windows/implements-structure.md)