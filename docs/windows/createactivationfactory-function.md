---
title: "CreateActivationFactory işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Details::CreateActivationFactory
dev_langs: C++
helpviewer_keywords: CreateActivationFactory function
ms.assetid: a1a53e04-6757-4faf-a4c8-ecf06e43b959
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e36a76de38290cfd1571f1c5743745561f14e438
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="createactivationfactory-function"></a>CreateActivationFactory İşlevi
Windows çalışma zamanı tarafından etkinleştirilebilir belirtilen sınıfının örnekleri oluşturan bir Üreteç oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
template<typename Factory>  
   inline HRESULT STDMETHODCALLTYPE CreateActivationFactory(  
      _In_ unsigned int *flags,        _In_ const CreatorMap* entry,   
      REFIID riid,   
     _Outptr_ IUnknown **ppFactory) throw();  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 `flags`  
 Bir veya daha fazla bileşimini [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) numaralandırma değerleri.  
  
 `entry`  
 İşaretçi bir [CreatorMap](../windows/creatormap-structure.md) parametresi başlatma ve kayıt bilgilerini içeren `riid`.  
  
 `riid`  
 Bir arabirim kimliği başvurusu  
  
 `ppFactory`  
 Bu işlem bir etkinleştirme üreteci için bir işaretçi başarıyla tamamlarsa.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde, HRESULT hata gösterir.  
  
## <a name="remarks"></a>Açıklamalar  
 Assert hata durumunda yayılan şablon parametresi `Factory` IActivationFactory arabiriminden türevi değil.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Wrappers::details Namespace](../windows/microsoft-wrl-wrappers-details-namespace.md)