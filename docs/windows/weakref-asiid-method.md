---
title: Weakref::asııd yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef::AsIID
dev_langs:
- C++
helpviewer_keywords:
- AsIID method
ms.assetid: 94e87309-32da-4dbb-8233-e77313a1f448
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 69108681b181d0b2fce20f9e30a009b6b93c2180
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="weakrefasiid-method"></a>WeakRef::AsIID Yöntemi
Belirtilen ComPtr işaretçi parametresi belirtilen arabirimi kimliğini temsil etmek için ayarlar  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT AsIID(  
   REFIID riid,  
   _Out_ ComPtr<IInspectable>* ptr  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `riid`  
 Bir arabirim kimliği  
  
 `ptr`  
 Bu işlem tamamlandığında, parametre temsil eden bir nesne `riid`.  
  
## <a name="return-value"></a>Dönüş Değeri  
  
-   Bu işlem başarılı olursa S_OK; Aksi takdirde, nedenini belirten bir HRESULT işlemi başarısız oldu, ve `ptr` ayarlanır `nullptr`.  
  
-   Bu işlem başarılı olur, ancak geçerli WeakRef nesne zaten yayımlandı S_OK. Parametre `ptr` ayarlanır `nullptr`.  
  
-   Bu işlem başarılı olur, ancak geçerli WeakRef nesne parametresinden türetilmemiş S_OK `riid`. Parametre `ptr` ayarlanır `nullptr`. (Açıklamalar daha fazla bilgi için bkz.)  
  
## <a name="remarks"></a>Açıklamalar  
 Bir hata durumunda yayılan parametresi `riid` Iınspectable türetilmemiş. Bu hata, dönüş değeri yerini alır.  
  
 İlk şablon kodunuzda kullanması gereken biçimidir. (Değil burada gösterilen, ancak üstbilgi dosyasında bildirilen) ikinci C++ dil özellikleri gibi destekleyen bir iç, yardımcı uzmanlık şablonudur [otomatik](../cpp/auto-cpp.md) kesintisi anahtar sözcüğü yazın.  
  
 Windows 10 SDK'sı başlayarak, bu yöntem WeakRef örneği ayarlanmamışsa `nullptr` zayıf başvuru edinilemedi, bu nedenle, kaçının için WeakRef denetler ve hata denetimi kodu `nullptr`. Bunun yerine, denetleme `ptr` için `nullptr`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [WeakRef Sınıfı](../windows/weakref-class.md)