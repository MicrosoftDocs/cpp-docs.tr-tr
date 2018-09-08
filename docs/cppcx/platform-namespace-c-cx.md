---
title: Platform ad alanı (C + +/ CX) | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- Platform/Platform
dev_langs:
- C++
helpviewer_keywords:
- Platform Namespace (C++/CX)
ms.assetid: b160e822-d424-43d2-ba60-57b0e81f259c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eb88b7b0d032ba5ff4e629279d61ad711ea42f4b
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44100463"
---
# <a name="platform-namespace-ccx"></a>Platform ad alanı (C + +/ CX)

Windows çalışma zamanı ile uyumlu olan yerleşik türler içerir.

## <a name="syntax"></a>Sözdizimi

```cpp
using namespace Platform;
```

### <a name="members"></a>Üyeler

**Öznitelikler**

Platform ad alanı öznitelikleri, sınıflar, numaralandırmalar, arabirimler ve yapıları içerir. Platform, ayrıca iç içe ad alanlarını içerir.

|Öznitelik|Açıklama|
|---------------|-----------------|
|Bayraklar|Bir numaralandırma bir bit alanı olarak davranılıp gösterir. diğer bir deyişle, bir dizi bayrakları.|
|MTAThread|Bir uygulama için iş parçacığı modeli çok iş parçacıklı grup (MTA) olduğunu gösterir.|
|STAThread|Bir uygulama için iş parçacığı modeli tek iş parçacıklı grup (STA) olduğunu gösterir.|

**Sınıflar**

Platform ad alanı, aşağıdaki sınıfları içerir.

|örneği|Açıklama|
|-----------|-----------------|
|[Platform::AccessDeniedException Sınıfı](../cppcx/platform-accessdeniedexception-class.md)|Bir kaynağa veya özellik erişimi reddedilirse oluşturulur.|
|[Platform::Agile Sınıfı](../cppcx/platform-agile-class.md)|Çevik olmayan bir nesne, Çevik bir nesne olarak temsil eder.|
|[Platform::Array Sınıfı](../cppcx/platform-array-class.md)|Tek boyutlu, değiştirilebilir bir dizi temsil eder.|
|[Platform::ArrayReference Sınıfı](../cppcx/platform-arrayreference-class.md)|Dizi, başlatma kopyalama işlemlerini en aza indirmek için optimize edilmiştir temsil eder.|
|[Platform::Box Sınıfı](../cppcx/platform-box-class.md)|Uygulama ikili arabiriminde (ABI) bu tür geçirildiğinde Windows::Foundation::DateTime veya Int64 gibi bir değer türü sarmalayan bir Kutulu türü bildirmek için kullanılan veya türünde bir değişkende depolanan [Platform::Object ^](../cppcx/platform-object-class.md).|
|[Platform::ChangedStateException Sınıfı](../cppcx/platform-changedstateexception-class.md)|Yöntemin sonuçları geçersiz kılmalarını üst koleksiyon değiştikten sonra bir koleksiyon yineleyici veya koleksiyon görünümü yöntemler çağrıldığında oluşturulur.|
|[Platform::ClassNotRegisteredException Sınıfı](../cppcx/platform-classnotregisteredexception-class.md)|Bir COM sınıfı kaydedilmemiş olduğu zaman oluşturulur.|
|[Platform::COMException Sınıfı](../cppcx/platform-comexception-class.md)|Tanınmayan değer bir COM yöntem çağrısından döndürülen olmadığında oluşan özel durumu temsil eder.|
|[Platform::Delegate Sınıfı](../cppcx/platform-delegate-class.md)|Bir geri çağırma işlevini imzası temsil eder.|
|[Platform::DisconnectedException Sınıfı](../cppcx/platform-disconnectedexception-class.md)|Nesnenin, istemcileriyle bağlantısı kesildi.|
|[Platform::Exception Sınıfı](../cppcx/platform-exception-class.md)|Uygulama yürütme sırasında oluşan hataları temsil eder. Özel durumlar için temel sınıf.|
|[Platform::FailureException Sınıfı](../cppcx/platform-failureexception-class.md)|İşlemi başarısız olduğunda oluşturulur. Bunu E_FAIL HRESULT eşdeğerdir.|
|[Platform::Guid değer Sınıfı](../cppcx/platform-guid-value-class.md)|Bir GUID, Windows çalışma zamanı tür sisteminde temsil eder.|
|[Platform::InvalidArgumentException Sınıfı](../cppcx/platform-invalidargumentexception-class.md)|Bir yöntem için sağlanan bağımsız değişkenlerden biri geçerli olmadığında oluşturulur.|
|[Platform::InvalidCastException Sınıfı](../cppcx/platform-invalidcastexception-class.md)|Geçersiz atama veya açık dönüştürme durumlarda oluşturulur.|
|[Platform::MTAThreadAttribute Sınıfı](../cppcx/platform-mtathreadattribute-class.md)|Bir uygulama için iş parçacığı modeli çok iş parçacıklı grup (MTA) olduğunu gösterir.|
|[Platform::NotImplementedException Sınıfı](../cppcx/platform-notimplementedexception-class.md)|Sınıf üzerinde bir arabirim yönteminin uygulanmadı durum.|
|[Platform::NullReferenceException Sınıfı](../cppcx/platform-nullreferenceexception-class.md)|Bir null Nesne başvurusu başvuru girişimi olduğunda oluşturulur.|
|[Platform::Object Sınıfı](../cppcx/platform-object-class.md)|Genel davranış sağlayan bir temel sınıf.|
|[Platform::ObjectDisposedException Sınıfı](../cppcx/platform-objectdisposedexception-class.md)|Silinen bir nesne üzerinde bir işlem gerçekleştirildiğinde oluşturulur.|
|[Platform::OperationCanceledException Sınıfı](../cppcx/platform-operationcanceledexception-class.md)|Bir işlem iptal edildiğinde oluşturulur.|
|[Platform::OutOfBoundsException Sınıfı](../cppcx/platform-outofboundsexception-class.md)|Bir işlem, geçerli aralığın dışında veri erişim girişiminde bulunduğunda oluşturulur.|
|[Platform::OutOfMemoryException Sınıfı](../cppcx/platform-outofmemoryexception-class.md)|İşlemi tamamlamak için bellek yetersiz olduğunda oluşturulur.|
|[Platform::STAThreadAttribute Sınıfı](../cppcx/platform-stathreadattribute-class.md)|Bir uygulama için iş parçacığı modeli tek iş parçacıklı grup (STA) olduğunu gösterir.|
|[Platform::String Sınıfı](../cppcx/platform-string-class.md)|Unicode karakter metin temsil etmek için kullanılan sıralı bir koleksiyonu.|
|[Platform::StringReference Sınıfı](../cppcx/platform-stringreference-class.md)|Kopya ek yükü en az dize arabelleklerinin erişim sağlar.|
|[Platform::Type Sınıfı](../cppcx/platform-type-class.md)|Yerleşik bir tür tarafından bir kategori sabit listesi tanımlar.|
|[Platform::ValueType Sınıfı](../cppcx/platform-valuetype-class.md)|Temel sınıf için değer türlerinin örnekleri.|
|[Platform::WeakReference Sınıfı](../cppcx/platform-weakreference-class.md)|Başvuru sayısını artırmaz zayıf bir başvuru ref sınıf nesnelerine sağlar.|
|[Platform::WriteOnlyArray Sınıfı](../cppcx/platform-writeonlyarray-class.md)|FillArray tasarımın yöntemlerde giriş parametresi olarak kullanılan bir tek boyutlu salt yazılır dizisini temsil eder.|
|[Platform::WrongThreadException Sınıfı](../cppcx/platform-wrongthreadexception-class.md)|Bir iş parçacığı için iş parçacığının grubunu ait olmayan bir proxy nesnesi için bir arabirim işaretçisi aracılığıyla çağırdığında oluşturulur.|

**Arabirim uygulamaları**

Platform ad alanı, aşağıdaki arabirimlerinden tanımlar.

|Arabirim|Açıklama|
|---------------|-----------------|
|[Platform::IBox Arabirimi](../cppcx/platform-ibox-interface.md)|Değer türleri parametreleri Platform::Object yazılan işlevlere geçirmek için kullanılan ^.|
|[Platform::IBoxArray Arabirimi](../cppcx/platform-iboxarray-interface.md)|İşlevler parametreleri Platform::Array yazılan diziler değer türlerinin geçirmek için kullanılan arabirim.|
|[Platform::IDisposable Arabirimi](../cppcx/platform-idisposable-interface.md)|Yönetilmeyen kaynakları serbest bırakmak için kullanılır.|

**Sabit Listeleri**

Aşağıdaki numaralandırmalar Platform ad alanı vardır.

|Arabirim|Açıklama|
|---------------|-----------------|
|[Platform::CallbackContext Numaralandırması](../cppcx/platform-callbackcontext-enumeration.md)|Bir temsilci Oluşturucu parametresi olarak kullanılan bir sabit listesi. Bu geri çağırma kaynak iş parçacığına veya çağıran iş parçacığına sıraya olup olmadığını belirler.|
|[Platform::TypeCode Numaralandırması](../cppcx/platform-typecode-enumeration.md)|Yerleşik türünü temsil eden sayısal bir kategorisini belirtir.|

**Yapılar**

Platform ad alanı, aşağıdaki yapılar vardır.

|Yapı|Açıklama|
|---------------|-----------------|
|[Platform::Enum Sınıfı](../cppcx/platform-enum-class.md)|Adlandırılmış bir sabiti temsil eder.|
|[Platform::Guid değer Sınıfı](../cppcx/platform-guid-value-class.md)|Bir GUID temsil eder.|
|[Platform::IntPtr değer Sınıfı](../cppcx/platform-intptr-value-class.md)|Boyutu (32 bit veya 64-bit) platform için uygun olan imzalı bir işaretçi.|
|[Platform::SizeT değer sınıfı](../cppcx/platform-sizet-value-class.md)|Bir nesnenin boyutunu temsil etmek için kullanılan bir imzasız veri türü.|
|[Platform::UIntPtr değer Sınıfı](../cppcx/platform-uintptr-value-class.md)|Boyutu (32 bit veya 64-bit) platform için uygun olan bir işaretsiz işaretçi.|

## <a name="see-also"></a>Ayrıca Bkz.

[Platform::Collections Ad Alanı](../cppcx/platform-collections-namespace.md)<br/>
[Platform::Runtime::CompilerServices Ad Alanı](../cppcx/platform-runtime-compilerservices-namespace.md)<br/>
[Platform::Runtime::InteropServices Ad Alanı](../cppcx/platform-runtime-interopservices-namespace.md)<br/>
[Platform::Metadata Ad Alanı](../cppcx/platform-metadata-namespace.md)