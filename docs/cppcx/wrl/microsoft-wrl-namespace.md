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
ms.openlocfilehash: c92251dacbfa17e8f1ac0cbdc41aa9b06118ac91
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213778"
---
# <a name="microsoftwrl-namespace"></a>Microsoft::WRL Ad Alanı

Windows Çalışma Zamanı C++ şablon kitaplığını oluşturan temel türleri tanımlar.

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
|[ActivationFactory Sınıfı](activationfactory-class.md)|Windows Çalışma Zamanı tarafından bir veya daha fazla sınıfın etkinleştirilmesini sağlar.|
|[AsyncBase Sınıfı](asyncbase-class.md)|Windows Çalışma Zamanı zaman uyumsuz durum makinesini uygular.|
|[ClassFactory Sınıfı](classfactory-class.md)|`IClassFactory` arabiriminin temel işlevlerini uygular.|
|[ComPtr Sınıfı](comptr-class.md)|Şablon parametresi tarafından belirtilen arabirimi temsil eden *akıllı bir işaretçi* türü oluşturur. ComPtr, temel alınan arabirim işaretçisi için bir başvuru sayısı otomatik olarak tutar ve başvuru sayısı sıfır olduğunda arabirimi yayınlar.|
|[DeferrableEventArgs Sınıfı](deferrableeventargs-class.md)|Erteleme için olay bağımsız değişken türleri için kullanılan bir şablon sınıfı.|
|[EventSource Sınıfı](eventsource-class.md)|Bir olayı temsil eder. `EventSource` üye işlevleri olay işleyicilerini ekler, kaldırır ve çağırır.|
|[FtmBase Sınıfı](ftmbase-class.md)|Serbest iş parçacıklı Sıralayıcı nesnesini temsil eder.|
|[Modül Sınıfı](module-class.md)|İlgili nesneler koleksiyonunu temsil eder.|
|[RuntimeClass Sınıfı](runtimeclass-class.md)|Belirtilen sayıda arabirimi devralan örneklenmiş bir sınıfı temsil eder ve belirtilen Windows Çalışma Zamanı, klasik COM ve zayıf başvuru desteğini sağlar.|
|[SimpleActivationFactory Sınıfı](simpleactivationfactory-class.md)|Windows Çalışma Zamanı veya klasik COM temel sınıfı oluşturmak için temel bir mekanizma sağlar.|
|[SimpleClassFactory Sınıfı](simpleclassfactory-class.md)|Temel sınıf oluşturmak için temel bir mekanizma sağlar.|
|[WeakRef Sınıfı](weakref-class.md)|Klasik COM değil yalnızca Windows Çalışma Zamanı tarafından kullanılabilen *zayıf bir başvuruyu* temsil eder. Zayıf başvuru, erişilebilir olabilecek veya erişilemeyen bir nesneyi temsil eder.|

### <a name="structures"></a>Yapılar

|Ad|Açıklama|
|----------|-----------------|
|[ChainInterfaces Yapısı](chaininterfaces-structure.md)|Bir arabirim kimliği kümesine uygulanabilen doğrulama ve başlatma işlevlerini belirtir.|
|[CloakedIid Yapısı](cloakediid-structure.md)|`RuntimeClass`, `Implements` ve `ChainInterfaces` şablonlarına, belirtilen arabirimin IID listesinde erişilebilir olmadığını gösterir.|
|[Implements Yapısı](implements-structure.md)|Belirtilen arabirimler için `QueryInterface` ve `GetIid` uygular.|
|[MixIn Yapısı](mixin-structure.md)|Çalışma zamanı sınıfının, varsa ve klasik COM arabirimlerinden Windows Çalışma Zamanı arabirimlerinden türemesini sağlar.|
|[RuntimeClassFlags Yapısı](runtimeclassflags-structure.md)|Bir [RuntimeClass](runtimeclass-class.md)örneği için türü içerir.|

### <a name="enumerations"></a>Numaralandırmalar

|Ad|Açıklama|
|----------|-----------------|
|[AsyncResultType Sabit Listesi](asyncresulttype-enumeration.md)|`GetResults()` yöntemi tarafından döndürülen sonuç türünü belirtir.|
|[ModuleType Sabit Listesi](moduletype-enumeration.md)|Modülün işlem içi bir sunucuyu mı yoksa işlem dışı bir sunucuyu mı desteklemesi gerektiğini belirtir.|
|[RuntimeClassType Sabit Listesi](runtimeclasstype-enumeration.md)|Desteklenen [RuntimeClass](runtimeclass-class.md) örneğinin türünü belirtir.|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|----------|-----------------|
|[AsWeak İşlevi](asweak-function.md)|Belirtilen örneğe zayıf bir başvuru alır.|
|[Callback İşlevi (WRL)](callback-function-wrl.md)|Üye işlevi bir geri çağırma yöntemi olan bir nesne oluşturur.|
|[CreateActivationFactory İşlevi](createactivationfactory-function.md)|Windows Çalışma Zamanı tarafından etkinleştirilenebilir belirtilen sınıfın örneklerini üreten bir fabrika oluşturur.|
|[CreateClassFactory İşlevi](createclassfactory-function.md)|Belirtilen sınıfın örneklerini üreten bir fabrika oluşturur.|
|[Make İşlevi](make-function.md)|Belirtilen Windows Çalışma Zamanı sınıfını başlatır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** Async. h, Client. h, corewrapper. h, Event. h, FTM. h, Implements. h, iç. h, modül. h

**Ad alanı:** Microsoft:: WRL

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL::Wrappers Ad Alanı](microsoft-wrl-wrappers-namespace.md)
