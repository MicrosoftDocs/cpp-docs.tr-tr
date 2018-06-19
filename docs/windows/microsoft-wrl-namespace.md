---
title: Microsoft::WRL Namespace | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
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
dev_langs:
- C++
helpviewer_keywords:
- WRL namespace
ms.assetid: 01118a8f-f564-4859-b87e-9444848585a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 37d4d5391da4dfb6e25754eb1350224acb97e972
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33881656"
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
|[ActivationFactory Sınıfı](../windows/activationfactory-class.md)|Windows çalışma zamanı tarafından etkinleştirilecek bir veya daha fazla sınıfları sağlar.|  
|[AsyncBase Sınıfı](../windows/asyncbase-class.md)|Windows çalışma zamanı zaman uyumsuz durum makinesinin uygular.|  
|[ClassFactory Sınıfı](../windows/classfactory-class.md)|Temel işlevselliğini uygulayan `IClassFactory` arabirimi.|  
|[ComPtr Sınıfı](../windows/comptr-class.md)|Oluşturur bir *akıllı işaretçi* şablon parametresi tarafından belirtilen arabirimi temsil eden tür. ComPtr otomatik olarak bir başvuru sayısı için temel arabirim işaretçisi tutar ve başvuru sayısı sıfır olarak gittiğinde arabirimi serbest bırakır.|  
|[DeferrableEventArgs Sınıfı](../windows/deferrableeventargs-class.md)|Deferrals için olay bağımsız değişken türleri için kullanılan bir şablon sınıfı.|  
|[EventSource Sınıfı](../windows/eventsource-class.md)|Bir olayı temsil eder. `EventSource` üye işlevleri eklemek, kaldırmak ve olay işleyicilerini çağırma.|  
|[FtmBase Sınıfı](../windows/ftmbase-class.md)|Ücretsiz iş parçacıklı Sıralayıcı nesneyi temsil eder.|  
|[Modül Sınıfı](../windows/module-class.md)|İlgili nesneler koleksiyonunu temsil eder.|  
|[RuntimeClass Sınıfı](../windows/runtimeclass-class.md)|Belirtilen sayıda arabirimleri devralır ve belirtilen Windows çalışma zamanı, klasik COM ve zayıf başvuru desteği sağlar başlatılan bir sınıfı temsil eder.|  
|[SimpleActivationFactory Sınıfı](../windows/simpleactivationfactory-class.md)|Windows çalışma zamanı veya klasik COM temel sınıf oluşturmak için temel bir mekanizma sağlar.|  
|[SimpleClassFactory Sınıfı](../windows/simpleclassfactory-class.md)|Bir taban sınıf oluşturmak için temel bir mekanizma sağlar.|  
|[WeakRef Sınıfı](../windows/weakref-class.md)|Temsil eden bir *zayıf başvuru* yalnızca Windows çalışma zamanı tarafından değil klasik COM kullanılabilir Zayıf başvuru olabilir ya da erişilebilir olmayabilir bir nesneyi temsil eder.|  
  
### <a name="structures"></a>Yapılar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ChainInterfaces Yapısı](../windows/chaininterfaces-structure.md)|Arabirim kimlikleri kümesine uygulanabilir doğrulama ve başlatma işlevleri belirtir.|  
|[CloakedIid Yapısı](../windows/cloakediid-structure.md)|RuntimeClass, uygular ve Chainınterfaces şablonların belirtilen arabirim IID listesinde erişilebilir değil gösterir.|  
|[Implements Yapısı](../windows/implements-structure.md)|QueryInterface ve GetIid için belirtilen arabirimlerini uygular.|  
|[MixIn Yapısı](../windows/mixin-structure.md)|Bir çalışma zamanı sınıf Windows Çalışma Zamanı Modülü arabirimler, varsa ve daha sonra klasik COM arabirimleri türetilen sağlar.|  
|[RuntimeClassFlags Yapısı](../windows/runtimeclassflags-structure.md)|Öğesinin bir örneği için türünü içeren bir [RuntimeClass](../windows/runtimeclass-class.md).|  
  
### <a name="enumerations"></a>Numaralandırmalar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[AsyncResultType Sabit Listesi](../windows/asyncresulttype-enumeration.md)|GetResults() yöntemi tarafından döndürülen sonuç türü belirtir.|  
|[ModuleType Sabit Listesi](../windows/moduletype-enumeration.md)|Bir modülü bir işlem sunucusuna veya bir işlem dışı sunucusuna desteklemesi gerekip gerekmediğini belirtir.|  
|[RuntimeClassType Sabit Listesi](../windows/runtimeclasstype-enumeration.md)|Türünü belirtir. [RuntimeClass](../windows/runtimeclass-class.md) desteklenen örneği.|  
  
### <a name="functions"></a>İşlevler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[AsWeak İşlevi](../windows/asweak-function.md)|Belirtilen bir örneğine zayıf başvuru alır.|  
|[Geri çağırma işlevi](../windows/callback-function-windows-runtime-cpp-template-library.md)|Bir geri çağırma yöntemi, üye işlevi olan bir nesne oluşturur.|  
|[CreateActivationFactory İşlevi](../windows/createactivationfactory-function.md)|Windows çalışma zamanı tarafından etkinleştirilebilir belirtilen sınıfının örnekleri oluşturan bir Üreteç oluşturur.|  
|[CreateClassFactory İşlevi](../windows/createclassfactory-function.md)|Belirtilen sınıf örnekleri oluşturan bir Üreteç oluşturur.|  
|[Make İşlevi](../windows/make-function.md)|Belirtilen Windows çalışma zamanı sınıf başlatır.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** async.h, client.h, corewrappers.h, event.h, ftm.h, implements.h, internal.h, module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Wrappers Ad Alanı](../windows/microsoft-wrl-wrappers-namespace.md)