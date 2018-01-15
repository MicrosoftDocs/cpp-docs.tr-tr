---
title: "Module::GetActivationFactory yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Module::GetActivationFactory
dev_langs: C++
helpviewer_keywords: GetActivationFactory method
ms.assetid: 59da8844-072e-414b-b89c-1db1cc4fd81d
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5d5c5ca4d470f52ff9dde862cc99b10a3459cd0c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="modulegetactivationfactory-method"></a>Module::GetActivationFactory Metodu
Modül için bir etkinleştirme üreteci alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
WRL_NOTHROW HRESULT GetActivationFactory(  
   _In_ HSTRING pActivatibleClassId,  
   _Deref_out_ IActivationFactory **ppIFactory,  
   wchar_t* serverName = nullptr  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pActivatibleClassId`  
 Bir çalışma zamanı sınıf IID.  
  
 `ppIFactory`  
 Belirtilen çalışma zamanı sınıf için IActivationFactory.  
  
 `serverName`  
 Sınıf oluşturucuları geçerli modülünde bir kısmı adı. Kullanılan sunucu adını belirtmek [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md) makro veya belirtin `nullptr` varsayılan sunucu adı alınamıyor.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde, GetActivationFactory tarafından döndürülen HRESULT.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[Modül sınıfı](../windows/module-class.md) [ActivatableClass makroları](../windows/activatableclass-macros.md)