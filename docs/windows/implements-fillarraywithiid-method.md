---
title: "Implements::fillarraywithıid yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Implements::FillArrayWithIid
dev_langs: C++
helpviewer_keywords: FillArrayWithIid method
ms.assetid: b2e62e3f-0ab9-4c70-aad7-856268544f44
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a53a7eb9a05e1f4583c49b42fa10efdf1ee815ab
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="implementsfillarraywithiid-method"></a>Implements::FillArrayWithIid Yöntemi
Belirtilen dizi öğesi içinde geçerli sıfırıncı şablon parametresi tarafından belirtilen arabirim kimliği ekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
__forceinline static void FillArrayWithIid(  
   unsigned long &index,  
   _In_ IID* iids  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `index`  
 Bu işlem için başlangıç dizi öğesi gösteren sıfır tabanlı dizini. Bu işlem tamamlandığında `index` 1 artırılır.  
  
 `iids`  
 IID türünde bir dizi.  
  
## <a name="remarks"></a>Açıklamalar  
 İç yardımcı işlevi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Implements yapısı](../windows/implements-structure.md)