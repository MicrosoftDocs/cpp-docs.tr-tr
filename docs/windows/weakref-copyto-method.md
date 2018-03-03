---
title: "WeakRef::CopyTo yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef::CopyTo
dev_langs:
- C++
helpviewer_keywords:
- CopyTo method
ms.assetid: f83de6da-b3d4-41a6-9845-cd725ecf3b75
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5b0114a9768fbea12a5b98f51911267cb24b0b43
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="weakrefcopyto-method"></a>WeakRef::CopyTo Yöntemi
Bir işaretçi bir arabirim için mevcut ise, belirtilen işaretçi değişkenine atar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT CopyTo(  
   REFIID riid,  
   _Deref_out_ IInspectable** ptr  
);  
  
template<  
   typename U  
>  
HRESULT CopyTo(  
   _Deref_out_ U** ptr  
);  
  
HRESULT CopyTo(  
   _Deref_out_ IWeakReference** ptr  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `U`  
 İşaretçi Iınspectable arabirim. Bir hata durumunda yayılan `U` Iınspectable türetilmemiş.  
  
 `riid`  
 Bir arabirim kimliği Bir hata durumunda yayılan `riid` türetilmedi **IWeakReference**.  
  
 `ptr`  
 Iınspectable veya IWeakReference karakteriyle dolaylı bir işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde, HRESULT hata açıklar. Daha fazla bilgi için açıklamalar bakın.  
  
## <a name="remarks"></a>Açıklamalar  
 S_OK dönüş değeri, bu işlemi başarılı oldu ancak zayıf başvuru güçlü bir başvuru çözümlendiği göstermez anlamına gelir. Bu parametrenin S_OK döndürülürse, test `p` güçlü bir başvuru; diğer bir deyişle, parametre `p` eşit değil `nullptr`.  
  
 Windows 10 SDK'sı başlayarak, bu yöntem WeakRef örneği ayarlanmamışsa `nullptr` zayıf başvuru edinilemedi, bu nedenle, kaçının için WeakRef denetler kod denetlenirken hata `nullptr`. Bunun yerine, denetleme `ptr` için `nullptr`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [WeakRef Sınıfı](../windows/weakref-class.md)