---
title: Microsoft::WRL Namespace | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL
- module/Microsoft::WRL
- async/Microsoft::WRL
- internal/Microsoft::WRL
- event/Microsoft::WRL
- ftm/Microsoft::WRL
- client/Microsoft::WRL
- corewrappers/Microsoft::WRL
dev_langs:
- C++
helpviewer_keywords:
- WRL namespace
ms.assetid: 01118a8f-f564-4859-b87e-9444848585a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5ffea6dede3bc6bcc7c28b2326299362e78ed2b9
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42599307"
---
# <a name="microsoftwrl-namespace"></a>Microsoft::WRL Ad Alanı

Windows çalışma zamanı C++ Şablon Kitaplığı ' olun temel türleri tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
namespace Microsoft::WRL;
```

## <a name="members"></a>Üyeler

### <a name="typedefs"></a>Tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`InhibitWeakReferencePolicy`|`RuntimeClassFlags<WinRt &#124; InhibitWeakReference>`|

### <a name="classes"></a>Sınıflar

|Ad|Açıklama|
|----------|-----------------|
|[ActivationFactory Sınıfı](../windows/activationfactory-class.md)|Windows çalışma zamanı tarafından etkinleştirilmesi bir veya daha fazla sınıflar sağlar.|
|[AsyncBase Sınıfı](../windows/asyncbase-class.md)|Windows çalışma zamanı zaman uyumsuz Durum makinesi uygular.|
|[ClassFactory Sınıfı](../windows/classfactory-class.md)|Temel işlevselliğini uygular `IClassFactory` arabirimi.|
|[ComPtr Sınıfı](../windows/comptr-class.md)|Oluşturur bir *akıllı işaretçi* şablon parametresi tarafından belirlenen arabirimi temsil eden tür. ComPtr otomatik olarak, temel arabirim işaretçisi için bir başvuru sayısını tutar ve başvuru sayısı sıfıra gittiğinde arabirimi serbest bırakır.|
|[DeferrableEventArgs Sınıfı](../windows/deferrableeventargs-class.md)|Gönderilemeyenler için olay bağımsız değişken türleri için kullanılan bir şablon sınıfı.|
|[EventSource Sınıfı](../windows/eventsource-class.md)|Bir olayı temsil eder. `EventSource` üye işlevleri ekleme, kaldırma ve olay işleyicilerini çağırır.|
|[FtmBase Sınıfı](../windows/ftmbase-class.md)|Ücretsiz iş parçacıklı bir Sıralayıcı nesnesini temsil eder.|
|[Modül Sınıfı](../windows/module-class.md)|İlgili nesneler koleksiyonunu temsil eder.|
|[RuntimeClass Sınıfı](../windows/runtimeclass-class.md)|Belirtilen sayıda arabirimleri devralan ve belirtilen Windows çalışma zamanı klasik COM ve zayıf başvuru desteği sağlayan örneklenmiş bir sınıfı temsil eder.|
|[SimpleActivationFactory Sınıfı](../windows/simpleactivationfactory-class.md)|Bir Windows çalışma zamanı veya klasik COM temel sınıfı oluşturmak için temel bir mekanizma sağlar.|
|[SimpleClassFactory Sınıfı](../windows/simpleclassfactory-class.md)|Bir temel sınıf oluşturmak için temel bir mekanizma sağlar.|
|[WeakRef Sınıfı](../windows/weakref-class.md)|Temsil eden bir *zayıf başvuru* yalnızca Windows çalışma zamanı tarafından değil klasik COM kullanılabilir Zayıf bir başvuru erişilebilir olmayabilir veya bir nesneyi temsil eder.|

### <a name="structures"></a>Yapılar

|Ad|Açıklama|
|----------|-----------------|
|[ChainInterfaces Yapısı](../windows/chaininterfaces-structure.md)|Arabirim kimlikleri kümesine uygulanabilir doğrulama ve başlatma işlevleri belirtir.|
|[CloakedIid Yapısı](../windows/cloakediid-structure.md)|Gösterir `RuntimeClass`, `Implements` ve `ChainInterfaces` şablonları belirtilen arabirim IID'si listesinde erişilebilir değil.|
|[Implements Yapısı](../windows/implements-structure.md)|Implements `QueryInterface` ve `GetIid` belirtilen arabirimleri için.|
|[MixIn Yapısı](../windows/mixin-structure.md)|Bir çalışma zamanı sınıf varsa Windows çalışma zamanı arabirimleri ve ardından klasik COM arabirimleri türetilen sağlar.|
|[RuntimeClassFlags Yapısı](../windows/runtimeclassflags-structure.md)|Örneğinin türünü içeren bir [RuntimeClass](../windows/runtimeclass-class.md).|

### <a name="enumerations"></a>Numaralandırmalar

|Ad|Açıklama|
|----------|-----------------|
|[AsyncResultType Sabit Listesi](../windows/asyncresulttype-enumeration.md)|Tarafından döndürülen sonuç türü belirtir `GetResults()` yöntemi.|
|[ModuleType Sabit Listesi](../windows/moduletype-enumeration.md)|Bir modülü bir işlem sunucusu veya bir işlem dışı sunucu desteklemesi gerekip gerekmediğini belirtir.|
|[RuntimeClassType Sabit Listesi](../windows/runtimeclasstype-enumeration.md)|Türünü belirten [RuntimeClass](../windows/runtimeclass-class.md) desteklenen örneği.|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|----------|-----------------|
|[AsWeak İşlevi](../windows/asweak-function.md)|Belirtilen bir örneğe zayıf bir başvuru alır.|
|[Geri çağırma işlevi](../windows/callback-function-windows-runtime-cpp-template-library.md)|Üye işlevi bir geri çağırma yöntemi olan nesne oluşturur.|
|[CreateActivationFactory İşlevi](../windows/createactivationfactory-function.md)|Windows çalışma zamanı tarafından etkinleştirilebilen belirtilen sınıf örneklerini oluşturan bir Üreteç oluşturur.|
|[CreateClassFactory İşlevi](../windows/createclassfactory-function.md)|Belirtilen sınıfın örneklerini oluşturan bir Üreteç oluşturur.|
|[Make İşlevi](../windows/make-function.md)|Belirtilen Windows çalışma zamanı sınıf başlatır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** async.h, client.h, corewrappers.h, event.h, ftm.h, implements.h, internal.h, module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL::Wrappers Ad Alanı](../windows/microsoft-wrl-wrappers-namespace.md)