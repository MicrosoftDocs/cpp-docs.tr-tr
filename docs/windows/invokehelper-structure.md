---
title: Invokehelper yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::InvokeHelper
dev_langs:
- C++
helpviewer_keywords:
- InvokeHelper structure
ms.assetid: 555ad2bc-4dd6-4e65-a2e2-1242c395f0e5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0ffef0c6a55116bf3a228d7d5da4bd698607d7fa
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46431040"
---
# <a name="invokehelper-structure"></a>InvokeHelper Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template<
   typename TDelegateInterface,
   typename TCallback,
   unsigned int argCount
>
struct InvokeHelper;
template<
   typename TDelegateInterface,
   typename TCallback
>
struct InvokeHelper<TDelegateInterface, TCallback, 0> : public Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;
template<
   typename TDelegateInterface,
   typename TCallback
>
struct InvokeHelper<TDelegateInterface, TCallback, 1> : public Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;
template<
   typename TDelegateInterface,
   typename TCallback
>
struct InvokeHelper<TDelegateInterface, TCallback, 2> : public Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;
template<
   typename TDelegateInterface,
   typename TCallback
>
struct InvokeHelper<TDelegateInterface, TCallback, 3> : public Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;
template<
   typename TDelegateInterface,
   typename TCallback
>
struct InvokeHelper<TDelegateInterface, TCallback, 4> : Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;
template<
   typename TDelegateInterface,
   typename TCallback
>
struct InvokeHelper<TDelegateInterface, TCallback, 5> : Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;
template<
   typename TDelegateInterface,
   typename TCallback
>
struct InvokeHelper<TDelegateInterface, TCallback, 6> : Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;
template<
   typename TDelegateInterface,
   typename TCallback
>
struct InvokeHelper<TDelegateInterface, TCallback, 7> : Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;
template<
   typename TDelegateInterface,
   typename TCallback
>
struct InvokeHelper<TDelegateInterface, TCallback, 8> : Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;
template<
   typename TDelegateInterface,
   typename TCallback
>
struct InvokeHelper<TDelegateInterface, TCallback, 9> : Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;
```

### <a name="parameters"></a>Parametreler

*TDelegateInterface*<br/>
*TCallback*  
Olay işleyici işlevi türü.

*argCount*<br/>
Bağımsız değişken sayısı bir **Invokehelper** özelleştirmesi.

## <a name="remarks"></a>Açıklamalar

Bir uygulamasını sağlar `Invoke()` tabanlı yöntemini belirtilen sayı ve bağımsız değişken türü.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`Traits`|Her olay işleyicisi bağımsız değişken türünü tanımlayan sınıf için bir eşanlamlı.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[InvokeHelper::InvokeHelper Oluşturucusu](../windows/invokehelper-invokehelper-constructor.md)|Yeni bir örneğini başlatır **Invokehelper** sınıfı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[InvokeHelper::Invoke Metodu](../windows/invokehelper-invoke-method.md)|İmzası olan, belirtilen sayıda bağımsız değişken içeren olay işleyicisini çağırır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[InvokeHelper::callback_ Veri Üyesi](../windows/invokehelper-callback-data-member.md)|Bir olay oluştuğunda çağrılacak olay işleyicisini temsil eder.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`InvokeHelper`

## <a name="requirements"></a>Gereksinimler

**Başlık:** event.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)