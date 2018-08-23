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
ms.openlocfilehash: e6088ec152d7c91cb06c17c9dae2698f2fd983d1
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42610196"
---
# <a name="activationfactory-class"></a>ActivationFactory Sınıfı

Windows çalışma zamanı tarafından etkinleştirilmesi bir veya daha fazla sınıflar sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <
   typename I0 = Details::Nil,
   typename I1 = Details::Nil,
   typename I2 = Details::Nil
>
class ActivationFactory : public Details::RuntimeClass<typename Details::InterfaceListHelper<IActivationFactory, I0, I1, I2, Details::Nil>::TypeT, RuntimeClassFlags<WinRt | InhibitWeakReference>, false>;
```

### <a name="parameters"></a>Parametreler

*I0*  
Sıfırıncı arabirim.

*I1*  
İlk arabirim.

*I2*  
İkinci arabirim.

## <a name="remarks"></a>Açıklamalar

**ActivationFactory** kayıt yöntemleri ve için temel işlevleri sağlayan `IActivationFactory` arabirimi. **ActivationFactory** ayrıca özel Üreteç uygulaması girmenize olanak tanır.

Aşağıdaki kod parçası bildirmelerine ActivationFactory kullanılması gösterilmektedir.

[!code-cpp[wrl-microsoft__wrl__activationfactory#1](../windows/codesnippet/CPP/activationfactory-class_1.cpp)]

Aşağıdaki kod parçası nasıl kullanılacağını gösterir [uygular](../windows/implements-structure.md) yapısı üçten fazla arabirim kimliklerini belirtin.

`struct MyFactory : ActivationFactory<Implements<I1, I2, I3>, I4, I5>;`

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[ActivationFactory::ActivationFactory Oluşturucusu](../windows/activationfactory-activationfactory-constructor.md)|Başlatır **ActivationFactory** sınıfı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[ActivationFactory::AddRef Metodu](../windows/activationfactory-addref-method.md)|Geçerli başvuru sayısını artırır **ActivationFactory** nesne.|
|[ActivationFactory::GetIids Metodu](../windows/activationfactory-getiids-method.md)|Uygulanan arabirimi kimlikleri dizisini alır.|
|[ActivationFactory::GetRuntimeClassName Metodu](../windows/activationfactory-getruntimeclassname-method.md)|Nesnenin çalışma zamanı sınıf adını alır Geçerli **ActivationFactory** başlatır.|
|[ActivationFactory::GetTrustLevel Metodu](../windows/activationfactory-gettrustlevel-method.md)|Nesne güven düzeyini alır Geçerli **ActivationFactory** başlatır.|
|[ActivationFactory::QueryInterface Metodu](../windows/activationfactory-queryinterface-method.md)|Belirtilen arabirim işaretçisi alır.|
|[ActivationFactory::Release Metodu](../windows/activationfactory-release-method.md)|Başvuru sayma geçerli azaltır **ActivationFactory** nesne.|

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