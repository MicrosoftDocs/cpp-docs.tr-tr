---
title: "ComPtrRef::operator * işleci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::Details::ComPtrRef::operator*
dev_langs: C++
helpviewer_keywords: operator* operator
ms.assetid: 0287ca7a-4ce1-47f7-bab6-714fca3e04bb
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 543f0099a3c6b60d8e6ec289ff560b1ffc4169e2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="comptrrefoperator-operator"></a>ComPtrRef::operator* İşleci
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
InterfaceType* operator *();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Geçerli ComPtrRef nesnesinin temsil ettiği arabirimi işaretçisi.  
  
## <a name="remarks"></a>Açıklamalar  
 Geçerli ComPtrRef nesnesinin temsil ettiği arabirimi işaretçisine alır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ComPtrRef sınıfı](../windows/comptrref-class.md)   
 [Microsoft::wrl:: details Namespace](../windows/microsoft-wrl-details-namespace.md)