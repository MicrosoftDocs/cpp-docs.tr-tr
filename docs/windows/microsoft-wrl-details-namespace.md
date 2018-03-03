---
title: 'Microsoft::wrl:: details Namespace | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: d71fe149-d804-4c6f-961d-43fe21ef8630
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f005969908252602cb2fb4bdd73d3b55ae342a99
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
|[ComPtrRef Sınıfı](../windows/comptrref-class.md)|ComPtr türünde bir nesneye başvuru temsil eden\<T >.|  
|[ComPtrRefBase Sınıfı](../windows/comptrrefbase-class.md)|İçin temel sınıfı temsil eder [ComPtrRef](../windows/comptrref-class.md) sınıfı.|  
|[DontUseNewUseMake Sınıfı](../windows/dontusenewusemake-class.md)|İşleç engel `new` içinde `RuntimeClass`. Sonuç olarak, kullanmalısınız [olun işlevi](../windows/make-function.md) yerine.|  
|[EventTargetArray Sınıfı](../windows/eventtargetarray-class.md)|Olay işleyicileri dizisini temsil eder.|  
|[MakeAllocator Sınıfı](../windows/makeallocator-class.md)|Zayıf başvuru desteği olmadan veya ile bir activatable sınıfı için bellek ayırır.|  
|[ModuleBase Sınıfı](../windows/modulebase-class.md)|Temel sınıfını temsil eden [Modülü](../windows/module-class.md) sınıfları.|  
|[RemoveIUnknown Sınıfı](../windows/removeiunknown-class.md)|Eşdeğer olan bir tür yapar bir `IUnknown`-tabanlı ancak türünde sanal olmayan `QueryInterface`, `AddRef`, ve `Release` yöntemleri.|  
|[WeakReference sınıfı](../windows/weakreference-class1.md)|Temsil eden bir *zayıf başvuru* kullanılabilecek Windows çalışma zamanı veya klasik COM Zayıf başvuru olabilir ya da erişilebilir olmayabilir bir nesneyi temsil eder.|  
  
### <a name="structures"></a>Yapılar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ArgTraits Yapısı](../windows/argtraits-structure.md)|Belirtilen temsilci arabirimi ve belirtilen bir parametre sayısı bir anonim üye işlevi bildirir.|  
|[ArgTraitsHelper Yapısı](../windows/argtraitshelper-structure.md)|Yardımcı genel özelliklerini temsilci bağımsız değişkenleri tanımlayın.|  
|[BoolStruct Yapısı](../windows/boolstruct-structure.md)|Bir ComPtr bir arabirim nesne ömrü yönetme olup olmadığını tanımlar. BoolStruct tarafından dahili olarak kullanılan [BoolType()](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md) işleci.|  
|[CreatorMap Yapısı](../windows/creatormap-structure.md)|Başlatma, kaydetme ve nesneleri kaydı hakkında bilgi içerir.|  
|[DerefHelper Yapısı](../windows/derefhelper-structure.md)|Dereferenced işaretçi temsil `T*` şablon parametresi.|  
|[EnableIf Yapısı](../windows/enableif-structure.md)|İlk şablon parametresi değerlendirilirse ikinci şablon parametresi tarafından belirtilen türde bir veri üyesi tanımlar `true`.|  
|[FactoryCache Yapısı](../windows/factorycache-structure.md)|Bir sınıf fabrikası ve kayıtlı Windows çalışma zamanı veya COM sınıf nesnesi tanımlayan bir değer konumunu içerir.|  
|[ImplementsBase Yapısı](../windows/implementsbase-structure.md)|Şablon parametresi türlerinde doğrulamak için kullanılan [Implements yapısı](../windows/implements-structure.md).|  
|[ImplementsHelper Yapısı](../windows/implementshelper-structure.md)|Uygulama yardımcı [uygulayan](../windows/implements-structure.md) yapısı.|  
|[InterfaceList Yapısı](../windows/interfacelist-structure.md)|Arabirimleri özyinelemeli listesini oluşturmak için kullanılır.|  
|[InterfaceListHelper Yapısı](../windows/interfacelisthelper-structure.md)|Derlemeler bir `InterfaceList` türü tarafından belirtilen şablonu parametre bağımsız değişkenlerini uygulama yinelemeli olarak.|  
|[InterfaceTraits Yapısı](../windows/interfacetraits-structure.md)|Arabirim genel özelliklerini uygular.|  
|[InvokeHelper Yapısı](../windows/invokehelper-structure.md)|Belirtilen sayı ve bağımsız değişken türü bağlı olması yöntemin bir uygulaması, sağlar.|  
|[IsBaseOfStrict Yapısı](../windows/isbaseofstrict-structure.md)|Başka bir taban bir türü olup olmadığını sınar.|  
|[IsSame Yapısı](../windows/issame-structure.md)|Belirtilen türü testleri bir türü belirtilmiş olup olmadığını başka aynıdır.|  
|[Nil Yapısı](../windows/nil-structure.md)|Belirtilmeyen, isteğe bağlı şablon parametresi göstermek için kullanılır.|  
|[RemoveReference Yapısı](../windows/removereference-structure.md)|Belirtilen sınıf şablon parametre başvurusu veya rvalue başvuru ayırdedici nitelik kaldırır.|  
|[RuntimeClassBase Yapısı](../windows/runtimeclassbase-structure.md)|Algılamak için kullanılan `RuntimeClass` içinde [olun](../windows/make-function.md) işlevi.|  
|[RuntimeClassBaseT Yapısı](../windows/runtimeclassbaset-structure.md)|İçin yardımcı yöntemleri sağlar `QueryInterface` işlemleri ve alma arabirimi kimlikleri.|  
|[VerifyInheritanceHelper Yapısı](../windows/verifyinheritancehelper-structure.md)|Başka bir arabiriminden bir arabirim türetilmiş olup olmadığını sınar.|  
|[VerifyInterfaceHelper Yapısı](../windows/verifyinterfacehelper-structure.md)|Şablon parametresi tarafından belirtilen arabirimi belirli gereksinimleri karşıladığını doğrular.|  
  
### <a name="enumerations"></a>Numaralandırmalar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[AsyncStatusInternal Sabit Listesi](../windows/asyncstatusinternal-enumeration.md)|Zaman uyumsuz işlemler durumu için iç numaralandırmalar arasında bir eşleme belirtir ve **Windows::Foundation::AsyncStatus** numaralandırması.|  
  
### <a name="functions"></a>İşlevler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ActivationFactoryCallback İşlevi](../windows/activationfactorycallback-function.md)|Belirtilen etkinleştirme kimliği için etkinleştirme üretecini alır|  
|[Move İşlevi](../windows/move-function.md)|Belirtilen bağımsız değişken bir konumdan diğerine taşır.|  
|[RaiseException İşlevi](../windows/raiseexception-function.md)|Çağıran iş parçacığı bir özel durumla başlatır.|  
|[Swap İşlevi (Windows Çalışma Zamanı C++ Şablon Kitaplığı)](../windows/swap-function-windows-runtime-cpp-template-library.md)|İki belirtilen bağımsız değişken değerlerini değiş tokuş eder.|  
|[TerminateMap İşlevi](../windows/terminatemap-function.md)|Sınıf oluşturucuları belirtilen modülde kapatır.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** async.h, client.h, corewrappers.h, event.h, ftm.h, implements.h, internal.h, module.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Namespace](../windows/microsoft-wrl-namespace.md)   
 [Microsoft::WRL::Wrappers Ad Alanı](../windows/microsoft-wrl-wrappers-namespace.md)