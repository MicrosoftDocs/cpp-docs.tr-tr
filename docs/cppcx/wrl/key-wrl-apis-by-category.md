---
title: Kategoriye Göre Başlıca WRL API'leri
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 7367bacf-6b7c-4ecd-a0ce-a662db46fc66
ms.openlocfilehash: f3065323c567c944dab12fc1ebbcbd6bb57127e9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62223156"
---
# <a name="key-wrl-apis-by-category"></a>Kategoriye Göre Başlıca WRL API'leri

Aşağıdaki tablolar, birincil Windows çalışma zamanı C++ Şablon kitaplığı sınıflar, yapılar, işlevlerini ve makrolarını listeler. Yardımcısı ad alanları ve sınıflar, yapılar göz ardı edilir. Bu listeler, API belgeleri, ad alanı tarafından düzenlenmiş artırabilir.

## <a name="classes"></a>Sınıflar

|Başlık|Açıklama|
|-----------|-----------------|
|[ActivationFactory Sınıfı](activationfactory-class.md)|Windows çalışma zamanı tarafından etkinleştirilmesi bir veya daha fazla sınıflar sağlar.|
|[AsyncBase Sınıfı](asyncbase-class.md)|Windows çalışma zamanı zaman uyumsuz Durum makinesi uygular.|
|[ClassFactory Sınıfı](classfactory-class.md)|Temel işlevselliğini uygular `IClassFactory` arabirimi.|
|[ComPtr Sınıfı](comptr-class.md)|Oluşturur bir *akıllı işaretçi* şablon parametresi tarafından belirlenen arabirimi temsil eden tür. ComPtr otomatik olarak, temel arabirim işaretçisi için bir başvuru sayısını tutar ve başvuru sayısı sıfıra gittiğinde arabirimi serbest bırakır.|
|[Olay Sınıfı (Windows Çalışma Zamanı C++ Şablon Kitaplığı)](event-class-wrl.md)|Bir olayı temsil eder.|
|[EventSource Sınıfı](eventsource-class.md)|Bir olayı temsil eder. `EventSource` üye işlevleri ekleme, kaldırma ve olay işleyicilerini çağırır.|
|[FtmBase Sınıfı](ftmbase-class.md)|Ücretsiz iş parçacıklı bir Sıralayıcı nesnesini temsil eder.|
|[HandleT Sınıfı](handlet-class.md)|Bir tutamacı nesneyi temsil eder.|
|[HString Sınıfı](hstring-class.md)|HSTRING tutamaçları düzenlenmesi için destek sağlar.|
|[HStringReference Sınıfı](hstringreference-class.md)|Varolan bir dizeden oluşturulan bir HSTRING temsil eder.|
|[Modül Sınıfı](module-class.md)|İlgili nesneler koleksiyonunu temsil eder.|
|[Module::GenericReleaseNotifier Sınıfı](module-genericreleasenotifier-class.md)|Geçerli modül içinde son nesnenin yayımlandığında bir olay işleyici çağırır. Olay işleyici lambda, functor veya işaretçi işlevi tarafından belirtilir.|
|[Module::MethodReleaseNotifier Sınıfı](module-methodreleasenotifier-class.md)|Geçerli modül içinde son nesnenin yayımlandığında bir olay işleyici çağırır. Olay işleyicisi, bir nesne ve onun yöntemi için işaretçi üye tarafından belirtilir.|
|[Module::ReleaseNotifier Sınıfı](module-releasenotifier-class.md)|Modül içindeki son nesnenin yayımlandığında bir olay işleyici çağırır.|
|[RoInitializeWrapper Sınıfı](roinitializewrapper-class.md)|Windows çalışma zamanı'nı başlatır.|
|[RuntimeClass Sınıfı](runtimeclass-class.md)|Belirtilen sayıda arabirimleri devralan ve belirtilen Windows çalışma zamanı klasik COM ve zayıf başvuru desteği sağlayan örneklenmiş bir sınıfı temsil eder.|
|[SimpleActivationFactory Sınıfı](simpleactivationfactory-class.md)|Bir Windows çalışma zamanı veya klasik COM temel sınıfı oluşturmak için temel bir mekanizma sağlar.|
|[SimpleClassFactory Sınıfı](simpleclassfactory-class.md)|Bir temel sınıf oluşturmak için temel bir mekanizma sağlar.|
|[WeakRef Sınıfı](weakref-class.md)|Temsil eden bir *zayıf başvuru* yalnızca Windows çalışma zamanı tarafından değil klasik COM kullanılabilir Zayıf bir başvuru erişilebilir olmayabilir veya bir nesneyi temsil eder.|

## <a name="structures"></a>Yapılar

|Başlık|Açıklama|
|-----------|-----------------|
|[ChainInterfaces Yapısı](chaininterfaces-structure.md)|Arabirim kimlikleri kümesine uygulanabilir doğrulama ve başlatma işlevleri belirtir.|
|[CloakedIid Yapısı](cloakediid-structure.md)|Gösterir `RuntimeClass`, `Implements` ve `ChainInterfaces` şablonları belirtilen arabirim IID'si listesinde erişilebilir değil.|
|[Implements Yapısı](implements-structure.md)|Implements `QueryInterface` ve `GetIid` belirtilen arabirimleri için.|
|[MixIn Yapısı](mixin-structure.md)|Bir çalışma zamanı sınıf varsa Windows çalışma zamanı arabirimleri ve ardından klasik COM arabirimleri türetilen sağlar.|

## <a name="functions"></a>İşlevler

|Başlık|Açıklama|
|-----------|-----------------|
|[ActivateInstance İşlevi](activateinstance-function.md)|Kaydeder ve belirtilen sınıf kimliğinde tanımlanan belirli bir türün bir örneğini alır.|
|[AsWeak İşlevi](asweak-function.md)|Belirtilen bir örneğe zayıf bir başvuru alır.|
|[Geri çağırma işlevi](callback-function-wrl.md)|Üye işlevi bir geri çağırma yöntemi olan nesne oluşturur.|
|[CreateActivationFactory İşlevi](createactivationfactory-function.md)|Windows çalışma zamanı tarafından etkinleştirilebilen belirtilen sınıf örneklerini oluşturan bir Üreteç oluşturur.|
|[CreateClassFactory İşlevi](createclassfactory-function.md)|Belirtilen sınıfın örneklerini oluşturan bir Üreteç oluşturur.|
|[GetActivationFactory İşlevi](getactivationfactory-function.md)|Şablon parametresi tarafından belirtilen tür için bir etkinleştirme üretecini alır.|
|[Make İşlevi](make-function.md)|Belirtilen Windows çalışma zamanı sınıf başlatır.|

## <a name="macros"></a>Makrolar

|Başlık|Açıklama|
|-----------|-----------------|
|[ActivatableClass Makroları](activatableclass-macros.md)|Belirtilen sınıfın bir örneğini oluşturan bir üreteci içeren bir iç önbelleğe doldurur.|
|[InspectableClass Makrosu](inspectableclass-macro.md)|Çalışma zamanı sınıf adı ve güven düzeyini ayarlar.|

## <a name="see-also"></a>Ayrıca bkz.

[Windows Çalışma Zamanı C++ Şablon Kitaplığı (WRL)](windows-runtime-cpp-template-library-wrl.md)