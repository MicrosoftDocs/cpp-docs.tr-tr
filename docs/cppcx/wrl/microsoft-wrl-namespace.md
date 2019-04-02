---
title: Microsoft::WRL Ad Alanı
ms.date: 11/04/2016
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
helpviewer_keywords:
- WRL namespace
ms.assetid: 01118a8f-f564-4859-b87e-9444848585a1
ms.openlocfilehash: d402f2a1292088b52ce921bbc0007ab96554189e
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58787065"
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
|`InhibitWeakReferencePolicy`|`RuntimeClassFlags<WinRt | InhibitWeakReference>`|

### <a name="classes"></a>Sınıflar

|Ad|Açıklama|
|----------|-----------------|
|[ActivationFactory Sınıfı](activationfactory-class.md)|Windows çalışma zamanı tarafından etkinleştirilmesi bir veya daha fazla sınıflar sağlar.|
|[AsyncBase Sınıfı](asyncbase-class.md)|Windows çalışma zamanı zaman uyumsuz Durum makinesi uygular.|
|[ClassFactory Sınıfı](classfactory-class.md)|Temel işlevselliğini uygular `IClassFactory` arabirimi.|
|[ComPtr Sınıfı](comptr-class.md)|Oluşturur bir *akıllı işaretçi* şablon parametresi tarafından belirlenen arabirimi temsil eden tür. ComPtr otomatik olarak, temel arabirim işaretçisi için bir başvuru sayısını tutar ve başvuru sayısı sıfıra gittiğinde arabirimi serbest bırakır.|
|[DeferrableEventArgs Sınıfı](deferrableeventargs-class.md)|Gönderilemeyenler için olay bağımsız değişken türleri için kullanılan bir şablon sınıfı.|
|[EventSource Sınıfı](eventsource-class.md)|Bir olayı temsil eder. `EventSource` üye işlevleri ekleme, kaldırma ve olay işleyicilerini çağırır.|
|[FtmBase Sınıfı](ftmbase-class.md)|Ücretsiz iş parçacıklı bir Sıralayıcı nesnesini temsil eder.|
|[Modül Sınıfı](module-class.md)|İlgili nesneler koleksiyonunu temsil eder.|
|[RuntimeClass Sınıfı](runtimeclass-class.md)|Belirtilen sayıda arabirimleri devralan ve belirtilen Windows çalışma zamanı klasik COM ve zayıf başvuru desteği sağlayan örneklenmiş bir sınıfı temsil eder.|
|[SimpleActivationFactory Sınıfı](simpleactivationfactory-class.md)|Bir Windows çalışma zamanı veya klasik COM temel sınıfı oluşturmak için temel bir mekanizma sağlar.|
|[SimpleClassFactory Sınıfı](simpleclassfactory-class.md)|Bir temel sınıf oluşturmak için temel bir mekanizma sağlar.|
|[WeakRef Sınıfı](weakref-class.md)|Temsil eden bir *zayıf başvuru* yalnızca Windows çalışma zamanı tarafından değil klasik COM kullanılabilir Zayıf bir başvuru erişilebilir olmayabilir veya bir nesneyi temsil eder.|

### <a name="structures"></a>Yapılar

|Ad|Açıklama|
|----------|-----------------|
|[ChainInterfaces Yapısı](chaininterfaces-structure.md)|Arabirim kimlikleri kümesine uygulanabilir doğrulama ve başlatma işlevleri belirtir.|
|[CloakedIid Yapısı](cloakediid-structure.md)|Gösterir `RuntimeClass`, `Implements` ve `ChainInterfaces` şablonları belirtilen arabirim IID'si listesinde erişilebilir değil.|
|[Implements Yapısı](implements-structure.md)|Implements `QueryInterface` ve `GetIid` belirtilen arabirimleri için.|
|[MixIn Yapısı](mixin-structure.md)|Bir çalışma zamanı sınıf varsa Windows çalışma zamanı arabirimleri ve ardından klasik COM arabirimleri türetilen sağlar.|
|[RuntimeClassFlags Yapısı](runtimeclassflags-structure.md)|Örneğinin türünü içeren bir [RuntimeClass](runtimeclass-class.md).|

### <a name="enumerations"></a>Numaralandırmalar

|Ad|Açıklama|
|----------|-----------------|
|[AsyncResultType Sabit Listesi](asyncresulttype-enumeration.md)|Tarafından döndürülen sonuç türü belirtir `GetResults()` yöntemi.|
|[ModuleType Sabit Listesi](moduletype-enumeration.md)|Bir modülü bir işlem sunucusu veya bir işlem dışı sunucu desteklemesi gerekip gerekmediğini belirtir.|
|[RuntimeClassType Sabit Listesi](runtimeclasstype-enumeration.md)|Türünü belirten [RuntimeClass](runtimeclass-class.md) desteklenen örneği.|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|----------|-----------------|
|[AsWeak İşlevi](asweak-function.md)|Belirtilen bir örneğe zayıf bir başvuru alır.|
|[Callback İşlevi (WRL)](callback-function-wrl.md)|Üye işlevi bir geri çağırma yöntemi olan nesne oluşturur.|
|[CreateActivationFactory İşlevi](createactivationfactory-function.md)|Windows çalışma zamanı tarafından etkinleştirilebilen belirtilen sınıf örneklerini oluşturan bir Üreteç oluşturur.|
|[CreateClassFactory İşlevi](createclassfactory-function.md)|Belirtilen sınıfın örneklerini oluşturan bir Üreteç oluşturur.|
|[Make İşlevi](make-function.md)|Belirtilen Windows çalışma zamanı sınıf başlatır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** async.h, client.h, corewrappers.h, event.h, ftm.h, implements.h, internal.h, module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL::Wrappers Ad Alanı](microsoft-wrl-wrappers-namespace.md)