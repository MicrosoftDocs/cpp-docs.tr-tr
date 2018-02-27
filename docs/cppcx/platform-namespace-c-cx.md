---
title: "Platform ad alanı (C + +/ CX) | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- Platform/Platform
dev_langs:
- C++
helpviewer_keywords:
- Platform Namespace (C++/CX)
ms.assetid: b160e822-d424-43d2-ba60-57b0e81f259c
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 08045758313274a3be5626a7c4f2fa5bd54ae891
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="platform-namespace-ccx"></a>Platform ad alanı (C + +/ CX)
Windows çalışma zamanı ile uyumlu olan yerleşik türler içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
using namespace Platform;  
```  
  
### <a name="members"></a>Üyeler  
 **Öznitelikler**  
  
 Platform ad alanı öznitelikleri, sınıflar, numaralandırmalar, arabirimler ve yapılar içerir. Platform Ayrıca iç içe geçmiş ad alanları içerir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|Bayraklar|Numaralandırma bit alan olarak kabul olduğunu gösterir; diğer bir deyişle, bayrakları kümesi.|  
|MTAThread|İş parçacığı modeli bir uygulama için birden çok iş parçacıklı (MTA) olduğunu gösterir.|  
|STAThread|Bir uygulama için iş parçacığı modelini tek iş parçacıklı (STA) olduğunu gösterir.|  
  
 **Sınıflar**  
  
 Platform ad alanı aşağıdaki sınıflar içerir.  
  
|örneği|Açıklama|  
|-----------|-----------------|  
|[Platform::AccessDeniedException Sınıfı](../cppcx/platform-accessdeniedexception-class.md)|Bir kaynak veya özellik için erişim reddedildi tetiklenir.|  
|[Platform::Agile Sınıfı](../cppcx/platform-agile-class.md)|Çevik olmayan bir nesne Çevik bir nesne olarak temsil eder.|  
|[Platform::Array Sınıfı](../cppcx/platform-array-class.md)|Tek boyutlu, değiştirilebilir bir dizisini temsil eder.|  
|[Platform::ArrayReference Sınıfı](../cppcx/platform-arrayreference-class.md)|Kopyalama işlemleri en aza indirmek için başlatma iyileştirilmiş bir dizi temsil eder.|  
|[Platform::Box Sınıfı](../cppcx/platform-box-class.md)|Bu tür uygulama ikili arabirimi (ABI) geçirildiğinde, bir değer türü Windows::Foundation::DateTime veya Int64 gibi yalıtır paketlenmiş bir türü bildirmek için kullanılan veya türü bir değişkende depolanan [Platform::Object ^](../cppcx/platform-object-class.md).|  
|[Platform::ChangedStateException Sınıfı](../cppcx/platform-changedstateexception-class.md)|Bir koleksiyon yineleyici veya bir koleksiyon görünümü yöntemlerini yöntemi sonuçlarını geçersiz kılmalarını üst koleksiyon değiştikten sonra çağrıldığında oluşturulur.|  
|[Platform::ClassNotRegisteredException Sınıfı](../cppcx/platform-classnotregisteredexception-class.md)|Bir COM sınıfı kaydedilmemiş zaman oluşturulur.|  
|[Platform::COMException Sınıfı](../cppcx/platform-comexception-class.md)|Tanınmayan bir değer bir COM yöntemi çağrısından döndürülen olmadığında oluşan özel durumu temsil eder.|  
|[Platform::Delegate Sınıfı](../cppcx/platform-delegate-class.md)|Bir geri çağırma işlevini imza temsil eder.|  
|[Platform::DisconnectedException Sınıfı](../cppcx/platform-disconnectedexception-class.md)|Nesne istemcilerinden.|  
|[Platform::Exception Sınıfı](../cppcx/platform-exception-class.md)|Uygulama yürütmesi sırasında oluşan hataları temsil eder. Özel durumlar için temel sınıf.|  
|[Platform::FailureException Sınıfı](../cppcx/platform-failureexception-class.md)|İşlemi başarısız olduğunda oluşturulur. E_FAIL HRESULT eşdeğeridir.|  
|[Platform::Guid değer Sınıfı](../cppcx/platform-guid-value-class.md)|Bir GUID Windows çalışma zamanı tür sisteminde temsil eder.|  
|[Platform::InvalidArgumentException Sınıfı](../cppcx/platform-invalidargumentexception-class.md)|Bir yöntem için sağlanan bağımsız değişkenlerden biri geçerli değilse oluşturulur.|  
|[Platform::InvalidCastException Sınıfı](../cppcx/platform-invalidcastexception-class.md)|Geçersiz atama veya açık dönüştürme durumlarda oluşturulur.|  
|[Platform::MTAThreadAttribute Sınıfı](../cppcx/platform-mtathreadattribute-class.md)|İş parçacığı modeli bir uygulama için birden çok iş parçacıklı (MTA) olduğunu gösterir.|  
|[Platform::NotImplementedException Sınıfı](../cppcx/platform-notimplementedexception-class.md)|Bir arabirim yöntemini sınıf üzerinde uygulanmadı dönerse oluşturulur.|  
|[Platform::NullReferenceException Sınıfı](../cppcx/platform-nullreferenceexception-class.md)|Null Nesne başvurusu başvuru girişimi olduğunda oluşturulur.|  
|[Platform::Object Sınıfı](../cppcx/platform-object-class.md)|Ortak davranışı sağlayan bir temel sınıf.|  
|[Platform::ObjectDisposedException Sınıfı](../cppcx/platform-objectdisposedexception-class.md)|Silinen bir nesne üzerinde bir işlemi gerçekleştirildiğinde oluşturulur.|  
|[Platform::OperationCanceledException Sınıfı](../cppcx/platform-operationcanceledexception-class.md)|Bir işlem iptal edildiğinde oluşturulur.|  
|[Platform::OutOfBoundsException Sınıfı](../cppcx/platform-outofboundsexception-class.md)|Bir işlem, geçerli aralığın dışında veri erişim girişiminde bulunduğunda oluşur.|  
|[Platform::OutOfMemoryException Sınıfı](../cppcx/platform-outofmemoryexception-class.md)|İşlemi tamamlamak için bellek yetersiz olduğunda oluşturulur.|  
|[Platform::STAThreadAttribute Sınıfı](../cppcx/platform-stathreadattribute-class.md)|Bir uygulama için iş parçacığı modelini tek iş parçacıklı (STA) olduğunu gösterir.|  
|[Platform::String Sınıfı](../cppcx/platform-string-class.md)|Unicode karakter metin temsil etmek için kullanılan sıralı bir koleksiyonu.|  
|[Platform::StringReference Sınıfı](../cppcx/platform-stringreference-class.md)|Kopya ek yükü en az dize arabelleklerinin erişim sağlar.|  
|[Platform::Type Sınıfı](../cppcx/platform-type-class.md)|Bir yerleşik bir kategori numaralandırmasıyla türlerini tanımlar.|  
|[Platform::ValueType Sınıfı](../cppcx/platform-valuetype-class.md)|Taban sınıfı için değer türleri örnekleri.|  
|[Platform::WeakReference Sınıfı](../cppcx/platform-weakreference-class.md)|Başvuru sayımı artırmaz zayıf bir başvuru ref sınıf nesnelerine sağlar.|  
|[Platform::WriteOnlyArray Sınıfı](../cppcx/platform-writeonlyarray-class.md)|FillArray deseni uygulayan yöntemlerde giriş parametresi olarak kullanılan bir tek boyutlu salt yazılır dizisini temsil eder.|  
|[Platform::WrongThreadException Sınıfı](../cppcx/platform-wrongthreadexception-class.md)|Bir iş parçacığı için iş parçacığının grubunu ait olmayan bir proxy nesnesi için bir arabirim işaretçisi aracılığıyla çağırdığında oluşturulur.|  
  
 **Arabirim uygulamaları**  
  
 Platform ad alanı aşağıdaki arabirimlerini tanımlar.  
  
|Arabirim|Açıklama|  
|---------------|-----------------|  
|[Platform::IBox Arabirimi](../cppcx/platform-ibox-interface.md)|Değer türleri parametreleri Platform::Object yazılan işlevlere geçirmek için kullanılan ^.|  
|[Platform::IBoxArray Arabirimi](../cppcx/platform-iboxarray-interface.md)|İşlevlere parametreleri Platform::Array yazılan diziler değer türlerini geçirmek için kullanılan arabirim.|  
|[Platform::IDisposable Arabirimi](../cppcx/platform-idisposable-interface.md)|Yönetilmeyen kaynakları serbest bırakmak için kullanılır.|  
  
 **Sabit Listeleri**  
  
 Platform ad alanı aşağıdaki numaralandırmalar sahiptir.  
  
|Arabirim|Açıklama|  
|---------------|-----------------|  
|[Platform::CallbackContext Numaralandırması](../cppcx/platform-callbackcontext-enumeration.md)|Temsilci Oluşturucu parametresi olarak kullanılan bir numaralandırması. Bu geri çağırma kaynak iş parçacığı veya çağıran iş parçacığı için sıraya olup olmadığını belirler.|  
|[Platform::TypeCode Numaralandırması](../cppcx/platform-typecode-enumeration.md)|Yerleşik türünü temsil eden bir sayısal kategorisini belirtir.|  
  
 **Yapılar**  
  
 Platform ad alanı aşağıdaki yapılar içerir.  
  
|Yapı|Açıklama|  
|---------------|-----------------|  
|[Platform::Enum Sınıfı](../cppcx/platform-enum-class.md)|Adlandırılmış bir sabiti temsil eder.|  
|[Platform::Guid değer Sınıfı](../cppcx/platform-guid-value-class.md)|Bir GUID temsil eder.|  
|[Platform::IntPtr değer Sınıfı](../cppcx/platform-intptr-value-class.md)|Büyüklüğü (32 bit veya 64 bit) platformu için uygun imzalı bir işaretçi.|  
|[Platform::SizeT değer sınıfı](../cppcx/platform-sizet-value-class.md)|Bir nesnenin boyutu temsil etmek için kullanılan bir imzasız veri türü.|  
|[Platform::UIntPtr değer Sınıfı](../cppcx/platform-uintptr-value-class.md)|Büyüklüğü (32 bit veya 64 bit) platformu için uygun olan imzasız bir işaretçi.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform::Collections Namespace](../cppcx/platform-collections-namespace.md)   
 [Platform::Runtime::CompilerServices Namespace](../cppcx/platform-runtime-compilerservices-namespace.md)   
 [Platform::Runtime::InteropServices Namespace](../cppcx/platform-runtime-interopservices-namespace.md)   
 [Platform::Metadata Ad Alanı](../cppcx/platform-metadata-namespace.md)