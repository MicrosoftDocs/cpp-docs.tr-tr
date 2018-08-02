---
title: CreateActivationFactory işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreateActivationFactory
dev_langs:
- C++
helpviewer_keywords:
- CreateActivationFactory function
ms.assetid: a1a53e04-6757-4faf-a4c8-ecf06e43b959
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fd2f65bb86cdd77d4e285cee5603416fa629f940
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39466354"
---
# <a name="createactivationfactory-function"></a>CreateActivationFactory İşlevi
Windows çalışma zamanı tarafından etkinleştirilebilen belirtilen sınıf örneklerini oluşturan bir Üreteç oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
template<typename Factory>  
   inline HRESULT STDMETHODCALLTYPE CreateActivationFactory(  
      _In_ unsigned int *flags,        _In_ const CreatorMap* entry,   
      REFIID riid,   
     _Outptr_ IUnknown **ppFactory) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 *bayrakları*  
 Bir veya daha fazla birleşimi [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) sabit listesi değerleri.  
  
 *entry*  
 İşaretçi bir [CreatorMap](../windows/creatormap-structure.md) parametresi başlatma ve kayıt bilgilerini içeren *riid*.  
  
 *riid*  
 Başvuru için bir arabirim kimliği.  
  
 *ppFactory*  
 Bu işlem bir etkinleştirme fabrikası için bir işaretçi başarıyla tamamlanırsa.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK; Aksi takdirde, HRESULT hata olduğunu gösterir.  
  
## <a name="remarks"></a>Açıklamalar  
 Assert hata durumunda yayıldığını şablon parametresi *Fabrika* arabiriminden türetilen değil `IActivationFactory`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Wrappers::Details Ad Alanı](../windows/microsoft-wrl-wrappers-details-namespace.md)