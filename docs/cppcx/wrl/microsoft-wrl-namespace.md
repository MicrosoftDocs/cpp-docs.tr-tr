---
description: 'Şu konuda daha fazla bilgi edinin: Microsoft:: WRL ad alanı'
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
ms.openlocfilehash: fdf7f0fbdca5cd5d95772052dd5dfb5018cabb18
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335532"
---
# <a name="microsoftwrl-namespace"></a>Microsoft::WRL Ad Alanı

Windows Çalışma Zamanı C++ şablon kitaplığını oluşturan temel türleri tanımlar.

## <a name="syntax"></a>Syntax

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
|[ActivationFactory sınıfı](activationfactory-class.md)|Windows Çalışma Zamanı tarafından bir veya daha fazla sınıfın etkinleştirilmesini sağlar.|
|[AsyncBase sınıfı](asyncbase-class.md)|Windows Çalışma Zamanı zaman uyumsuz durum makinesini uygular.|
|[ClassFactory sınıfı](classfactory-class.md)|, Arabiriminin temel işlevlerini uygular `IClassFactory` .|
|[ComPtr sınıfı](comptr-class.md)|Şablon parametresi tarafından belirtilen arabirimi temsil eden *akıllı bir işaretçi* türü oluşturur. ComPtr, temel alınan arabirim işaretçisi için bir başvuru sayısı otomatik olarak tutar ve başvuru sayısı sıfır olduğunda arabirimi yayınlar.|
|[Deferraybleeventargs sınıfı](deferrableeventargs-class.md)|Erteleme için olay bağımsız değişken türleri için kullanılan bir şablon sınıfı.|
|[EventSource sınıfı](eventsource-class.md)|Bir olayı temsil eder. `EventSource` üye işlevleri olay işleyicilerini ekler, kaldırır ve çağırır.|
|[FtmBase Sınıfı](ftmbase-class.md)|Serbest iş parçacıklı Sıralayıcı nesnesini temsil eder.|
|[Module sınıfı](module-class.md)|İlgili nesneler koleksiyonunu temsil eder.|
|[RuntimeClass Sınıfı](runtimeclass-class.md)|Belirtilen sayıda arabirimi devralan örneklenmiş bir sınıfı temsil eder ve belirtilen Windows Çalışma Zamanı, klasik COM ve zayıf başvuru desteğini sağlar.|
|[SimpleActivationFactory sınıfı](simpleactivationfactory-class.md)|Windows Çalışma Zamanı veya klasik COM temel sınıfı oluşturmak için temel bir mekanizma sağlar.|
|[SimpleClassFactory sınıfı](simpleclassfactory-class.md)|Temel sınıf oluşturmak için temel bir mekanizma sağlar.|
|[WeakRef Sınıfı](weakref-class.md)|Klasik COM değil yalnızca Windows Çalışma Zamanı tarafından kullanılabilen *zayıf bir başvuruyu* temsil eder. Zayıf başvuru, erişilebilir olabilecek veya erişilemeyen bir nesneyi temsil eder.|

### <a name="structures"></a>Yapılar

|Ad|Açıklama|
|----------|-----------------|
|[ChainInterfaces Yapısı](chaininterfaces-structure.md)|Bir arabirim kimliği kümesine uygulanabilen doğrulama ve başlatma işlevlerini belirtir.|
|[CloakedIid Yapısı](cloakediid-structure.md)|`RuntimeClass`, `Implements` Ve ' nin, `ChainInterfaces` belirtilen arabirime IID listesinde erişilebilir olmadığını gösterir.|
|[Implements Yapısı](implements-structure.md)|`QueryInterface` `GetIid` Belirtilen arabirimler için ve uygular.|
|[MixIn Yapısı](mixin-structure.md)|Çalışma zamanı sınıfının, varsa ve klasik COM arabirimlerinden Windows Çalışma Zamanı arabirimlerinden türemesini sağlar.|
|[RuntimeClassFlags Yapısı](runtimeclassflags-structure.md)|Bir [RuntimeClass](runtimeclass-class.md)örneği için türü içerir.|

### <a name="enumerations"></a>Listelemeler

|Ad|Açıklama|
|----------|-----------------|
|[AsyncResultType Numaralandırması](asyncresulttype-enumeration.md)|Yöntem tarafından döndürülen sonuç türünü belirtir `GetResults()` .|
|[ModuleType Numaralandırması](moduletype-enumeration.md)|Modülün işlem içi bir sunucuyu mı yoksa işlem dışı bir sunucuyu mı desteklemesi gerektiğini belirtir.|
|[RuntimeClassType Sabit Listesi](runtimeclasstype-enumeration.md)|Desteklenen [RuntimeClass](runtimeclass-class.md) örneğinin türünü belirtir.|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|----------|-----------------|
|[Aszayıf Işlev](asweak-function.md)|Belirtilen örneğe zayıf bir başvuru alır.|
|[Callback Işlevi (WRL)](callback-function-wrl.md)|Üye işlevi bir geri çağırma yöntemi olan bir nesne oluşturur.|
|[CreateActivationFactory Işlevi](createactivationfactory-function.md)|Windows Çalışma Zamanı tarafından etkinleştirilenebilir belirtilen sınıfın örneklerini üreten bir fabrika oluşturur.|
|[CreateClassFactory Işlevi](createclassfactory-function.md)|Belirtilen sınıfın örneklerini üreten bir fabrika oluşturur.|
|[Make Işlevi](make-function.md)|Belirtilen Windows Çalışma Zamanı sınıfını başlatır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** Async. h, Client. h, corewrapper. h, Event. h, FTM. h, Implements. h, iç. h, modül. h

**Ad alanı:** Microsoft:: WRL

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft:: WRL:: sarmalayıcılar ad alanı](microsoft-wrl-wrappers-namespace.md)
