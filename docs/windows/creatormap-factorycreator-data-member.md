---
title: "CreatorMap::factoryCreator veri üyesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Details::CreatorMap::factoryCreator
dev_langs: C++
helpviewer_keywords: factoryCreator data member
ms.assetid: c9aac363-8f38-4cfd-9605-1e6ac74c5097
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6e80b63a82a37350595e673e5f57b9e508d0bf9a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="creatormapfactorycreator-data-member"></a>CreatorMap::factoryCreator Veri Üyesi
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT (*factoryCreator)(  
   unsigned int* currentflags,  
   const CreatorMap* entry,  
   REFIID iidClassFactory,  
 IUnknown** factory);  
```  
  
## <a name="parameters"></a>Parametreler  
 `currentflags`  
 Aşağıdakilerden birini [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) numaralandırıcılar.  
  
 `entry`  
 CreatorMap.  
  
 `iidClassFactory`  
 Bir sınıf üreteci arabirimi kimliği.  
  
 `factory`  
 İşlem tamamlandığında, bir sınıf fabrikası adresidir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde, HRESULT hata gösterir.  
  
## <a name="remarks"></a>Açıklamalar  
 Belirtilen CreatorMap için bir üreteci oluşturur.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CreatorMap yapısı](../windows/creatormap-structure.md)   
 [Microsoft::wrl:: details Namespace](../windows/microsoft-wrl-details-namespace.md)