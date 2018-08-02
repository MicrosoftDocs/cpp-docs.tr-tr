---
title: CreateClassFactory işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreateClassFactory
dev_langs:
- C++
helpviewer_keywords:
- CreateClassFactory function
ms.assetid: 772d5d1b-8872-4745-81ca-521a39564713
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ff853fce39b2052b82df921bf6743b0db361408c
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461331"
---
# <a name="createclassfactory-function"></a>CreateClassFactory İşlevi
Belirtilen sınıfın örneklerini oluşturan bir Üreteç oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
template<typename Factory>  
inline HRESULT STDMETHODCALLTYPE CreateClassFactory(  
   _In_ unsigned int *flags,   
   _In_ const CreatorMap* entry,   
   REFIID riid,   
   _Outptr_ IUnknown **ppFactory  
) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 *bayrakları*  
 Bir veya daha fazla birleşimi [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) sabit listesi değerleri.  
  
 *entry*  
 İşaretçi bir [CreatorMap](../windows/creatormap-structure.md) parametresi başlatma ve kayıt bilgilerini içeren *riid*.  
  
 *riid*  
 Başvuru için bir arabirim kimliği.  
  
 *ppFactory*  
 Bu işlem bir sınıf üreteci için bir işaretçi başarıyla tamamlanırsa.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK; Aksi takdirde, HRESULT hata olduğunu gösterir.  
  
## <a name="remarks"></a>Açıklamalar  
 Assert hata durumunda yayıldığını şablon parametresi *Fabrika* arabiriminden türetilen değil `IClassFactory`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Wrappers::Details Ad Alanı](../windows/microsoft-wrl-wrappers-details-namespace.md)