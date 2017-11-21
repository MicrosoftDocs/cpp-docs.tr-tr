---
title: Microsoft::WRL Namespace | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
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
dev_langs: C++
helpviewer_keywords: WRL namespace
ms.assetid: 01118a8f-f564-4859-b87e-9444848585a1
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7b3c3bef713bd63b7b82761ce36ab039556e63c0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="microsoftwrl-namespace"></a>Microsoft::WRL Ad Alanı
Windows çalışma zamanı C++ Şablon kitaplığı yapmak temel türlerini tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
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
|[ActivationFactory sınıfı](../windows/activationfactory-class.md)|Windows çalışma zamanı tarafından etkinleştirilecek bir veya daha fazla sınıfları sağlar.|  
|[AsyncBase sınıfı](../windows/asyncbase-class.md)|Windows çalışma zamanı zaman uyumsuz durum makinesinin uygular.|  
|[ClassFactory sınıfı](../windows/classfactory-class.md)|Temel işlevselliğini uygulayan `IClassFactory` arabirimi.|  
|[ComPtr sınıfı](../windows/comptr-class.md)|Oluşturur bir *akıllı işaretçi* şablon parametresi tarafından belirtilen arabirimi temsil eden tür. ComPtr otomatik olarak bir başvuru sayısı için temel arabirim işaretçisi tutar ve başvuru sayısı sıfır olarak gittiğinde arabirimi serbest bırakır.|  
|[DeferrableEventArgs sınıfı](../windows/deferrableeventargs-class.md)|Deferrals için olay bağımsız değişken türleri için kullanılan bir şablon sınıfı.|  
|[EventSource sınıfı](../windows/eventsource-class.md)|Bir olayı temsil eder. `EventSource`üye işlevleri eklemek, kaldırmak ve olay işleyicilerini çağırma.|  
|[FtmBase sınıfı](../windows/ftmbase-class.md)|Ücretsiz iş parçacıklı Sıralayıcı nesneyi temsil eder.|  
|[Modül sınıfı](../windows/module-class.md)|İlgili nesneler koleksiyonunu temsil eder.|  
|[RuntimeClass sınıfı](../windows/runtimeclass-class.md)|Belirtilen sayıda arabirimleri devralır ve belirtilen Windows çalışma zamanı, klasik COM ve zayıf başvuru desteği sağlar başlatılan bir sınıfı temsil eder.|  
|[SimpleActivationFactory sınıfı](../windows/simpleactivationfactory-class.md)|Windows çalışma zamanı veya klasik COM temel sınıf oluşturmak için temel bir mekanizma sağlar.|  
|[SimpleClassFactory sınıfı](../windows/simpleclassfactory-class.md)|Bir taban sınıf oluşturmak için temel bir mekanizma sağlar.|  
|[WeakRef sınıfı](../windows/weakref-class.md)|Temsil eden bir *zayıf başvuru* yalnızca Windows çalışma zamanı tarafından değil klasik COM kullanılabilir Zayıf başvuru olabilir ya da erişilebilir olmayabilir bir nesneyi temsil eder.|  
  
### <a name="structures"></a>Yapılar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Chainınterfaces yapısı](../windows/chaininterfaces-structure.md)|Arabirim kimlikleri kümesine uygulanabilir doğrulama ve başlatma işlevleri belirtir.|  
|[Cloakedıid yapısı](../windows/cloakediid-structure.md)|RuntimeClass, uygular ve Chainınterfaces şablonların belirtilen arabirim IID listesinde erişilebilir değil gösterir.|  
|[Implements yapısı](../windows/implements-structure.md)|QueryInterface ve GetIid için belirtilen arabirimlerini uygular.|  
|[Mixın yapısı](../windows/mixin-structure.md)|Bir çalışma zamanı sınıf Windows Çalışma Zamanı Modülü arabirimler, varsa ve daha sonra klasik COM arabirimleri türetilen sağlar.|  
|[RuntimeClassFlags yapısı](../windows/runtimeclassflags-structure.md)|Öğesinin bir örneği için türünü içeren bir [RuntimeClass](../windows/runtimeclass-class.md).|  
  
### <a name="enumerations"></a>Numaralandırmalar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[AsyncResultType numaralandırması](../windows/asyncresulttype-enumeration.md)|GetResults() yöntemi tarafından döndürülen sonuç türü belirtir.|  
|[ModuleType numaralandırması](../windows/moduletype-enumeration.md)|Bir modülü bir işlem sunucusuna veya bir işlem dışı sunucusuna desteklemesi gerekip gerekmediğini belirtir.|  
|[RuntimeClassType numaralandırması](../windows/runtimeclasstype-enumeration.md)|Türünü belirtir. [RuntimeClass](../windows/runtimeclass-class.md) desteklenen örneği.|  
  
### <a name="functions"></a>İşlevler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[AsWeak işlevi](../windows/asweak-function.md)|Belirtilen bir örneğine zayıf başvuru alır.|  
|[Geri çağırma işlevi](../windows/callback-function-windows-runtime-cpp-template-library.md)|Bir geri çağırma yöntemi, üye işlevi olan bir nesne oluşturur.|  
|[CreateActivationFactory işlevi](../windows/createactivationfactory-function.md)|Windows çalışma zamanı tarafından etkinleştirilebilir belirtilen sınıfının örnekleri oluşturan bir Üreteç oluşturur.|  
|[CreateClassFactory işlevi](../windows/createclassfactory-function.md)|Belirtilen sınıf örnekleri oluşturan bir Üreteç oluşturur.|  
|[Make işlevi](../windows/make-function.md)|Belirtilen Windows çalışma zamanı sınıf başlatır.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** async.h, client.h, corewrappers.h, event.h, ftm.h, implements.h, internal.h, module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::wrl:: Wrappers Namespace](../windows/microsoft-wrl-wrappers-namespace.md)