---
title: "Anahtar WRL API'leri kategoriye göre | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
ms.assetid: 7367bacf-6b7c-4ecd-a0ce-a662db46fc66
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f4748220f0115f9bd05d051ca5f1bb3f6fcc8ded
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="key-wrl-apis-by-category"></a>Kategoriye Göre Başlıca WRL API'leri
Birincil Windows çalışma zamanı C++ Şablon kitaplığı sınıflar, yapılar, İşlevler ve makrolar aşağıdaki tablolarda listelenmektedir. Yardımcı ad alanları ve sınıfları yapılardan göz ardı edilir. Bu listeler ad alanlarına göre düzenlenen API belgelerine kullanmasıdır.  
  
### <a name="classes"></a>Sınıflar  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[ActivationFactory sınıfı](../windows/activationfactory-class.md)|Windows çalışma zamanı tarafından etkinleştirilecek bir veya daha fazla sınıfları sağlar.|  
|[AsyncBase sınıfı](../windows/asyncbase-class.md)|Windows çalışma zamanı zaman uyumsuz durum makinesinin uygular.|  
|[ClassFactory sınıfı](../windows/classfactory-class.md)|Temel işlevselliğini uygulayan `IClassFactory` arabirimi.|  
|[ComPtr sınıfı](../windows/comptr-class.md)|Oluşturur bir *akıllı işaretçi* şablon parametresi tarafından belirtilen arabirimi temsil eden tür. ComPtr otomatik olarak bir başvuru sayısı için temel arabirim işaretçisi tutar ve başvuru sayısı sıfır olarak gittiğinde arabirimi serbest bırakır.|  
|[Olay sınıfı (Windows çalışma zamanı C++ Şablon kitaplığı)](../windows/event-class-windows-runtime-cpp-template-library.md)|Bir olayı temsil eder.|  
|[EventSource sınıfı](../windows/eventsource-class.md)|Bir olayı temsil eder. `EventSource`üye işlevleri eklemek, kaldırmak ve olay işleyicilerini çağırma.|  
|[FtmBase sınıfı](../windows/ftmbase-class.md)|Ücretsiz iş parçacıklı Sıralayıcı nesneyi temsil eder.|  
|[HandleT sınıfı](../windows/handlet-class.md)|Bir tanıtıcı nesneyi temsil eder.|  
|[HString sınıfı](../windows/hstring-class.md)|HSTRING tanıtıcıları yönlendirmek için destek sağlar.|  
|[HStringReference sınıfı](../windows/hstringreference-class.md)|Varolan bir dizeden oluşturulmuş bir HSTRING temsil eder.|  
|[Modül sınıfı](../windows/module-class.md)|İlgili nesneler koleksiyonunu temsil eder.|  
|[Module::GenericReleaseNotifier sınıfı](../windows/module-genericreleasenotifier-class.md)|Son nesne geçerli modülünde yayımlandığında, bir olay işleyiciyi çağırır. Olay işleyicisi lambda, functor veya işaretçi işlevi belirtilir.|  
|[Module::MethodReleaseNotifier sınıfı](../windows/module-methodreleasenotifier-class.md)|Son nesne geçerli modülünde yayımlandığında, bir olay işleyiciyi çağırır. Olay işleyicisi bir nesne ve kendi yöntemi için işaretçi üyesi tarafından belirtilir.|  
|[Module::ReleaseNotifier sınıfı](../windows/module-releasenotifier-class.md)|Bir modül son nesnesinde yayımlandığında, bir olay işleyiciyi çağırır.|  
|[Roınitializewrapper sınıfı](../windows/roinitializewrapper-class.md)|Windows çalışma zamanı başlatır.|  
|[RuntimeClass sınıfı](../windows/runtimeclass-class.md)|Belirtilen sayıda arabirimleri devralır ve belirtilen Windows çalışma zamanı, klasik COM ve zayıf başvuru desteği sağlar başlatılan bir sınıfı temsil eder.|  
|[SimpleActivationFactory sınıfı](../windows/simpleactivationfactory-class.md)|Windows çalışma zamanı veya klasik COM temel sınıf oluşturmak için temel bir mekanizma sağlar.|  
|[SimpleClassFactory sınıfı](../windows/simpleclassfactory-class.md)|Bir taban sınıf oluşturmak için temel bir mekanizma sağlar.|  
|[WeakRef sınıfı](../windows/weakref-class.md)|Temsil eden bir *zayıf başvuru* yalnızca Windows çalışma zamanı tarafından değil klasik COM kullanılabilir Zayıf başvuru olabilir ya da erişilebilir olmayabilir bir nesneyi temsil eder.|  
  
### <a name="structures"></a>Yapılar  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Chainınterfaces yapısı](../windows/chaininterfaces-structure.md)|Arabirim kimlikleri kümesine uygulanabilir doğrulama ve başlatma işlevleri belirtir.|  
|[Cloakedıid yapısı](../windows/cloakediid-structure.md)|Gösterir `RuntimeClass`, `Implements` ve `ChainInterfaces` şablonları belirtilen arabirim IID listesinde erişilebilir değil.|  
|[Implements yapısı](../windows/implements-structure.md)|Implements `QueryInterface` ve `GetIid` belirtilen arabirimleri için.|  
|[Mixın yapısı](../windows/mixin-structure.md)|Bir çalışma zamanı sınıf Windows Çalışma Zamanı Modülü arabirimler, varsa ve daha sonra klasik COM arabirimleri türetilen sağlar.|  
  
### <a name="functions"></a>İşlevler  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Activateınstance işlevi](../windows/activateinstance-function.md)|Kaydeder ve bir belirtilen sınıf kimliği tanımlanan belirtilen bir türün bir örneğini alır.|  
|[AsWeak işlevi](../windows/asweak-function.md)|Belirtilen bir örneğine zayıf başvuru alır.|  
|[Geri çağırma işlevi](../windows/callback-function-windows-runtime-cpp-template-library.md)|Bir geri çağırma yöntemi, üye işlevi olan bir nesne oluşturur.|  
|[CreateActivationFactory işlevi](../windows/createactivationfactory-function.md)|Windows çalışma zamanı tarafından etkinleştirilebilir belirtilen sınıfının örnekleri oluşturan bir Üreteç oluşturur.|  
|[CreateClassFactory işlevi](../windows/createclassfactory-function.md)|Belirtilen sınıf örnekleri oluşturan bir Üreteç oluşturur.|  
|[GetActivationFactory işlevi](../windows/getactivationfactory-function.md)|Şablon parametresi tarafından belirtilen tür için bir etkinleştirme üreteci alır.|  
|[Make işlevi](../windows/make-function.md)|Belirtilen Windows çalışma zamanı sınıf başlatır.|  
  
### <a name="macros"></a>Makrolar  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[ActivatableClass makroları](../windows/activatableclass-macros.md)|Belirtilen sınıfının bir örneğini oluşturabilirsiniz bir Fabrika içeren bir iç önbelleğe doldurur.|  
|[Inspectableclass makrosu](../windows/inspectableclass-macro.md)|Çalışma zamanı sınıf adı ve güven düzeyinde ayarlar.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows çalışma zamanı C++ Şablon kitaplığı (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)