---
title: Kategoriye Göre Başlıca WRL API'leri
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 7367bacf-6b7c-4ecd-a0ce-a662db46fc66
ms.openlocfilehash: 8ac89f3286866ac61bac5ae256bdb448fe88f07d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213830"
---
# <a name="key-wrl-apis-by-category"></a>Kategoriye Göre Başlıca WRL API'leri

Aşağıdaki tablolarda birincil Windows Çalışma Zamanı C++ şablon kitaplığı sınıfları, yapıları, işlevleri ve makroları listelenmektedir. Yardımcı ad alanlarında ve sınıflarda yapılar atlanır. Bu listeler, ad alanı tarafından düzenlenen API belgelerini artırabilir.

## <a name="classes"></a>Sınıflar

|Başlık|Açıklama|
|-----------|-----------------|
|[ActivationFactory Sınıfı](activationfactory-class.md)|Windows Çalışma Zamanı tarafından bir veya daha fazla sınıfın etkinleştirilmesini sağlar.|
|[AsyncBase Sınıfı](asyncbase-class.md)|Windows Çalışma Zamanı zaman uyumsuz durum makinesini uygular.|
|[ClassFactory Sınıfı](classfactory-class.md)|`IClassFactory` arabiriminin temel işlevlerini uygular.|
|[ComPtr Sınıfı](comptr-class.md)|Şablon parametresi tarafından belirtilen arabirimi temsil eden *akıllı bir işaretçi* türü oluşturur. ComPtr, temel alınan arabirim işaretçisi için bir başvuru sayısı otomatik olarak tutar ve başvuru sayısı sıfır olduğunda arabirimi yayınlar.|
|[Olay Sınıfı (Windows Çalışma Zamanı C++ Şablon Kitaplığı)](event-class-wrl.md)|Bir olayı temsil eder.|
|[EventSource Sınıfı](eventsource-class.md)|Bir olayı temsil eder. `EventSource` üye işlevleri olay işleyicilerini ekler, kaldırır ve çağırır.|
|[FtmBase Sınıfı](ftmbase-class.md)|Serbest iş parçacıklı Sıralayıcı nesnesini temsil eder.|
|[HandleT Sınıfı](handlet-class.md)|Bir nesneye olan tanıtıcıyı temsil eder.|
|[HString Sınıfı](hstring-class.md)|HSTRıNG tutamaçlarını işlemek için destek sağlar.|
|[HStringReference Sınıfı](hstringreference-class.md)|Varolan bir dizeden oluşturulan bir HSTRıNG temsil eder.|
|[Modül Sınıfı](module-class.md)|İlgili nesneler koleksiyonunu temsil eder.|
|[Module::GenericReleaseNotifier Sınıfı](module-genericreleasenotifier-class.md)|Geçerli modüldeki son nesne serbest bırakıldığında bir olay işleyicisini çağırır. Olay işleyicisi, bir lambda, functor veya işlev işaretçisi üzerinde tarafından belirtilir.|
|[Module::MethodReleaseNotifier Sınıfı](module-methodreleasenotifier-class.md)|Geçerli modüldeki son nesne serbest bırakıldığında bir olay işleyicisini çağırır. Olay işleyicisi bir nesne ve onun işaretçiden yönteme üyesi tarafından belirtilir.|
|[Module::ReleaseNotifier Sınıfı](module-releasenotifier-class.md)|Bir modüldeki son nesne bırakıldığında bir olay işleyicisini çağırır.|
|[RoInitializeWrapper Sınıfı](roinitializewrapper-class.md)|Windows Çalışma Zamanı başlatır.|
|[RuntimeClass Sınıfı](runtimeclass-class.md)|Belirtilen sayıda arabirimi devralan örneklenmiş bir sınıfı temsil eder ve belirtilen Windows Çalışma Zamanı, klasik COM ve zayıf başvuru desteğini sağlar.|
|[SimpleActivationFactory Sınıfı](simpleactivationfactory-class.md)|Windows Çalışma Zamanı veya klasik COM temel sınıfı oluşturmak için temel bir mekanizma sağlar.|
|[SimpleClassFactory Sınıfı](simpleclassfactory-class.md)|Temel sınıf oluşturmak için temel bir mekanizma sağlar.|
|[WeakRef Sınıfı](weakref-class.md)|Klasik COM değil yalnızca Windows Çalışma Zamanı tarafından kullanılabilen *zayıf bir başvuruyu* temsil eder. Zayıf başvuru, erişilebilir olabilecek veya erişilemeyen bir nesneyi temsil eder.|

## <a name="structures"></a>Yapılar

|Başlık|Açıklama|
|-----------|-----------------|
|[ChainInterfaces Yapısı](chaininterfaces-structure.md)|Bir arabirim kimliği kümesine uygulanabilen doğrulama ve başlatma işlevlerini belirtir.|
|[CloakedIid Yapısı](cloakediid-structure.md)|`RuntimeClass`, `Implements` ve `ChainInterfaces` şablonlarına, belirtilen arabirimin IID listesinde erişilebilir olmadığını gösterir.|
|[Implements Yapısı](implements-structure.md)|Belirtilen arabirimler için `QueryInterface` ve `GetIid` uygular.|
|[MixIn Yapısı](mixin-structure.md)|Çalışma zamanı sınıfının, varsa ve klasik COM arabirimlerinden Windows Çalışma Zamanı arabirimlerinden türemesini sağlar.|

## <a name="functions"></a>İşlevler

|Başlık|Açıklama|
|-----------|-----------------|
|[ActivateInstance İşlevi](activateinstance-function.md)|Belirtilen bir sınıf KIMLIĞINDE tanımlanan belirli bir türün bir örneğini kaydeder ve alır.|
|[AsWeak İşlevi](asweak-function.md)|Belirtilen örneğe zayıf bir başvuru alır.|
|[Callback Işlevi](callback-function-wrl.md)|Üye işlevi bir geri çağırma yöntemi olan bir nesne oluşturur.|
|[CreateActivationFactory İşlevi](createactivationfactory-function.md)|Windows Çalışma Zamanı tarafından etkinleştirilenebilir belirtilen sınıfın örneklerini üreten bir fabrika oluşturur.|
|[CreateClassFactory İşlevi](createclassfactory-function.md)|Belirtilen sınıfın örneklerini üreten bir fabrika oluşturur.|
|[GetActivationFactory İşlevi](getactivationfactory-function.md)|Şablon parametresi tarafından belirtilen tür için bir etkinleştirme fabrikası alır.|
|[Make İşlevi](make-function.md)|Belirtilen Windows Çalışma Zamanı sınıfını başlatır.|

## <a name="macros"></a>Makrolar

|Başlık|Açıklama|
|-----------|-----------------|
|[ActivatableClass Makroları](activatableclass-macros.md)|Belirtilen sınıfın bir örneğini oluşturabileceğiniz bir fabrika içeren bir iç önbelleği doldurur.|
|[InspectableClass Makrosu](inspectableclass-macro.md)|Çalışma zamanı sınıf adı ve güven düzeyini ayarlar.|

## <a name="see-also"></a>Ayrıca bkz.

[Windows Çalışma Zamanı C++ Şablon Kitaplığı (WRL)](windows-runtime-cpp-template-library-wrl.md)
