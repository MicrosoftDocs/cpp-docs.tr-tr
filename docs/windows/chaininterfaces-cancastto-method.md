---
title: "Chainınterfaces::cancastto yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::ChainInterfaces::CanCastTo
dev_langs: C++
helpviewer_keywords: CanCastTo method
ms.assetid: 8be44875-53ed-494b-91a0-0f8e399685bb
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 99738f9c5335ede5dafe60e35b3104951f5fb556
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="chaininterfacescancastto-method"></a>ChainInterfaces::CanCastTo Yöntemi
Belirtilen arabirim kimliği her varsayılan olmayan şablon parametreleri tarafından tanımlanan özelleştirmeleri içerip içermeyeceğini gösterir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
__forceinline bool CanCastTo(  
   REFIID riid,  
   _Deref_out_ void **ppv  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `riid`  
 Bir arabirim kimliği  
  
 `ppv`  
 Başarılı bir şekilde atama son arabirimi kimliği için bir işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `true`tüm yayın operasyonlar başarılıysa; Aksi takdirde `false`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Chainınterfaces yapısı](../windows/chaininterfaces-structure.md)