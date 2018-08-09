---
title: Module::RegisterWinRTObject yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::RegisterWinRTObject
dev_langs:
- C++
helpviewer_keywords:
- RegisterWinRTObject method
ms.assetid: a2782c9c-b9c5-4e4b-9c8d-ef513aea20c5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5b5605b68c569d4579324b51eaad42b1e9532011
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40017421"
---
# <a name="moduleregisterwinrtobject-method"></a>Module::RegisterWinRTObject Yöntemi
Diğer uygulamalar için bağlanabilmesi için bir veya daha fazla Windows çalışma zamanı nesneleri kaydeder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT RegisterWinRTObject(const wchar_t* serverName,  
   wchar_t** activatableClassIds,  
   WINRT_REGISTRATION_COOKIE* cookie,  
   unsigned int count)  
```  
  
### <a name="parameters"></a>Parametreler  
 *SunucuAdı*  
 Bu işlemden etkilenen nesneler kümesini belirten bir ad.  
  
 *activatableClassIds*  
 Kaydedilecek etkinleştirilebilir CLSID dizisi.  
  
 *Tanımlama bilgisi*  
 Kaydedilen sınıf nesneleri tanımlayan bir değer. Bu değer daha sonra kaydı iptal etmek için kullanılır.  
  
 *Sayısı*  
 Kaydedilecek nesne sayısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK; Aksi takdirde bir hata HRESULT nedenini belirten CO_E_OBJISREG gibi işlem başarısız oldu.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Ayrıca Bkz.
 [Modül Sınıfı](../windows/module-class.md)