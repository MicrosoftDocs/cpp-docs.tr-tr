---
title: Module::GetActivationFactory metodu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GetActivationFactory
dev_langs:
- C++
helpviewer_keywords:
- GetActivationFactory method
ms.assetid: 59da8844-072e-414b-b89c-1db1cc4fd81d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e41b90ea56f65665ccdaff0fe4dceff292d1cdcf
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608111"
---
# <a name="modulegetactivationfactory-method"></a>Module::GetActivationFactory Metodu
Etkinleştirme fabrikası için modülü alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
WRL_NOTHROW HRESULT GetActivationFactory(  
   _In_ HSTRING pActivatibleClassId,  
   _Deref_out_ IActivationFactory **ppIFactory,  
   wchar_t* serverName = nullptr  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 *pActivatibleClassId*  
 Laboratuvardaki bir çalışma zamanı sınıf.  
  
 *ppIFactory*  
 Belirtilen çalışma zamanı sınıfının IActivationFactory.  
  
 *SunucuAdı*  
 Sınıf üreteçlerini geçerli modüldeki bir alt kümesi adı. Kullanılan sunucu adını belirtmek [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md) makro veya belirtin **nullptr** varsayılan sunucu adı alınamıyor.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK; Aksi takdirde GetActivationFactory tarafından döndürülen HRESULT.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Modül Sınıfı](../windows/module-class.md)  
 [ActivatableClass Makroları](../windows/activatableclass-macros.md)