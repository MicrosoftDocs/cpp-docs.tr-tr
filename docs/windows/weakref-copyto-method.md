---
title: WeakRef::CopyTo yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef::CopyTo
dev_langs:
- C++
helpviewer_keywords:
- CopyTo method
ms.assetid: f83de6da-b3d4-41a6-9845-cd725ecf3b75
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 817d984e995e7ac33ba80f978a282a8c0bac3e4f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33890641"
---
# <a name="weakrefcopyto-method"></a>WeakRef::CopyTo Yöntemi
Bir işaretçi bir arabirim için mevcut ise, belirtilen işaretçi değişkenine atar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT CopyTo(  
   REFIID riid,  
   _Deref_out_ IInspectable** ptr  
);  
  
template<typename U>  
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