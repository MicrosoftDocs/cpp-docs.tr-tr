---
description: "Daha fazla bilgi edinin: kategoriye göre anahtar WRL API 'Leri"
title: Kategoriye Göre Başlıca WRL API'leri
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 7367bacf-6b7c-4ecd-a0ce-a662db46fc66
ms.openlocfilehash: 14b5e113cb5553227f452d217a1745cbf20a5757
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298922"
---
# <a name="key-wrl-apis-by-category"></a>Kategoriye Göre Başlıca WRL API'leri

Aşağıdaki tablolarda, birincil Windows Çalışma Zamanı C++ Şablon kitaplığı sınıfları, yapıları, işlevleri ve makroları listelenmektedir. Yardımcı ad alanlarında ve sınıflarda yapılar atlanır. Bu listeler, ad alanı tarafından düzenlenen API belgelerini artırabilir.

## <a name="classes"></a>Sınıflar

|Başlık|Açıklama|
|-----------|-----------------|
|[ActivationFactory sınıfı](activationfactory-class.md)|Windows Çalışma Zamanı tarafından bir veya daha fazla sınıfın etkinleştirilmesini sağlar.|
|[AsyncBase sınıfı](asyncbase-class.md)|Windows Çalışma Zamanı zaman uyumsuz durum makinesini uygular.|
|[ClassFactory sınıfı](classfactory-class.md)|, Arabiriminin temel işlevlerini uygular `IClassFactory` .|
|[ComPtr sınıfı](comptr-class.md)|Şablon parametresi tarafından belirtilen arabirimi temsil eden *akıllı bir işaretçi* türü oluşturur. ComPtr, temel alınan arabirim işaretçisi için bir başvuru sayısı otomatik olarak tutar ve başvuru sayısı sıfır olduğunda arabirimi yayınlar.|
|[Olay Sınıfı (Windows Çalışma Zamanı C++ Şablon Kitaplığı)](event-class-wrl.md)|Bir olayı temsil eder.|
|[EventSource sınıfı](eventsource-class.md)|Bir olayı temsil eder. `EventSource` üye işlevleri olay işleyicilerini ekler, kaldırır ve çağırır.|
|[FtmBase Sınıfı](ftmbase-class.md)|Serbest iş parçacıklı Sıralayıcı nesnesini temsil eder.|
|[HandleT Sınıfı](handlet-class.md)|Bir nesneye olan tanıtıcıyı temsil eder.|
|[HString sınıfı](hstring-class.md)|HSTRıNG tutamaçlarını işlemek için destek sağlar.|
|[HStringReference sınıfı](hstringreference-class.md)|Varolan bir dizeden oluşturulan bir HSTRıNG temsil eder.|
|[Module sınıfı](module-class.md)|İlgili nesneler koleksiyonunu temsil eder.|
|[Module:: GenericReleaseNotifier sınıfı](module-genericreleasenotifier-class.md)|Geçerli modüldeki son nesne serbest bırakıldığında bir olay işleyicisini çağırır. Olay işleyicisi, bir lambda, functor veya işlev işaretçisi üzerinde tarafından belirtilir.|
|[Module:: MethodReleaseNotifier sınıfı](module-methodreleasenotifier-class.md)|Geçerli modüldeki son nesne serbest bırakıldığında bir olay işleyicisini çağırır. Olay işleyicisi bir nesne ve onun işaretçiden yönteme üyesi tarafından belirtilir.|
|[Module:: ReleaseNotifier sınıfı](module-releasenotifier-class.md)|Bir modüldeki son nesne bırakıldığında bir olay işleyicisini çağırır.|
|[RoInitializeWrapper sınıfı](roinitializewrapper-class.md)|Windows Çalışma Zamanı başlatır.|
|[RuntimeClass Sınıfı](runtimeclass-class.md)|Belirtilen sayıda arabirimi devralan örneklenmiş bir sınıfı temsil eder ve belirtilen Windows Çalışma Zamanı, klasik COM ve zayıf başvuru desteğini sağlar.|
|[SimpleActivationFactory sınıfı](simpleactivationfactory-class.md)|Windows Çalışma Zamanı veya klasik COM temel sınıfı oluşturmak için temel bir mekanizma sağlar.|
|[SimpleClassFactory sınıfı](simpleclassfactory-class.md)|Temel sınıf oluşturmak için temel bir mekanizma sağlar.|
|[WeakRef Sınıfı](weakref-class.md)|Klasik COM değil yalnızca Windows Çalışma Zamanı tarafından kullanılabilen *zayıf bir başvuruyu* temsil eder. Zayıf başvuru, erişilebilir olabilecek veya erişilemeyen bir nesneyi temsil eder.|

## <a name="structures"></a>Yapılar

|Başlık|Açıklama|
|-----------|-----------------|
|[ChainInterfaces Yapısı](chaininterfaces-structure.md)|Bir arabirim kimliği kümesine uygulanabilen doğrulama ve başlatma işlevlerini belirtir.|
|[CloakedIid Yapısı](cloakediid-structure.md)|`RuntimeClass`, `Implements` Ve ' nin, `ChainInterfaces` belirtilen arabirime IID listesinde erişilebilir olmadığını gösterir.|
|[Implements Yapısı](implements-structure.md)|`QueryInterface` `GetIid` Belirtilen arabirimler için ve uygular.|
|[MixIn Yapısı](mixin-structure.md)|Çalışma zamanı sınıfının, varsa ve klasik COM arabirimlerinden Windows Çalışma Zamanı arabirimlerinden türemesini sağlar.|

## <a name="functions"></a>İşlevler

|Başlık|Açıklama|
|-----------|-----------------|
|[ActivateInstance Işlevi](activateinstance-function.md)|Belirtilen bir sınıf KIMLIĞINDE tanımlanan belirli bir türün bir örneğini kaydeder ve alır.|
|[Aszayıf Işlev](asweak-function.md)|Belirtilen örneğe zayıf bir başvuru alır.|
|[Callback Işlevi](callback-function-wrl.md)|Üye işlevi bir geri çağırma yöntemi olan bir nesne oluşturur.|
|[CreateActivationFactory Işlevi](createactivationfactory-function.md)|Windows Çalışma Zamanı tarafından etkinleştirilenebilir belirtilen sınıfın örneklerini üreten bir fabrika oluşturur.|
|[CreateClassFactory Işlevi](createclassfactory-function.md)|Belirtilen sınıfın örneklerini üreten bir fabrika oluşturur.|
|[GetActivationFactory Işlevi](getactivationfactory-function.md)|Şablon parametresi tarafından belirtilen tür için bir etkinleştirme fabrikası alır.|
|[Make Işlevi](make-function.md)|Belirtilen Windows Çalışma Zamanı sınıfını başlatır.|

## <a name="macros"></a>Makrolar

|Başlık|Açıklama|
|-----------|-----------------|
|[ActivatableClass makroları](activatableclass-macros.md)|Belirtilen sınıfın bir örneğini oluşturabileceğiniz bir fabrika içeren bir iç önbelleği doldurur.|
|[InspectableClass makrosu](inspectableclass-macro.md)|Çalışma zamanı sınıf adı ve güven düzeyini ayarlar.|

## <a name="see-also"></a>Ayrıca bkz.

[Windows Çalışma Zamanı C++ Şablon Kitaplığı (WRL)](windows-runtime-cpp-template-library-wrl.md)
