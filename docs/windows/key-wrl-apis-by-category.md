---
title: Anahtar WRL API'leri kategoriye göre | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: 7367bacf-6b7c-4ecd-a0ce-a662db46fc66
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9936c85443f893111b3c2b9de17ca80e6fb382b2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="key-wrl-apis-by-category"></a>Kategoriye Göre Başlıca WRL API'leri
Birincil Windows çalışma zamanı C++ Şablon kitaplığı sınıflar, yapılar, İşlevler ve makrolar aşağıdaki tablolarda listelenmektedir. Yardımcı ad alanları ve sınıfları yapılardan göz ardı edilir. Bu listeler ad alanlarına göre düzenlenen API belgelerine kullanmasıdır.  
  
### <a name="classes"></a>Sınıflar  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[ActivationFactory Sınıfı](../windows/activationfactory-class.md)|Windows çalışma zamanı tarafından etkinleştirilecek bir veya daha fazla sınıfları sağlar.|  
|[AsyncBase Sınıfı](../windows/asyncbase-class.md)|Windows çalışma zamanı zaman uyumsuz durum makinesinin uygular.|  
|[ClassFactory Sınıfı](../windows/classfactory-class.md)|Temel işlevselliğini uygulayan `IClassFactory` arabirimi.|  
|[ComPtr Sınıfı](../windows/comptr-class.md)|Oluşturur bir *akıllı işaretçi* şablon parametresi tarafından belirtilen arabirimi temsil eden tür. ComPtr otomatik olarak bir başvuru sayısı için temel arabirim işaretçisi tutar ve başvuru sayısı sıfır olarak gittiğinde arabirimi serbest bırakır.|  
|[Olay Sınıfı (Windows Çalışma Zamanı C++ Şablon Kitaplığı)](../windows/event-class-windows-runtime-cpp-template-library.md)|Bir olayı temsil eder.|  
|[EventSource Sınıfı](../windows/eventsource-class.md)|Bir olayı temsil eder. `EventSource` üye işlevleri eklemek, kaldırmak ve olay işleyicilerini çağırma.|  
|[FtmBase Sınıfı](../windows/ftmbase-class.md)|Ücretsiz iş parçacıklı Sıralayıcı nesneyi temsil eder.|  
|[HandleT Sınıfı](../windows/handlet-class.md)|Bir tanıtıcı nesneyi temsil eder.|  
|[HString Sınıfı](../windows/hstring-class.md)|HSTRING tanıtıcıları yönlendirmek için destek sağlar.|  
|[HStringReference Sınıfı](../windows/hstringreference-class.md)|Varolan bir dizeden oluşturulmuş bir HSTRING temsil eder.|  
|[Modül Sınıfı](../windows/module-class.md)|İlgili nesneler koleksiyonunu temsil eder.|  
|[Module::GenericReleaseNotifier Sınıfı](../windows/module-genericreleasenotifier-class.md)|Son nesne geçerli modülünde yayımlandığında, bir olay işleyiciyi çağırır. Olay işleyicisi lambda, functor veya işaretçi işlevi belirtilir.|  
|[Module::MethodReleaseNotifier Sınıfı](../windows/module-methodreleasenotifier-class.md)|Son nesne geçerli modülünde yayımlandığında, bir olay işleyiciyi çağırır. Olay işleyicisi bir nesne ve kendi yöntemi için işaretçi üyesi tarafından belirtilir.|  
|[Module::ReleaseNotifier Sınıfı](../windows/module-releasenotifier-class.md)|Bir modül son nesnesinde yayımlandığında, bir olay işleyiciyi çağırır.|  
|[RoInitializeWrapper Sınıfı](../windows/roinitializewrapper-class.md)|Windows çalışma zamanı başlatır.|  
|[RuntimeClass Sınıfı](../windows/runtimeclass-class.md)|Belirtilen sayıda arabirimleri devralır ve belirtilen Windows çalışma zamanı, klasik COM ve zayıf başvuru desteği sağlar başlatılan bir sınıfı temsil eder.|  
|[SimpleActivationFactory Sınıfı](../windows/simpleactivationfactory-class.md)|Windows çalışma zamanı veya klasik COM temel sınıf oluşturmak için temel bir mekanizma sağlar.|  
|[SimpleClassFactory Sınıfı](../windows/simpleclassfactory-class.md)|Bir taban sınıf oluşturmak için temel bir mekanizma sağlar.|  
|[WeakRef Sınıfı](../windows/weakref-class.md)|Temsil eden bir *zayıf başvuru* yalnızca Windows çalışma zamanı tarafından değil klasik COM kullanılabilir Zayıf başvuru olabilir ya da erişilebilir olmayabilir bir nesneyi temsil eder.|  
  
### <a name="structures"></a>Yapılar  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[ChainInterfaces Yapısı](../windows/chaininterfaces-structure.md)|Arabirim kimlikleri kümesine uygulanabilir doğrulama ve başlatma işlevleri belirtir.|  
|[CloakedIid Yapısı](../windows/cloakediid-structure.md)|Gösterir `RuntimeClass`, `Implements` ve `ChainInterfaces` şablonları belirtilen arabirim IID listesinde erişilebilir değil.|  
|[Implements Yapısı](../windows/implements-structure.md)|Implements `QueryInterface` ve `GetIid` belirtilen arabirimleri için.|  
|[MixIn Yapısı](../windows/mixin-structure.md)|Bir çalışma zamanı sınıf Windows Çalışma Zamanı Modülü arabirimler, varsa ve daha sonra klasik COM arabirimleri türetilen sağlar.|  
  
### <a name="functions"></a>İşlevler  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[ActivateInstance İşlevi](../windows/activateinstance-function.md)|Kaydeder ve bir belirtilen sınıf kimliği tanımlanan belirtilen bir türün bir örneğini alır.|  
|[AsWeak İşlevi](../windows/asweak-function.md)|Belirtilen bir örneğine zayıf başvuru alır.|  
|[Geri çağırma işlevi](../windows/callback-function-windows-runtime-cpp-template-library.md)|Bir geri çağırma yöntemi, üye işlevi olan bir nesne oluşturur.|  
|[CreateActivationFactory İşlevi](../windows/createactivationfactory-function.md)|Windows çalışma zamanı tarafından etkinleştirilebilir belirtilen sınıfının örnekleri oluşturan bir Üreteç oluşturur.|  
|[CreateClassFactory İşlevi](../windows/createclassfactory-function.md)|Belirtilen sınıf örnekleri oluşturan bir Üreteç oluşturur.|  
|[GetActivationFactory İşlevi](../windows/getactivationfactory-function.md)|Şablon parametresi tarafından belirtilen tür için bir etkinleştirme üreteci alır.|  
|[Make İşlevi](../windows/make-function.md)|Belirtilen Windows çalışma zamanı sınıf başlatır.|  
  
### <a name="macros"></a>Makrolar  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[ActivatableClass Makroları](../windows/activatableclass-macros.md)|Belirtilen sınıfının bir örneğini oluşturabilirsiniz bir Fabrika içeren bir iç önbelleğe doldurur.|  
|[InspectableClass Makrosu](../windows/inspectableclass-macro.md)|Çalışma zamanı sınıf adı ve güven düzeyinde ayarlar.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows Çalışma Zamanı C++ Şablon Kitaplığı (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)