---
title: 'Microsoft::wrl:: details Namespace | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
ms.assetid: d71fe149-d804-4c6f-961d-43fe21ef8630
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 284d9393f7f967230fd3f7deb497a0e245d78dec
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="microsoftwrldetails-namespace"></a>Microsoft::WRL::Details Ad Alanı
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
namespace Microsoft::WRL::Details;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="classes"></a>Sınıflar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ComPtrRef sınıfı](../windows/comptrref-class.md)|ComPtr türünde bir nesneye başvuru temsil eden\<T >.|  
|[ComPtrRefBase sınıfı](../windows/comptrrefbase-class.md)|İçin temel sınıfı temsil eder [ComPtrRef](../windows/comptrref-class.md) sınıfı.|  
|[DontUseNewUseMake sınıfı](../windows/dontusenewusemake-class.md)|İşleç engel `new` içinde `RuntimeClass`. Sonuç olarak, kullanmalısınız [olun işlevi](../windows/make-function.md) yerine.|  
|[EventTargetArray sınıfı](../windows/eventtargetarray-class.md)|Olay işleyicileri dizisini temsil eder.|  
|[MakeAllocator sınıfı](../windows/makeallocator-class.md)|Zayıf başvuru desteği olmadan veya ile bir activatable sınıfı için bellek ayırır.|  
|[ModuleBase sınıfı](../windows/modulebase-class.md)|Temel sınıfını temsil eden [Modülü](../windows/module-class.md) sınıfları.|  
|[Removeıunknown sınıfı](../windows/removeiunknown-class.md)|Eşdeğer olan bir tür yapar bir `IUnknown`-tabanlı ancak türünde sanal olmayan `QueryInterface`, `AddRef`, ve `Release` yöntemleri.|  
|[WeakReference sınıfı](../windows/weakreference-class1.md)|Temsil eden bir *zayıf başvuru* kullanılabilecek Windows çalışma zamanı veya klasik COM Zayıf başvuru olabilir ya da erişilebilir olmayabilir bir nesneyi temsil eder.|  
  
### <a name="structures"></a>Yapılar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ArgTraits yapısı](../windows/argtraits-structure.md)|Belirtilen temsilci arabirimi ve belirtilen bir parametre sayısı bir anonim üye işlevi bildirir.|  
|[ArgTraitsHelper yapısı](../windows/argtraitshelper-structure.md)|Yardımcı genel özelliklerini temsilci bağımsız değişkenleri tanımlayın.|  
|[BoolStruct yapısı](../windows/boolstruct-structure.md)|Bir ComPtr bir arabirim nesne ömrü yönetme olup olmadığını tanımlar. BoolStruct tarafından dahili olarak kullanılan [BoolType()](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md) işleci.|  
|[CreatorMap yapısı](../windows/creatormap-structure.md)|Başlatma, kaydetme ve nesneleri kaydı hakkında bilgi içerir.|  
|[DerefHelper yapısı](../windows/derefhelper-structure.md)|Dereferenced işaretçi temsil `T*` şablon parametresi.|  
|[Enableıf yapısı](../windows/enableif-structure.md)|İlk şablon parametresi değerlendirilirse ikinci şablon parametresi tarafından belirtilen türde bir veri üyesi tanımlar `true`.|  
|[FactoryCache yapısı](../windows/factorycache-structure.md)|Bir sınıf fabrikası ve kayıtlı Windows çalışma zamanı veya COM sınıf nesnesi tanımlayan bir değer konumunu içerir.|  
|[Implementsbase yapısı](../windows/implementsbase-structure.md)|Şablon parametresi türlerinde doğrulamak için kullanılan [Implements yapısı](../windows/implements-structure.md).|  
|[Implementshelper yapısı](../windows/implementshelper-structure.md)|Uygulama yardımcı [uygulayan](../windows/implements-structure.md) yapısı.|  
|[Interfacelist yapısı](../windows/interfacelist-structure.md)|Arabirimleri özyinelemeli listesini oluşturmak için kullanılır.|  
|[Interfacelisthelper yapısı](../windows/interfacelisthelper-structure.md)|Derlemeler bir `InterfaceList` türü tarafından belirtilen şablonu parametre bağımsız değişkenlerini uygulama yinelemeli olarak.|  
|[Interfacetraits yapısı](../windows/interfacetraits-structure.md)|Arabirim genel özelliklerini uygular.|  
|[Invokehelper yapısı](../windows/invokehelper-structure.md)|Belirtilen sayı ve bağımsız değişken türü bağlı olması yöntemin bir uygulaması, sağlar.|  
|[Isbaseofstrict yapısı](../windows/isbaseofstrict-structure.md)|Başka bir taban bir türü olup olmadığını sınar.|  
|[Issame yapısı](../windows/issame-structure.md)|Belirtilen türü testleri bir türü belirtilmiş olup olmadığını başka aynıdır.|  
|[Nil yapısı](../windows/nil-structure.md)|Belirtilmeyen, isteğe bağlı şablon parametresi göstermek için kullanılır.|  
|[RemoveReference yapısı](../windows/removereference-structure.md)|Belirtilen sınıf şablon parametre başvurusu veya rvalue başvuru ayırdedici nitelik kaldırır.|  
|[RuntimeClassBase yapısı](../windows/runtimeclassbase-structure.md)|Algılamak için kullanılan `RuntimeClass` içinde [olun](../windows/make-function.md) işlevi.|  
|[RuntimeClassBaseT yapısı](../windows/runtimeclassbaset-structure.md)|İçin yardımcı yöntemleri sağlar `QueryInterface` işlemleri ve alma arabirimi kimlikleri.|  
|[Verifyınheritancehelper yapısı](../windows/verifyinheritancehelper-structure.md)|Başka bir arabiriminden bir arabirim türetilmiş olup olmadığını sınar.|  
|[Verifyınterfacehelper yapısı](../windows/verifyinterfacehelper-structure.md)|Şablon parametresi tarafından belirtilen arabirimi belirli gereksinimleri karşıladığını doğrular.|  
  
### <a name="enumerations"></a>Numaralandırmalar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Asyncstatusınternal numaralandırması](../windows/asyncstatusinternal-enumeration.md)|Zaman uyumsuz işlemler durumu için iç numaralandırmalar arasında bir eşleme belirtir ve **Windows::Foundation::AsyncStatus** numaralandırması.|  
  
### <a name="functions"></a>İşlevler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ActivationFactoryCallback işlevi](../windows/activationfactorycallback-function.md)|Belirtilen etkinleştirme kimliği için etkinleştirme üretecini alır|  
|[Move işlevi](../windows/move-function.md)|Belirtilen bağımsız değişken bir konumdan diğerine taşır.|  
|[RaiseException işlevi](../windows/raiseexception-function.md)|Çağıran iş parçacığı bir özel durumla başlatır.|  
|[Swap işlevi (Windows çalışma zamanı C++ Şablon kitaplığı)](../windows/swap-function-windows-runtime-cpp-template-library.md)|İki belirtilen bağımsız değişken değerlerini değiş tokuş eder.|  
|[TerminateMap işlevi](../windows/terminatemap-function.md)|Sınıf oluşturucuları belirtilen modülde kapatır.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** async.h, client.h, corewrappers.h, event.h, ftm.h, implements.h, internal.h, module.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Namespace](../windows/microsoft-wrl-namespace.md)   
 [Microsoft::wrl:: Wrappers Namespace](../windows/microsoft-wrl-wrappers-namespace.md)