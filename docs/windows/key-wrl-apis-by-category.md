---
title: Kategoriye Göre Başlıca WRL API'leri
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 7367bacf-6b7c-4ecd-a0ce-a662db46fc66
ms.openlocfilehash: 529d561aa3ec486a7fa2b69e5ca8aa241b0879fe
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50638067"
---
# <a name="key-wrl-apis-by-category"></a>Kategoriye Göre Başlıca WRL API'leri

Aşağıdaki tablolar, birincil Windows çalışma zamanı C++ Şablon kitaplığı sınıflar, yapılar, işlevlerini ve makrolarını listeler. Yardımcısı ad alanları ve sınıflar, yapılar göz ardı edilir. Bu listeler, API belgeleri, ad alanı tarafından düzenlenmiş artırabilir.

## <a name="classes"></a>Sınıflar

|Başlık|Açıklama|
|-----------|-----------------|
|[ActivationFactory Sınıfı](../windows/activationfactory-class.md)|Windows çalışma zamanı tarafından etkinleştirilmesi bir veya daha fazla sınıflar sağlar.|
|[AsyncBase Sınıfı](../windows/asyncbase-class.md)|Windows çalışma zamanı zaman uyumsuz Durum makinesi uygular.|
|[ClassFactory Sınıfı](../windows/classfactory-class.md)|Temel işlevselliğini uygular `IClassFactory` arabirimi.|
|[ComPtr Sınıfı](../windows/comptr-class.md)|Oluşturur bir *akıllı işaretçi* şablon parametresi tarafından belirlenen arabirimi temsil eden tür. ComPtr otomatik olarak, temel arabirim işaretçisi için bir başvuru sayısını tutar ve başvuru sayısı sıfıra gittiğinde arabirimi serbest bırakır.|
|[Olay Sınıfı (Windows Çalışma Zamanı C++ Şablon Kitaplığı)](../windows/event-class-windows-runtime-cpp-template-library.md)|Bir olayı temsil eder.|
|[EventSource Sınıfı](../windows/eventsource-class.md)|Bir olayı temsil eder. `EventSource` üye işlevleri ekleme, kaldırma ve olay işleyicilerini çağırır.|
|[FtmBase Sınıfı](../windows/ftmbase-class.md)|Ücretsiz iş parçacıklı bir Sıralayıcı nesnesini temsil eder.|
|[HandleT Sınıfı](../windows/handlet-class.md)|Bir tutamacı nesneyi temsil eder.|
|[HString Sınıfı](../windows/hstring-class.md)|HSTRING tutamaçları düzenlenmesi için destek sağlar.|
|[HStringReference Sınıfı](../windows/hstringreference-class.md)|Varolan bir dizeden oluşturulan bir HSTRING temsil eder.|
|[Modül Sınıfı](../windows/module-class.md)|İlgili nesneler koleksiyonunu temsil eder.|
|[Module::GenericReleaseNotifier Sınıfı](../windows/module-genericreleasenotifier-class.md)|Geçerli modül içinde son nesnenin yayımlandığında bir olay işleyici çağırır. Olay işleyici lambda, functor veya işaretçi işlevi tarafından belirtilir.|
|[Module::MethodReleaseNotifier Sınıfı](../windows/module-methodreleasenotifier-class.md)|Geçerli modül içinde son nesnenin yayımlandığında bir olay işleyici çağırır. Olay işleyicisi, bir nesne ve onun yöntemi için işaretçi üye tarafından belirtilir.|
|[Module::ReleaseNotifier Sınıfı](../windows/module-releasenotifier-class.md)|Modül içindeki son nesnenin yayımlandığında bir olay işleyici çağırır.|
|[RoInitializeWrapper Sınıfı](../windows/roinitializewrapper-class.md)|Windows çalışma zamanı'nı başlatır.|
|[RuntimeClass Sınıfı](../windows/runtimeclass-class.md)|Belirtilen sayıda arabirimleri devralan ve belirtilen Windows çalışma zamanı klasik COM ve zayıf başvuru desteği sağlayan örneklenmiş bir sınıfı temsil eder.|
|[SimpleActivationFactory Sınıfı](../windows/simpleactivationfactory-class.md)|Bir Windows çalışma zamanı veya klasik COM temel sınıfı oluşturmak için temel bir mekanizma sağlar.|
|[SimpleClassFactory Sınıfı](../windows/simpleclassfactory-class.md)|Bir temel sınıf oluşturmak için temel bir mekanizma sağlar.|
|[WeakRef Sınıfı](../windows/weakref-class.md)|Temsil eden bir *zayıf başvuru* yalnızca Windows çalışma zamanı tarafından değil klasik COM kullanılabilir Zayıf bir başvuru erişilebilir olmayabilir veya bir nesneyi temsil eder.|

## <a name="structures"></a>Yapılar

|Başlık|Açıklama|
|-----------|-----------------|
|[ChainInterfaces Yapısı](../windows/chaininterfaces-structure.md)|Arabirim kimlikleri kümesine uygulanabilir doğrulama ve başlatma işlevleri belirtir.|
|[CloakedIid Yapısı](../windows/cloakediid-structure.md)|Gösterir `RuntimeClass`, `Implements` ve `ChainInterfaces` şablonları belirtilen arabirim IID'si listesinde erişilebilir değil.|
|[Implements Yapısı](../windows/implements-structure.md)|Implements `QueryInterface` ve `GetIid` belirtilen arabirimleri için.|
|[MixIn Yapısı](../windows/mixin-structure.md)|Bir çalışma zamanı sınıf varsa Windows çalışma zamanı arabirimleri ve ardından klasik COM arabirimleri türetilen sağlar.|

## <a name="functions"></a>İşlevler

|Başlık|Açıklama|
|-----------|-----------------|
|[ActivateInstance İşlevi](../windows/activateinstance-function.md)|Kaydeder ve belirtilen sınıf kimliğinde tanımlanan belirli bir türün bir örneğini alır.|
|[AsWeak İşlevi](../windows/asweak-function.md)|Belirtilen bir örneğe zayıf bir başvuru alır.|
|[Geri çağırma işlevi](../windows/callback-function-windows-runtime-cpp-template-library.md)|Üye işlevi bir geri çağırma yöntemi olan nesne oluşturur.|
|[CreateActivationFactory İşlevi](../windows/createactivationfactory-function.md)|Windows çalışma zamanı tarafından etkinleştirilebilen belirtilen sınıf örneklerini oluşturan bir Üreteç oluşturur.|
|[CreateClassFactory İşlevi](../windows/createclassfactory-function.md)|Belirtilen sınıfın örneklerini oluşturan bir Üreteç oluşturur.|
|[GetActivationFactory İşlevi](../windows/getactivationfactory-function.md)|Şablon parametresi tarafından belirtilen tür için bir etkinleştirme üretecini alır.|
|[Make İşlevi](../windows/make-function.md)|Belirtilen Windows çalışma zamanı sınıf başlatır.|

## <a name="macros"></a>Makrolar

|Başlık|Açıklama|
|-----------|-----------------|
|[ActivatableClass Makroları](../windows/activatableclass-macros.md)|Belirtilen sınıfın bir örneğini oluşturan bir üreteci içeren bir iç önbelleğe doldurur.|
|[InspectableClass Makrosu](../windows/inspectableclass-macro.md)|Çalışma zamanı sınıf adı ve güven düzeyini ayarlar.|

## <a name="see-also"></a>Ayrıca Bkz.

[Windows Çalışma Zamanı C++ Şablon Kitaplığı (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)