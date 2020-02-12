---
title: accelerator Sınıfı
ms.date: 11/04/2016
f1_keywords:
- AMPRT/accelerator
- AMPRT/Concurrency::accelerator::accelerator
- AMPRT/Concurrency::accelerator::create_view
- AMPRT/Concurrency::accelerator::get_all
- AMPRT/Concurrency::accelerator::get_auto_selection_view
- AMPRT/Concurrency::accelerator::get_dedicated_memory
- AMPRT/Concurrency::accelerator::get_default_cpu_access_type
- AMPRT/Concurrency::accelerator::get_default_view
- AMPRT/Concurrency::accelerator::get_description
- AMPRT/Concurrency::accelerator::get_device_path
- AMPRT/Concurrency::accelerator::get_has_display
- AMPRT/Concurrency::accelerator::get_is_debug
- AMPRT/Concurrency::accelerator::get_is_emulated
- AMPRT/Concurrency::accelerator::get_supports_cpu_shared_memory
- AMPRT/Concurrency::accelerator::get_supports_double_precision
- AMPRT/Concurrency::accelerator::get_supports_limited_double_precision
- AMPRT/Concurrency::accelerator::get_version
- AMPRT/Concurrency::accelerator::set_default
- AMPRT/Concurrency::accelerator::set_default_cpu_access_type
- AMPRT/Concurrency::accelerator::cpu_accelerator
- AMPRT/Concurrency::accelerator::dedicated_memory
- AMPRT/Concurrency::accelerator::default_accelerator
- AMPRT/Concurrency::accelerator::default_cpu_access_type
- AMPRT/Concurrency::accelerator::default_view
- AMPRT/Concurrency::accelerator::description
- AMPRT/Concurrency::accelerator::device_path
- AMPRT/Concurrency::accelerator::direct3d_ref
- AMPRT/Concurrency::accelerator::direct3d_warp
- AMPRT/Concurrency::accelerator::has_display
- AMPRT/Concurrency::accelerator::is_debug
- AMPRT/Concurrency::accelerator::is_emulated
- AMPRT/Concurrency::accelerator::supports_cpu_shared_memory
- AMPRT/Concurrency::accelerator::supports_double_precision
- AMPRT/Concurrency::accelerator::supports_limited_double_precision
- AMPRT/Concurrency::accelerator::version
helpviewer_keywords:
- accelerator class
ms.assetid: 37eed593-cf87-4611-9cdc-e98df6c2377a
ms.openlocfilehash: 72a570ab28696730f835c42748a6ea12b865ca55
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127170"
---
# <a name="accelerator-class"></a>accelerator Sınıfı

Hızlandırıcı, veri paralel bilgi işlem için iyileştirilmiş bir donanım özelliğidir. Hızlandırıcı, bir PCIe veri yoluna (örneğin, GPU) bağlı bir cihaz veya ana CPU üzerinde genişletilmiş bir yönerge olabilir.

## <a name="syntax"></a>Sözdizimi

```cpp
class accelerator;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Hızlandırıcı Oluşturucusu](#ctor)|`accelerator` sınıfının yeni bir örneğini başlatır.|
|[~ Accelerator yıkıcısı](#ctor)|`accelerator` nesnesini yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[create_view](#create_view)|Bu hızlandırıcıda bir `accelerator_view` nesnesi oluşturur ve döndürür.|
|[get_all](#get_all)|Tüm kullanılabilir hızlandırıcıları temsil eden `accelerator` nesnelerinin bir vektörünü döndürür.|
|[get_auto_selection_view](#get_auto_selection_view)|Otomatik seçim `accelerator_view`döndürür.|
|[get_dedicated_memory](#get_dedicated_memory)|`accelerator`için ayrılmış belleği kilobayt cinsinden döndürür.|
|[get_default_cpu_access_type](#get_default_cpu_access_type)|Bu hızlandırıcıda oluşturulan arabellekler için varsayılan [access_type](concurrency-namespace-enums-amp.md#access_type) döndürür.|
|[get_default_view](#get_default_view)|`accelerator`ilişkili varsayılan `accelerator_view` nesnesini döndürür.|
|[get_description](#get_description)|`accelerator` cihazının kısa bir açıklamasını döndürür.|
|[get_device_path](#get_device_path)|Cihazın yolunu döndürür.|
|[get_has_display](#get_has_display)|`accelerator` bir görüntülemeye eklenip eklenmeyeceğini belirler.|
|[get_is_debug](#get_is_debug)|`accelerator`, kapsamlı hata raporlaması için hata ayıklama katmanının etkinleştirilip etkinleştirilmediğini belirler.|
|[get_is_emulated](#get_is_emulated)|`accelerator` benzetilen olup olmadığını belirler.|
|[get_supports_cpu_shared_memory](#get_supports_cpu_shared_memory)|`accelerator` paylaşılan belleği destekleyip desteklemediğini belirler|
|[get_supports_double_precision](#get_supports_double_precision)|`accelerator` bir görüntülemeye eklenip eklenmeyeceğini belirler.|
|[get_supports_limited_double_precision](#get_supports_limited_double_precision)|`accelerator` çift duyarlıklı matematik için sınırlı desteğe sahip olup olmadığını belirler.|
|[get_version](#get_version)|`accelerator`sürümünü döndürür.|
|[set_default](#set_default)|Varsayılan Hızlandırıcının yolunu döndürür.|
|[set_default_cpu_access_type](#set_default_cpu_access_type)|Bu `accelerator`yapılan diziler ve örtülü bellek ayırma için varsayılan CPU [access_type](concurrency-namespace-enums-amp.md#access_type)ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[operator!=](#operator_neq)|Bu `accelerator` nesnesini diğeri ile karşılaştırır ve aynı ise **false** değerini döndürür; Aksi takdirde, **true**döndürür.|
|[işleç =](#operator_eq)|Belirtilen `accelerator` nesnesinin içeriğini buna kopyalar.|
|[işleç = =](#operator_eq_eq)|Bu `accelerator` nesnesini diğeri ile karşılaştırır ve aynı olursa **true** değerini döndürür; Aksi takdirde, **false**döndürür.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[cpu_accelerator](#cpu_accelerator)|CPU `accelerator`için bir dize sabiti alır.|
|[dedicated_memory](#dedicated_memory)|`accelerator`için ayrılmış belleği kilobayt cinsinden alır.|
|[default_accelerator](#default_accelerator)|Varsayılan `accelerator`bir dize sabiti alır.|
|[default_cpu_access_type](#default_cpu_access_type)|Bu `accelerator`yapılan diziler ve örtülü bellek ayırma için varsayılan CPU [access_type](concurrency-namespace-enums-amp.md#access_type)alır veya ayarlar.|
|[default_view](#default_view)|`accelerator`ilişkili varsayılan `accelerator_view` nesnesini alır.|
|[açıklaması](#description)|`accelerator` cihazının kısa bir açıklamasını alır.|
|[device_path](#device_path)|Cihazın yolunu alır.|
|[direct3d_ref](#direct3d_ref)|Direct3D başvurusu `accelerator`için bir dize sabiti alır.|
|[direct3d_warp](#direct3d_warp)|Streaming SIMD Extensions (SSE) kullanan çok çekirdekli CPU 'Larda amp kodu yürütmek C++ için kullanabileceğiniz bir `accelerator` nesnesi için dize sabiti alır.|
|[has_display](#has_display)|`accelerator` bir görüntülemeye iliştirilip bağlanmadığını belirten bir Boole değeri alır.|
|[is_debug](#is_debug)|`accelerator`, kapsamlı hata raporlaması için hata ayıklama katmanının etkinleştirilip etkinleştirilmediğini gösterir.|
|[is_emulated](#is_emulated)|`accelerator` öykünmesinin yapılıp yapılmayacağını belirtir.|
|[supports_cpu_shared_memory](#supports_cpu_shared_memory)|`accelerator` paylaşılan belleği destekleyip desteklemediğini gösterir.|
|[supports_double_precision](#supports_double_precision)|Hızlandırıcının çift duyarlıklı matematik desteği olup olmadığını gösterir.|
|[supports_limited_double_precision](#supports_limited_double_precision)|Hızlandırıcının çift duyarlıklı matematik için sınırlı desteğe sahip olup olmadığını gösterir.|
|[version](#version)|`accelerator`sürümünü alır.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`accelerator`

## <a name="remarks"></a>Açıklamalar

Hızlandırıcı, veri paralel bilgi işlem için iyileştirilmiş bir donanım özelliğidir. Hızlandırıcı genellikle ayrı bir GPU olur, ancak aynı zamanda DirectX başvuru cihazı, bir ÇARPıTMA (SSE yönergeleri aracılığıyla hızlandırılır) veya CPU 'nun kendisi gibi bir sanal ana bilgisayar tarafı varlığı da olabilir.

Kullanılabilir cihazları numaralandırarak veya varsayılan cihazı, başvuru cihazını veya WARP cihazını alarak bir `accelerator` nesnesi oluşturabilirsiniz.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** amprt. h

**Ad alanı:** Zamanlı

## <a name="dtor"></a></a> ~ Hızlandırıcı

`accelerator` nesnesini yok eder.

```cpp
~accelerator();
```

### <a name="return-value"></a>Dönüş Değeri

## <a name="ctor"></a>hızlandır

[Hızlandırıcı sınıfının](accelerator-class.md)yeni bir örneğini başlatır.

```cpp
accelerator();

explicit accelerator(const std::wstring& _Device_path);

accelerator(const accelerator& _Other);
```

### <a name="parameters"></a>Parametreler

*_Device_path*<br/>
Fiziksel cihazın yolu.

*_Other*<br/>
Kopyalanacak hızlandırıcı.

## <a name="cpu_accelerator"></a>cpu_accelerator

CPU Hızlandırıcısı için bir dize sabiti alır.

```cpp
static const wchar_t cpu_accelerator[];
```

## <a name="create_view"></a>create_view

Belirtilen sıraya alma modunu kullanarak bu hızlandırıcıda bir `accelerator_view` nesnesi oluşturur ve döndürür. Sıraya alma modu belirtilmediğinde, yeni `accelerator_view` [queuing_mode:: ımı](concurrency-namespace-enums-amp.md#queuing_mode) sıraya alma modunu kullanır.

```cpp
accelerator_view create_view(queuing_mode qmode = queuing_mode_automatic);
```

### <a name="parameters"></a>Parametreler

*qmode*<br/>
Sıraya alma modu.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen sıraya alma modunu kullanarak bu hızlandırıcıda yeni bir `accelerator_view` nesnesi.

## <a name="dedicated_memory"></a>dedicated_memory

`accelerator`için ayrılmış belleği kilobayt cinsinden alır.

```cpp
__declspec(property(get= get_dedicated_memory)) size_t dedicated_memory;
```

## <a name="default_accelerator"></a>default_accelerator

Varsayılan `accelerator`bir dize sabiti alır.

```cpp
static const wchar_t default_accelerator[];
```

## <a name="default_cpu_access_type"></a>default_cpu_access_type

Bu `accelerator`yapılan diziler ve örtülü bellek ayırma için varsayılan CPU [access_type](concurrency-namespace-enums-amp.md#access_type).

```cpp
__declspec(property(get= get_default_cpu_access_type)) access_type default_cpu_access_type;
```

## <a name="default_view"></a>default_view

`accelerator`ilişkili varsayılan Hızlandırıcı görünümünü alır.

```cpp
__declspec(property(get= get_default_view)) accelerator_view default_view;
```

## <a name="description"></a>açıklaması

`accelerator` cihazının kısa bir açıklamasını alır.

```cpp
__declspec(property(get= get_description)) std::wstring description;
```

## <a name="device_path"></a>device_path

Hızlandırıcının yolunu alır. Yol, sistemde benzersizdir.

```cpp
__declspec(property(get= get_device_path)) std::wstring device_path;
```

## <a name="direct3d_ref"></a>direct3d_ref

Direct3D başvuru Hızlandırıcısı için bir dize sabiti alır.

```cpp
static const wchar_t direct3d_ref[];
```

## <a name="direct3d_warp"></a>direct3d_warp

Streaming SIMD Extensions (SSE) kullanan çok çekirdekli CPU 'Larda C++ amp kodunuzu yürütmek için kullanabileceğiniz bir `accelerator` nesnesi için dize sabiti alır.

```cpp
static const wchar_t direct3d_warp[];
```

## <a name="get_all"></a>get_all

Tüm kullanılabilir hızlandırıcıları temsil eden `accelerator` nesnelerinin bir vektörünü döndürür.

```cpp
static inline std::vector<accelerator> get_all();
```

### <a name="return-value"></a>Dönüş Değeri

Kullanılabilir Hızlandırıcılar 'ın vektörü

## <a name="get_auto_selection_view"></a>get_auto_selection_view

Parallel_for_each hedef olarak belirtildiğinde, parallel_for_each çekirdeğini çalışma zamanı tarafından otomatik olarak seçilecek şekilde yürütmek için hedef accelerator_view accelerator_view otomatik seçimi döndürür. Diğer tüm amaçlar için, bu yöntemin döndürdüğü accelerator_view varsayılan hızlandırıcının varsayılan accelerator_view aynıdır

```cpp
static accelerator_view __cdecl get_auto_selection_view();
```

### <a name="return-value"></a>Dönüş Değeri

Otomatik seçim accelerator_view.

## <a name="get_dedicated_memory"></a>get_dedicated_memory

`accelerator`için ayrılmış belleği kilobayt cinsinden döndürür.

```cpp
size_t get_dedicated_memory() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kilobayt cinsinden `accelerator`için ayrılmış bellek.

## <a name="get_default_cpu_access_type"></a>get_default_cpu_access_type

Bu hızlandırıcıda oluşturulan arabellekler için varsayılan CPU access_type alır

```cpp
access_type get_default_cpu_access_type() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu hızlandırıcıda oluşturulan arabellekler için varsayılan CPU access_type.

## <a name="get_default_view"></a>get_default_view

`accelerator`ilişkili varsayılan `accelerator_view` nesnesini döndürür.

```cpp
accelerator_view get_default_view() const;
```

### <a name="return-value"></a>Dönüş Değeri

`accelerator`ilişkili varsayılan `accelerator_view` nesnesi.

## <a name="get_description"></a>get_description

`accelerator` cihazının kısa bir açıklamasını döndürür.

```cpp
std::wstring get_description() const;
```

### <a name="return-value"></a>Dönüş Değeri

`accelerator` cihazının kısa bir açıklaması.

## <a name="get_device_path"></a>get_device_path

Hızlandırıcının yolunu döndürür. Yol, sistemde benzersizdir.

```cpp
std::wstring get_device_path() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sistem genelindeki benzersiz cihaz örneği yolu.

## <a name="get_has_display"></a>get_has_display

`accelerator` bir ekranda bir ekran için çıkış yapıp kullanamayacağını belirten bir Boole değeri döndürür.

```cpp
bool get_has_display() const;
```

### <a name="return-value"></a>Dönüş Değeri

`accelerator` bir görüntü için çıktıbiliyorsa, **true** , Aksi takdirde, **false**.

## <a name="get_is_debug"></a>get_is_debug

`accelerator`, kapsamlı hata raporlaması için hata ayıklama katmanının etkinleştirilip etkinleştirilmediğini belirler.

```cpp
bool get_is_debug() const;
```

### <a name="return-value"></a>Dönüş Değeri

`accelerator`, yoğun hata raporlama için etkin hata ayıklama katmanını içeriyorsa **true** . Aksi takdirde, **false**.

## <a name="get_is_emulated"></a>get_is_emulated

`accelerator` benzetilen olup olmadığını belirler.

```cpp
bool get_is_emulated() const;
```

### <a name="return-value"></a>Dönüş Değeri

`accelerator` öykündüğü **true** . Aksi takdirde, **false**.

## <a name="get_supports_cpu_shared_memory"></a>get_supports_cpu_shared_memory

Hızlandırıcının hem Hızlandırıcı hem de CPU tarafından erişilebilen belleği destekleyip desteklemediğini gösteren bir Boole değeri döndürür.

```cpp
bool get_supports_cpu_shared_memory() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hızlandırıcı, CPU paylaşılan belleğini destekliyorsa, **doğru** . Aksi takdirde, **false**.

## <a name="get_supports_double_precision"></a>get_supports_double_precision

Hızlandırıcının, fkullanılan çarpma ekleme (FMA), bölme, geri çevirme ve **int** ile **Double** arasında atama dahil olmak üzere çift duyarlıklı matematik desteği destekleyip desteklemediğini gösteren bir Boole değeri döndürür

```cpp
bool get_supports_double_precision() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hızlandırıcı çift duyarlıklı matematik 'yı destekliyorsa, **doğru** ; Aksi takdirde, **false**.

## <a name="get_supports_limited_double_precision"></a>get_supports_limited_double_precision

Hızlandırıcının çift duyarlıklı matematik için sınırlı desteğe sahip olup olmadığını gösteren bir Boole değeri döndürür. Hızlandırıcının yalnızca sınırlı desteği varsa, fımtı Add (FMA), bölme, **karşılıklı ve atama** ile **Double** arasında çarpma desteklenmez.

```cpp
bool get_supports_limited_double_precision() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hızlandırıcının çift duyarlıklı matematik için sınırlı desteği varsa **doğru** ; Aksi takdirde, **false**.

## <a name="get_version"></a>get_version

`accelerator`sürümünü döndürür.

```cpp
unsigned int get_version() const;
```

### <a name="return-value"></a>Dönüş Değeri

`accelerator`sürümü.

## <a name="has_display"></a>has_display

`accelerator` bir ekranda bir ekran için çıkış yapıp kullanamayacağını belirten bir Boole değeri alır.

```cpp
__declspec(property(get= get_has_display)) bool has_display;
```

## <a name="is_debug"></a>is_debug

`accelerator`, yoğun hata raporlama için hata ayıklama katmanının etkinleştirilip etkinleştirilmediğini belirten bir Boole değeri alır.

```cpp
__declspec(property(get= get_is_debug)) bool is_debug;
```

## <a name="is_emulated"></a>is_emulated

`accelerator` öykünmesinin yapılıp yapılmayacağını belirten bir Boole değeri alır.

```cpp
__declspec(property(get= get_is_emulated)) bool is_emulated;
```

## <a name="operator_neq"></a>işleç! =

Bu `accelerator` nesnesini diğeri ile karşılaştırır ve aynı ise **false** değerini döndürür; Aksi takdirde, **true**döndürür.

```cpp
bool operator!= (const accelerator& _Other) const;
```

### <a name="parameters"></a>Parametreler

*_Other*<br/>
`accelerator` nesne bununla Karşılaştırılacak.

### <a name="return-value"></a>Dönüş Değeri

iki `accelerator` nesnesi aynıysa **false** ; Aksi takdirde, **doğru**.

## <a name="operator_eq"></a>işleç =

Belirtilen `accelerator` nesnesinin içeriğini buna kopyalar.

```cpp
accelerator& operator= (const accelerator& _Other);
```

### <a name="parameters"></a>Parametreler

*_Other*<br/>
Kopyalamanın `accelerator` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Bu `accelerator` nesnesine bir başvuru.

## <a name="operator_eq_eq"></a>işleç = =

Bu `accelerator` nesnesini diğeri ile karşılaştırır ve aynı olursa **true** değerini döndürür; Aksi takdirde, **false**döndürür.

```cpp
bool operator== (const accelerator& _Other) const;
```

### <a name="parameters"></a>Parametreler

*_Other*<br/>
`accelerator` nesne bununla Karşılaştırılacak.

### <a name="return-value"></a>Dönüş Değeri

diğer `accelerator` nesnesi bu `accelerator` nesneyle aynıysa **doğru** ; Aksi takdirde, **false**.

## <a name="set_default"></a>set_default

Varsayılan hızlandırıcıyı örtülü olarak kullanan herhangi bir işlem için kullanılacak varsayılan hızlandırıcıyı ayarlar. Bu yöntem yalnızca çalışma zamanı seçili varsayılan Hızlandırıcı, Varsayılan hızlandırıcıyı örtülü olarak kullanan bir işlemde henüz kullanılmıyorsa başarılı olur

```cpp
static inline bool set_default(std::wstring _Path);
```

### <a name="parameters"></a>Parametreler

*_Path*<br/>
Hızlandırıcının yolu.

### <a name="return-value"></a>Dönüş Değeri

Varsayılan hızlandırıcı ayarı sırasında çağrı başarılı olursa **true** . Aksi takdirde, **false**.

## <a name="set_default_cpu_access_type"></a>set_default_cpu_access_type

Bu hızlandırıcıda veya bu hızlandırıcıda erişilen array_views bir parçası olarak örtük bellek ayırmaları için oluşturulan diziler için varsayılan CPU access_type ayarlayın. Bu yöntem yalnızca hızlandırıcının default_cpu_access_type önceki bir çağrı tarafından zaten geçersiz kılınmamışsa ve bu hızlandırıcının Bu Hızlandırıcı için default_cpu_access_type seçili olan çalışma zamanının bir diziyi ayırmak için henüz kullanılmadığından başarılı olur. Bu hızlandırıcıda erişilen bir array_view yedekleyen örtülü bellek ayırma.

```cpp
bool set_default_cpu_access_type(access_type _Default_cpu_access_type);
```

### <a name="parameters"></a>Parametreler

*_Default_cpu_access_type*<br/>
Bu Hızlandırıcı 'daki dizi/array_view bellek ayırmaları için kullanılacak varsayılan CPU access_type.

### <a name="return-value"></a>Dönüş Değeri

Hızlandırıcının varsayılan CPU access_type başarıyla ayarlandığını belirten bir Boole değeri.

## <a name="supports_cpu_shared_memory"></a>supports_cpu_shared_memory

`accelerator` paylaşılan belleği destekleyip desteklemediğini gösteren bir Boole değeri alır.

```cpp
__declspec(property(get= get_supports_cpu_shared_memory)) bool supports_cpu_shared_memory;
```

## <a name="supports_double_precision"></a>supports_double_precision

Hızlandırıcının çift duyarlıklı matematik desteği destekleyip desteklemediğini gösteren bir Boole değeri alır.

```cpp
__declspec(property(get= get_supports_double_precision)) bool supports_double_precision;
```

## <a name="supports_limited_double_precision"></a>supports_limited_double_precision

Hızlandırıcının çift duyarlıklı matematik için sınırlı desteğe sahip olup olmadığını gösteren bir Boole değeri alır. Hızlandırıcının yalnızca sınırlı desteği varsa, fımtı Add (FMA), bölme, karşılıklı ve `int` ile `double` arasında atama desteklenmez.

```cpp
__declspec(property(get= get_supports_limited_double_precision)) bool supports_limited_double_precision;
```

## <a name="version"></a>Sürüm

`accelerator`sürümünü alır.

```cpp
__declspec(property(get= get_version)) unsigned int version;
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
