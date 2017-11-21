---
title: "ComPtr::CopyTo yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::ComPtr::CopyTo
dev_langs: C++
helpviewer_keywords: CopyTo method
ms.assetid: 8801bc49-6db4-4393-a55f-a701ae3b8718
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 184abddec5099eff20f75531fe240886841e9814
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="comptrcopyto-method"></a>ComPtr::CopyTo Yöntemi
Kopya geçerli ya da belirtilen arabirimi belirtilen işaretçisine bu ComPtr ile ilişkili.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT CopyTo(  
   _Deref_out_ InterfaceType** ptr  
);  
  
HRESULT CopyTo(  
   REFIID riid,  
   _Deref_out_ void** ptr  
) const;  
template<  
   typename U  
>  
  
HRESULT CopyTo(  
   _Deref_out_ U** ptr  
) const;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `U`  
 Tür adı.  
  
 `ptr`  
 Bu işlem tamamlandığında, istenen arabirimi için bir işaretçi.  
  
 `riid`  
 Bir arabirim kimliği  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde, HRESULT örtük QueryInterface işlemi neden başarısız gösterir.  
  
## <a name="remarks"></a>Açıklamalar  
 İlk işlev bu ComPtr ile ilişkili arabiriminin bir işaretçi bir kopyasını döndürür. Bu işlev, her zaman S_OK döndürür.  
  
 İkinci işlev tarafından belirtilen arabirim için bu ComPtr ilişkili arabirimindeki QueryInterface işlemi gerçekleştirir `riid` parametresi.  
  
 QueryInterface işlemi için temel alınan arabiriminin bu ComPtr ilişkili arabirimde üçüncü işlevi gerçekleştirir `U` parametresi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ComPtr sınıfı](../windows/comptr-class.md)