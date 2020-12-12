---
description: 'Daha fazla bilgi edinin: Platform ad alanı (C++/CX)'
title: Platform Ad Alanı (C++/CX)
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- Platform/Platform
helpviewer_keywords:
- Platform Namespace (C++/CX)
ms.assetid: b160e822-d424-43d2-ba60-57b0e81f259c
ms.openlocfilehash: 80f1b82ed39212812c8d316d4b7de09bf20ccad8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97308321"
---
# <a name="platform-namespace-ccx"></a>Platform Ad Alanı (C++/CX)

Windows Çalışma Zamanı uyumlu yerleşik türler içerir.

## <a name="syntax"></a>Syntax

```cpp
using namespace Platform;
```

### <a name="members"></a>Üyeler

**Öznitelikler**

Platform ad alanı öznitelikler, sınıflar, numaralandırmalar, arabirimler ve yapılar içerir. Platform iç içe geçmiş ad alanları da içerir.

|Öznitelik|Açıklama|
|---------------|-----------------|
|Bayraklar|Bir numaralandırmanın bir bit alanı olarak değerlendirileceğini belirtir; Yani, bir bayrak kümesi.|
|MTAThread|Bir uygulama için iş parçacığı modelinin çok iş parçacıklı apartman (MTA) olduğunu gösterir.|
|STAThread|Bir uygulamanın iş parçacığı modelinin tek iş parçacıklı Apartment (STA) olduğunu gösterir.|

**Sınıflar**

Platform ad alanı aşağıdaki sınıflara sahiptir.

|Sınıf|Açıklama|
|-----------|-----------------|
|[Platform:: AccessDeniedException Oluşturucusu sınıfı](../cppcx/platform-accessdeniedexception-class.md)|Bir kaynak veya özelliğe erişim reddedildiğinde tetiklenir.|
|[Platform:: çevik sınıfı](../cppcx/platform-agile-class.md)|Çevik olmayan bir nesneyi çevik bir nesne olarak temsil eder.|
|[Platform:: Array sınıfı](../cppcx/platform-array-class.md)|Tek boyutlu, değiştirilebilir bir diziyi temsil eder.|
|[Platform:: ArrayReference sınıfı](../cppcx/platform-arrayreference-class.md)|Kopyalama işlemlerini en aza indirmek için başlatma en iyi duruma getirilmiş bir diziyi temsil eder.|
|[Platform:: Box sınıfı](../cppcx/platform-box-class.md)|Windows:: Foundation gibi bir değer türünü kapsülleyen paketlenmiş bir tür bildirmek için kullanılır:D: Bu tür, uygulama ikili arabirimine (ABı) geçirildiğinde veya [Platform:: Object ^](../cppcx/platform-object-class.md)türünde bir değişkende depolanıyorsa.|
|[Platform:: ChangedStateException sınıfı](../cppcx/platform-changedstateexception-class.md)|Üst koleksiyon değiştirildikten sonra bir koleksiyon yineleyici veya koleksiyon görünümü metotları çağrıldığında, yöntemin sonuçları geçersiz kılınırken oluşturulur.|
|[Platform:: Classnotregisteredexception Oluşturucusu sınıfı](../cppcx/platform-classnotregisteredexception-class.md)|Bir COM sınıfı kaydedilmemişse oluşturulur.|
|[Platform:: COMException sınıfı](../cppcx/platform-comexception-class.md)|Bir COM yöntem çağrısından tanınmayan bir değer döndürüldüğünde oluşturulan özel durumu temsil eder.|
|[Platform::D elegate sınıfı](../cppcx/platform-delegate-class.md)|Geri çağırma işlevinin imzasını temsil eder.|
|[Platform::D isconnectedException sınıfı](../cppcx/platform-disconnectedexception-class.md)|Nesnenin istemcileriyle bağlantısı kesildi.|
|[Platform:: Exception sınıfı](../cppcx/platform-exception-class.md)|Uygulama yürütme sırasında oluşan hataları temsil eder. Özel durumlar için temel sınıf.|
|[Platform:: FailureException sınıfı](../cppcx/platform-failureexception-class.md)|İşlem başarısız olduğunda oluşturulur. HRESULT E_FAIL eşdeğerdir.|
|[Platform::Guid değer sınıfı](../cppcx/platform-guid-value-class.md)|Windows Çalışma Zamanı tür sistemindeki bir GUID 'YI temsil eder.|
|[Platform:: InvalidArgumentException Sınıfı](../cppcx/platform-invalidargumentexception-class.md)|Bir yönteme verilen bağımsız değişkenlerden biri geçerli değilse oluşturulur.|
|[Platform:: InvalidCastException sınıfı](../cppcx/platform-invalidcastexception-class.md)|Geçersiz atama ya da açık dönüştürme durumlarında oluşturulur.|
|[Platform:: MTAThreadAttribute sınıfı](../cppcx/platform-mtathreadattribute-class.md)|Bir uygulama için iş parçacığı modelinin çok iş parçacıklı apartman (MTA) olduğunu gösterir.|
|[Platform:: NotImplementedException sınıfı](../cppcx/platform-notimplementedexception-class.md)|Sınıf üzerinde bir arabirim yöntemi uygulanmadığından oluşturulur.|
|[Platform:: NullReferenceException sınıfı](../cppcx/platform-nullreferenceexception-class.md)|Null nesne başvurusunu başvuru girişimi olduğunda oluşturulur.|
|[Platform:: Object sınıfı](../cppcx/platform-object-class.md)|Ortak davranış sağlayan bir temel sınıf.|
|[Platform:: ObjectDisposedException sınıfı](../cppcx/platform-objectdisposedexception-class.md)|Atılmış bir nesne üzerinde bir işlem gerçekleştirildiğinde oluşturulur.|
|[Platform:: Operationolaydexception sınıfı](../cppcx/platform-operationcanceledexception-class.md)|Bir işlem iptal edildiğinde oluşturulur.|
|[Platform:: OutOfBoundsException sınıfı](../cppcx/platform-outofboundsexception-class.md)|Bir işlem geçerli Aralık dışında veriye erişmeye çalıştığında oluşturulur.|
|[Platform:: OutOfMemoryException sınıfı](../cppcx/platform-outofmemoryexception-class.md)|İşlemi gerçekleştirmek için yeterli bellek kalmadığında oluşturulur.|
|[Platform:: STAThreadAttribute sınıfı](../cppcx/platform-stathreadattribute-class.md)|Bir uygulamanın iş parçacığı modelinin tek iş parçacıklı Apartment (STA) olduğunu gösterir.|
|[Platform:: String sınıfı](../cppcx/platform-string-class.md)|Metni göstermek için kullanılan, ardışık bir Unicode karakter koleksiyonu.|
|[Platform:: StringReference sınıfı](../cppcx/platform-stringreference-class.md)|En az kopya yük yüküyle dize arabelleklerine erişim sağlar.|
|[Platform:: Type sınıfı](../cppcx/platform-type-class.md)|Bir kategori numaralandırması ile yerleşik bir türü tanımlar.|
|[Platform:: ValueType sınıfı](../cppcx/platform-valuetype-class.md)|Değer türlerinin örnekleri için temel sınıf.|
|[Platform:: WeakReference sınıfı](../cppcx/platform-weakreference-class.md)|Başvuru sayısını artmayan başvuru sınıfı nesnelerine zayıf bir başvuru sağlar.|
|[Platform:: WriteOnlyArray sınıfı](../cppcx/platform-writeonlyarray-class.md)|FillArray modelini uygulayan metotlarda giriş parametresi olarak kullanılan tek boyutlu bir salt yazılır diziyi temsil eder.|
|[Platform:: yanlışlıkla Gthreadexception sınıfı](../cppcx/platform-wrongthreadexception-class.md)|Bir iş parçacığı, iş parçacığının grubuna ait olmayan bir ara sunucu nesnesi için olan bir arabirim işaretçisi aracılığıyla çağırdığında oluşturulur.|

**Arabirim Uygulamaları**

Platform ad alanı aşağıdaki arabirimleri tanımlar.

|Arabirim|Açıklama|
|---------------|-----------------|
|[Platform:: Ibox arabirimi](../cppcx/platform-ibox-interface.md)|Parametreleri Platform:: Object ^ olarak yazılan işlevlere değer türlerini geçirmek için kullanılır.|
|[Platform:: ıboxarray arabirimi](../cppcx/platform-iboxarray-interface.md)|Parametreleri Platform:: Array olarak yazılan işlevlere değer türlerinin dizilerini geçirmek için kullanılan arabirim.|
|[Platform:: IDisposable arabirimi](../cppcx/platform-idisposable-interface.md)|Yönetilmeyen kaynakları serbest bırakmak için kullanılır.|

**Listelemeler**

Platform ad alanı aşağıdaki numaralandırmalara sahiptir.

|Arabirim|Açıklama|
|---------------|-----------------|
|[Platform::CallbackContext Numaralandırması](../cppcx/platform-callbackcontext-enumeration.md)|Temsilci oluşturucusunun parametresi olarak kullanılan bir sabit listesi. Geri aramanın, kaynak iş parçacığına veya çağıran iş parçacığına sıraya sokulıp edilmeyeceğini belirler.|
|[Platform::TypeCode Numaralandırması](../cppcx/platform-typecode-enumeration.md)|Yerleşik bir türü temsil eden sayısal bir kategori belirtir.|

**Yapılar**

Platform ad alanında aşağıdaki yapılar bulunur.

|Yapı|Açıklama|
|---------------|-----------------|
|[Platform:: enum sınıfı](../cppcx/platform-enum-class.md)|Adlandırılmış sabiti temsil eder.|
|[Platform::Guid değer sınıfı](../cppcx/platform-guid-value-class.md)|Bir GUID 'YI temsil eder.|
|[Platform::IntPtr değer sınıfı](../cppcx/platform-intptr-value-class.md)|Boyutu platform için uygun olan işaretli bir işaretçi (32 bit veya 64 bit).|
|[Platform::SizeT değer sınıfı](../cppcx/platform-sizet-value-class.md)|Bir nesnenin boyutunu temsil etmek için kullanılan işaretsiz veri türü.|
|[Platform::UIntPtr değer sınıfı](../cppcx/platform-uintptr-value-class.md)|Boyutu platform için uygun olan işaretsiz bir işaretçi (32 bit veya 64 bit).|

## <a name="see-also"></a>Ayrıca bkz.

[Platform:: Collections ad alanı](../cppcx/platform-collections-namespace.md)<br/>
[Platform:: Runtime:: CompilerServices Ad alanı](../cppcx/platform-runtime-compilerservices-namespace.md)<br/>
[Platform:: Runtime:: InteropServices ad alanı](../cppcx/platform-runtime-interopservices-namespace.md)<br/>
[Platform:: Metadata ad alanı](../cppcx/platform-metadata-namespace.md)
