---
title: ActivationFactory sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory
dev_langs:
- C++
helpviewer_keywords:
- ActivationFactory class
ms.assetid: 5faddf1f-43b6-4f8a-97de-8c9d3ae1e1ff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6775e9466ed337a070b6a234a4d65bb949a009e4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33857961"
---
# <a name="activationfactory-class"></a>ActivationFactory Sınıfı
Windows çalışma zamanı tarafından etkinleştirilecek bir veya daha fazla sınıfları sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <  
   typename I0 = Details::Nil,  
   typename I1 = Details::Nil,  
   typename I2 = Details::Nil  
>  
class ActivationFactory : public Details::RuntimeClass<typename Details::InterfaceListHelper<IActivationFactory, I0, I1, I2, Details::Nil>::TypeT, RuntimeClassFlags<WinRt | InhibitWeakReference>, false>;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `I0`  
 Sıfırıncı arabirimi.  
  
 `I1`  
 İlk arabirimi.  
  
 `I2`  
 İkinci arabirim.  
  
## <a name="remarks"></a>Açıklamalar  
 ActivationFactory kayıt yöntemleri ve IActivationFactory arabirimi için temel işlevleri sağlar. ActivationFactory özel Üreteç uygulaması vermenizi sağlar.  
  
 Aşağıdaki kod parçası, sembolik olarak nasıl ActivationFactory kullanılacağı gösterilmektedir.  
  
 [!code-cpp[wrl-microsoft__wrl__activationfactory#1](../windows/codesnippet/CPP/activationfactory-class_1.cpp)]  
  
 Aşağıdaki kod parçası nasıl kullanılacağını gösterir [uygulayan](../windows/implements-structure.md) yapısı üçten fazla arabirim kimlikleri belirtin.  
  
 `struct MyFactory : ActivationFactory<Implements<I1, I2, I3>, I4, I5>;`  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ActivationFactory::ActivationFactory Oluşturucusu](../windows/activationfactory-activationfactory-constructor.md)|ActivationFactory sınıfı başlatır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ActivationFactory::AddRef Metodu](../windows/activationfactory-addref-method.md)|Geçerli ActivationFactory nesne başvurusu sayısını artırır.|  
|[ActivationFactory::GetIids Metodu](../windows/activationfactory-getiids-method.md)|Uygulanan arabirimi kimlikleri dizisini alır.|  
|[ActivationFactory::GetRuntimeClassName Metodu](../windows/activationfactory-getruntimeclassname-method.md)|Geçerli ActivationFactory başlatır nesne çalışma zamanı sınıf adını alır.|  
|[ActivationFactory::GetTrustLevel Metodu](../windows/activationfactory-gettrustlevel-method.md)|Geçerli ActivationFactory başlatır nesne güven düzeyini alır.|  
|[ActivationFactory::QueryInterface Metodu](../windows/activationfactory-queryinterface-method.md)|Belirtilen arabirim için bir işaretçi alır.|  
|[ActivationFactory::Release Metodu](../windows/activationfactory-release-method.md)|Başvurusu geçerli ActivationFactory nesne sayısını azaltır.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `I0`  
  
 `ChainInterfaces`  
  
 `I0`  
  
 `RuntimeClassBase`  
  
 `ImplementsHelper`  
  
 `DontUseNewUseMake`  
  
 `RuntimeClassFlags`  
  
 `RuntimeClassBaseT`  
  
 `RuntimeClass`  
  
 `ActivationFactory`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)