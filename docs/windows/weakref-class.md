---
title: WeakRef sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef
dev_langs:
- C++
helpviewer_keywords:
- WeakRef class
ms.assetid: 572be703-c641-496c-8af5-ad6164670ba1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 96aa076bb8285154f3b340e9e39ae36ed621522f
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42612739"
---
# <a name="weakref-class"></a>WeakRef Sınıfı

Temsil eden bir *zayıf başvuru* yalnızca Windows çalışma zamanı tarafından değil klasik COM kullanılabilir Zayıf bir başvuru erişilebilir olmayabilir veya bir nesneyi temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class WeakRef : public ComPtr<IWeakReference>
```

## <a name="remarks"></a>Açıklamalar

A **WeakRef** nesne tutan bir *güçlü başvuru*, bir nesne ile ilişkili ve geçerli ya da geçersiz olabilir. Çağrı `As()` veya `AsIID()` güçlü bir başvuru almak için yöntemi. Güçlü Başvuru geçerli olduğunda, ilişkili nesne erişebilir. Güçlü Başvuru olduğunda geçersiz (**nullptr**), ilişkili nesne erişilemez.

A **WeakRef** nesne genellikle, varlığı harici bir iş parçacığı ya da uygulama tarafından denetlenen bir nesneyi göstermek için kullanılır. Örneğin, oluşturun bir **WeakRef** nesneden bir dosya nesnesine bir başvuru. Dosya açıkken, güçlü başvuru geçerli değil. Ancak, dosya kapalıysa, güçlü başvuru geçersiz hale gelir.

Davranış değişikliği olduğunu unutmayın [olarak](../windows/weakref-as-method.md), [Asııd](../windows/weakref-asiid-method.md) ve [CopyTo](../windows/weakref-copyto-method.md) Windows 10 SDK'sı yöntemleri. Daha önce bu yöntemlerin herhangi biriyle çağrıldıktan sonra WeakRef için iade edilemedi **nullptr** güçlü bir başvuru başarıyla, aşağıdaki kodda gösterildiği gibi edinilen olmadığını belirlemek için:

```cpp
WeakRef wr;
strongComptrRef.AsWeak(&wr);

// Now suppose that the object strongComPtrRef points to no longer exists
// and the following code tries to get a strong ref from the weak ref:
ComPtr<ISomeInterface> strongRef;
HRESULT hr = wr.As(&strongRef);

// This check won't work with the Windows 10 SDK version of the library.
// Check the input pointer instead.
if(wr == nullptr)  
{
    wprintf(L"Couldn’t get strong ref!");
}
```

Yukarıdaki kod, Windows 10 SDK'sı kullanırken çalışmaz (veya üzeri). Bunun yerine, için geçirilen işaretçiyi denetleyin **nullptr**.

```cpp
if (strongRef == nullptr)  
{
    wprintf(L"Couldn't get strong ref!");
}
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[WeakRef::WeakRef Oluşturucusu](../windows/weakref-weakref-constructor.md)|Yeni bir örneğini başlatır **WeakRef** sınıfı.|
|[WeakRef::~WeakRef Yıkıcısı](../windows/weakref-tilde-weakref-destructor.md)|Geçerli örneğinin başlatmasını geri alır **WeakRef** sınıfı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[WeakRef::As Metodu](../windows/weakref-as-method.md)|Belirtilen ayarlar `ComPtr` belirtilen arabirim temsil etmek için işaretçi parametresi.|
|[WeakRef::AsIID Metodu](../windows/weakref-asiid-method.md)|Belirtilen ayarlar `ComPtr` belirtilen arabirim kimliği. temsil etmek için işaretçi parametresi|
|[WeakRef::CopyTo Metodu](../windows/weakref-copyto-method.md)|Bir işaretçi bir arabirim için kullanılabiliyorsa, belirtilen bir işaretçi değişkenine atar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[WeakRef::operator& İşleci](../windows/weakref-operator-ampersand-operator.md)|Döndürür bir `ComPtrRef` geçerli temsil eden nesne **WeakRef** nesne.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ComPtr`

`WeakRef`

## <a name="requirements"></a>Gereksinimler

**Başlık:** client.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)