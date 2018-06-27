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
ms.openlocfilehash: 26c3542f5bea21d1b705cd3253e6828ff73677df
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33889013"
---
# <a name="runtimeclass-class"></a>RuntimeClass Sınıfı
Belirtilen arabirimlerden devralır ve belirtilen Windows çalışma zamanı, klasik COM ve zayıf başvuru desteği sağlayan bir WinRT veya COM sınıfı temsil eder.  
  
Bu sınıf uygulaması sağlama WinRT ve COM sınıfları Demirbaş uygulamasını sağlar `QueryInterface`, `AddRef`, `Release` vb., modül başvurusu sayısı yönetir ve üreteci için sağlama desteğe sahiptir activatable nesneleri.
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <typename ...TInterfaces> class RuntimeClass
template <unsigned int classFlags, typename ...TInterfaces> class RuntimeClass;
```
  
#### <a name="parameters"></a>Parametreler  
 `classFlags`  
İsteğe bağlı parametresi. Bir veya daha fazla bileşimini [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) numaralandırma değerleri. `__WRL_CONFIGURATION_LEGACY__` Makrosu classFlags projedeki tüm çalışma zamanı sınıfları için varsayılan değeri değiştirmek için tanımlanabilir. Tanımlanmış ise, RuntimeClass varsayılan olmayan Çevik örnekleridir. Tanımlı değil, RuntimeClass varsayılan olarak Çevik örnekleridir. Önlemek için belirsizlik her zaman belirtmeniz Microsoft::WRL::FtmBase `TInterfaces` veya RuntimeClassType::InhibitFtmBase. InhibitFtmBase ve FtmBase hem de nesne kullanılan ise Not Çevik olacaktır.
 
 `TInterfaces`  
IUnknown, Iınspectable veya denetlediği diğer arabirimleri ötesinde nesne arabirimleri listesine uygulayan [RuntimeClassType](../windows/runtimeclasstype-enumeration.md). Ayrıca, özellikle Microsoft::WRL::FtmBase, nesne Çevik yapıp IMarshal uygulamak neden türetilmesi için diğer sınıflar de listeleyebilir.
  
## <a name="members"></a>Üyeler  
`RuntimeClassInitialize` Makeandınitialize şablon işlevi nesneyi oluşturmak için kullanılan nesneyi başlatır bir işlev. Başlatma başarısız olursa nesne başarıyla başlatılmış varsa S_OK veya bir COM hata kodunu döndürür. COM hata kodu Makeandınitialize dönüş değeri olarak yayılır. Yapma şablon işlevi nesnesi oluşturmak için kullanılıyorsa, RuntimeClassInitialize yöntemi çağrılmaz unutmayın.

### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[RuntimeClass::RuntimeClass Oluşturucusu](../windows/runtimeclass-runtimeclass-constructor.md)|RuntimeClass sınıfı geçerli bir örneğini başlatır.|  
|[RuntimeClass::~RuntimeClass Yıkıcısı](../windows/runtimeclass-tilde-runtimeclass-destructor.md)|RuntimeClass sınıfı, geçerli örneğini deinitializes.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
Bir uygulama ayrıntılarını budur.
  
## <a name="requirements"></a>Gereksinimler  
**Başlık:** implements.h  
  
**Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)
