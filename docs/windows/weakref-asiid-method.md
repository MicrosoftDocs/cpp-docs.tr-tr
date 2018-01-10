---
title: "Weakref::asııd yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::WeakRef::AsIID
dev_langs: C++
helpviewer_keywords: AsIID method
ms.assetid: 94e87309-32da-4dbb-8233-e77313a1f448
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8fdefa73ac14e807c5e4100fd81e1d931f4bf6e6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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