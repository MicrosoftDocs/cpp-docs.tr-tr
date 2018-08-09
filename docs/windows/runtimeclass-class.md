---
title: RuntimeClass sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass
dev_langs:
- C++
helpviewer_keywords:
- RuntimeClass class
ms.assetid: d52f9d1a-98e5-41f2-a143-8fb629dd0727
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7f76695cfe3dcad0f5c835577aa4cc9b7cd3ec62
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40017649"
---
# <a name="runtimeclass-class"></a>RuntimeClass Sınıfı
Belirtilen Windows çalışma zamanı klasik COM ve zayıf başvuru desteği sağlar ve belirtilen arabirimlerden devralan WinRT veya COM bir sınıfı temsil eder.  
  
Bu sınıf uygulamasını sağlayan, WinRT ve COM sınıfların ortak uygulamasını sağlar `QueryInterface`, `AddRef`, `Release` vb., modülün başvuru sayısını yönetir ve sınıf üreteci için sağlama için destek sunmaktadır nesneleri etkinleştirilebilir.
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
template <typename ...TInterfaces> class RuntimeClass
template <unsigned int classFlags, typename ...TInterfaces> class RuntimeClass;
```
  
### <a name="parameters"></a>Parametreler  
 *classFlags*  
İsteğe bağlı parametre. Bir veya daha fazla birleşimi [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) sabit listesi değerleri. `__WRL_CONFIGURATION_LEGACY__` ClassFlags projedeki tüm çalışma zamanı sınıflar için varsayılan değeri değiştirmek için makro tanımlanabilir. Tanımlı değilse RuntimeClass varsayılan olmayan Çevik örnekleridir. RuntimeClass örnekleri, tanımlı değil, varsayılan olarak Çevik. Her zaman belirsizlik belirtmeniz önlemek `Microsoft::WRL::FtmBase` içinde `TInterfaces` veya `RuntimeClassType::InhibitFtmBase`. Hem de nesne kullanılan InhibitFtmBase ve FtmBase olup olmadığını Not, Çevik olacaktır.
 
 *TInterfaces*  
Arabirimlerin listesini ötesinde nesne uygulayan `IUnknown`, `IInspectable` veya diğer arabirimleri tarafından denetlenen [RuntimeClassType](../windows/runtimeclasstype-enumeration.md). Diğer sınıflar, özellikle türetilmesi listeleyebilir `Microsoft::WRL::FtmBase` nesne Çevik olun ve uygulamak neden `IMarshal`.
  
## <a name="members"></a>Üyeler  
`RuntimeClassInitialize` Bir işlev, nesne başlatır `MakeAndInitialize` şablon işlevi, nesneyi oluşturmak için kullanılır. Başlatma başarısız olursa nesne başarıyla başlatıldı, S_OK veya bir COM hata kodu döndürür. COM hata kodu, dönüş değeri olarak yayılır `MakeAndInitialize`. Unutmayın `RuntimeClassInitialize` yönteminin çağrılmaması durumunda `Make` şablon işlevi, nesneyi oluşturmak için kullanılır.

### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[RuntimeClass::RuntimeClass Oluşturucusu](../windows/runtimeclass-runtimeclass-constructor.md)|RuntimeClass sınıfının geçerli örneğinin başlatır.|  
|[RuntimeClass::~RuntimeClass Yıkıcısı](../windows/runtimeclass-tilde-runtimeclass-destructor.md)|RuntimeClass sınıfının geçerli örneğinin başlatmasını geri alır.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
Bir uygulama ayrıntısı budur.
  
## <a name="requirements"></a>Gereksinimler  
**Başlık:** implements.h  
  
**Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)