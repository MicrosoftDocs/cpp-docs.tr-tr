---
title: "CreateClassFactory işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Details::CreateClassFactory
dev_langs: C++
helpviewer_keywords: CreateClassFactory function
ms.assetid: 772d5d1b-8872-4745-81ca-521a39564713
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5ac438e233c675b6d650af83354edd36f877602d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="createclassfactory-function"></a>CreateClassFactory İşlevi
Belirtilen sınıf örnekleri oluşturan bir Üreteç oluşturur.  
  
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
 `flags`  
 Bir veya daha fazla bileşimini [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) numaralandırma değerleri.  
  
 `entry`  
 İşaretçi bir [CreatorMap](../windows/creatormap-structure.md) parametresi başlatma ve kayıt bilgilerini içeren `riid`.  
  
 `riid`  
 Bir arabirim kimliği başvurusu  
  
 `ppFactory`  
 Bu işlem bir üreteci için bir işaretçi başarıyla tamamlarsa.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde, HRESULT hata gösterir.  
  
## <a name="remarks"></a>Açıklamalar  
 Assert hata durumunda yayılan şablon parametresi `Factory` IClassFactory arabiriminden türevi değil.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Wrappers::details Namespace](../windows/microsoft-wrl-wrappers-details-namespace.md)