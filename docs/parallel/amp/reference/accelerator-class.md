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
ms.openlocfilehash: 2045d2d1c6a848378ac55114b61177d386b14fab
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51523929"
---
# <a name="accelerator-class"></a>accelerator Sınıfı

Hızlandırıcı veri paralel hesaplamaları için optimize edilmiş bir donanımdır. Bir Hızlandırıcı PCIe veri yoluna (örneğin GPU) bağlı bir cihaz olabilir veya ana CPU üzerinde ayarlanmış, genişletilmiş bir yönerge olabilir.

## <a name="syntax"></a>Sözdizimi

```
class accelerator;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Hızlandırıcı Oluşturucusu](#ctor)|Yeni bir örneğini başlatır `accelerator` sınıfı.|
|[~ accelerator yok Edicisi](#ctor)|Yok eder `accelerator` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[create_view](#create_view)|Oluşturur ve döndürür bir `accelerator_view` bu Hızlandırıcı üzerinde nesne.|
|[get_all](#get_all)|Bir vektör döndürür `accelerator` tüm kullanılabilir Hızlandırıcıları temsil eden nesneleri.|
|[get_auto_selection_view](#get_auto_selection_view)|Otomatik Seçim döndürür `accelerator_view`.|
|[get_dedicated_memory](#get_dedicated_memory)|Ayrılmış belleği döndürür `accelerator`, kilobayt cinsinden.|
|[get_default_cpu_access_type](#get_default_cpu_access_type)|Varsayılan döndürür [access_type](concurrency-namespace-enums-amp.md#access_type) bu hızlandırıcıda oluşturulan arabellekler için.|
|[get_default_view](#get_default_view)|Varsayılan döndürür `accelerator_view` ile ilişkili nesne `accelerator`.|
|[get_description](#get_description)|Kısa bir açıklamasını döndürür `accelerator` cihaz.|
|[get_device_path](#get_device_path)|Cihazın yolunu döndürür.|
|[get_has_display](#get_has_display)|Belirler olmadığını `accelerator` bir görüntüye bağlı.|
|[get_is_debug](#get_is_debug)|Belirler olmadığını `accelerator` ayrıntılı hata raporlama için etkinleştirilen DEBUG katmanına sahip.|
|[get_is_emulated](#get_is_emulated)|Belirler olmadığını `accelerator` benzetilip benzetilmediğini.|
|[get_supports_cpu_shared_memory](#get_supports_cpu_shared_memory)|Belirler olmadığını `accelerator` paylaşılan belleği destekleyip|
|[get_supports_double_precision](#get_supports_double_precision)|Belirler olmadığını `accelerator` bir görüntüye bağlı.|
|[get_supports_limited_double_precision](#get_supports_limited_double_precision)|Belirler olmadığını `accelerator` çifte duyarlı Matematiği için sınırlı desteğe sahip.|
|[get_version](#get_version)|Sürümünü döndürür `accelerator`.|
|[set_default](#set_default)|Varsayılan hızlandırıcının yolunu döndürür.|
|[set_default_cpu_access_type](#set_default_cpu_access_type)|Ayarlar için varsayılan CPU [access_type](concurrency-namespace-enums-amp.md#access_type)diziler ve bunun üzerinde yapılan örtülü bellek ayırmaları `accelerator`.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[operator!=](#operator_neq)|Bu karşılaştırır `accelerator` döndürür ve başka nesnesi **false** aynı; olmaları durumunda döndürür, aksi takdirde, **true**.|
|[operator=](#operator_eq)|Belirtilen içeriğini kopyalar `accelerator` buna nesne.|
|[operator==](#operator_eq_eq)|Bu karşılaştırır `accelerator` döndürür ve başka nesnesi **true** aynı; olmaları durumunda döndürür, aksi takdirde, **false**.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[cpu_accelerator](#cpu_accelerator)|CPU için bir dize sabiti alır `accelerator`.|
|[dedicated_memory](#dedicated_memory)|Ayrılmış belleği alır `accelerator`, kilobayt cinsinden.|
|[default_accelerator](#default_accelerator)|İçin varsayılan bir dize sabiti alır `accelerator`.|
|[default_cpu_access_type](#default_cpu_access_type)|Alır veya ayarlar için varsayılan CPU [access_type](concurrency-namespace-enums-amp.md#access_type)diziler ve bunun üzerinde yapılan örtülü bellek ayırmaları `accelerator`.|
|[default_view](#default_view)|Varsayılan alır `accelerator_view` ile ilişkili nesne `accelerator`.|
|[Açıklaması](#description)|Kısa bir açıklamasını alır `accelerator` cihaz.|
|[device_path](#device_path)|Cihazın yolunu alır.|
|[direct3d_ref](#direct3d_ref)|Bir Direct3D başvurusu için bir dize sabiti alır `accelerator`.|
|[direct3d_warp](#direct3d_warp)|İçin dizeyi sabit alır bir `accelerator` , Streaming SIMD uzantılarını (SSE) kullanan çok çekirdekli CPU üzerinde C++ AMP kodunu yürütmek için kullanabileceğiniz nesne.|
|[has_display](#has_display)|Gösteren bir Boole değeri alır olmadığını `accelerator` bir görüntüye bağlı.|
|[is_debug](#is_debug)|Belirtir olup olmadığını `accelerator` ayrıntılı hata raporlama için etkinleştirilen DEBUG katmanına sahip.|
|[is_emulated](#is_emulated)|Belirtir olup olmadığını `accelerator` benzetilip benzetilmediğini.|
|[supports_cpu_shared_memory](#supports_cpu_shared_memory)|Belirtir olup olmadığını `accelerator` paylaşılan belleği destekleyip.|
|[supports_double_precision](#supports_double_precision)|Hızlandırıcının çifte duyarlı Matematiği destekleyip desteklemediğini gösterir.|
|[supports_limited_double_precision](#supports_limited_double_precision)|Hızlandırıcının çifte duyarlı Matematiği için sınırlı desteğe sahip olup olmadığını gösterir.|
|[version](#version)|Sürümünü alır `accelerator`.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`accelerator`

## <a name="remarks"></a>Açıklamalar

Hızlandırıcı veri paralel hesaplamaları için optimize edilmiş bir donanımdır. Hızlandırıcı genellikle ayrı ancak DirectX REF cihazı, bir WARP (SSE yönergeleri ile hızlandırılmış bir CPU tarafı cihazı) veya CPU'nun kendisi gibi bir sanal konak tarafı varlığı olabilir.

Oluşturulabilir bir `accelerator` kullanılabilir cihazları listeleniyor tarafından veya varsayılan cihazı, başvuru cihazını veya WARP cihazını alarak bir nesne.

## <a name="requirements"></a>Gereksinimler

**Başlık:** amprt.h

**Namespace:** eşzamanlılık

##  <a name="dtor"></a> </a> ~ accelerator

Yok eder `accelerator` nesne.

```
~accelerator();
```

### <a name="return-value"></a>Dönüş Değeri

##  <a name="ctor"></a> Hızlandırıcı

Yeni bir örneğini başlatır [Hızlandırıcı sınıfı](accelerator-class.md).

```
accelerator();

explicit accelerator(const std::wstring& _Device_path);

accelerator(const accelerator& _Other);
```

### <a name="parameters"></a>Parametreler

*_Device_path*<br/>
Fiziksel cihazın yolu.

*_Diğer*<br/>
Kopyalamak için Hızlandırıcı.

##  <a name="cpu_accelerator"></a> cpu_accelerator

Bir dize için CPU Hızlandırıcı sabiti alır.

```
static const wchar_t cpu_accelerator[];
```

##  <a name="create_view"></a> create_view

Oluşturur ve döndürür bir `accelerator_view` belirtilen bir sıralama modu kullanarak bu hızlandırıcıda nesne. Sıralama modu değil belirtildiği zaman, yeni `accelerator_view` kullanan [queuing_mode::immediate](concurrency-namespace-enums-amp.md#queuing_mode) sıralama modu.

```
accelerator_view create_view(queuing_mode qmode = queuing_mode_automatic);
```

### <a name="parameters"></a>Parametreler

*qmode*<br/>
Sıralama modu.

### <a name="return-value"></a>Dönüş Değeri

Yeni bir `accelerator_view` belirtilen bir sıralama modu kullanarak bu hızlandırıcıda nesne.

##  <a name="dedicated_memory"></a> dedicated_memory

Ayrılmış belleği alır `accelerator`, kilobayt cinsinden.

```
__declspec(property(get= get_dedicated_memory)) size_t dedicated_memory;
```

##  <a name="default_accelerator"></a> default_accelerator

İçin varsayılan bir dize sabiti alır `accelerator`.

```
static const wchar_t default_accelerator[];
```

##  <a name="default_cpu_access_type"></a> default_cpu_access_type

Varsayılan cpu [access_type](concurrency-namespace-enums-amp.md#access_type)diziler ve bunun üzerinde yapılan örtülü bellek ayırmaları `accelerator`.

```
__declspec(property(get= get_default_cpu_access_type)) access_type default_cpu_access_type;
```

##  <a name="default_view"></a> default_view

İle ilişkili varsayılan Hızlandırıcı görünümü alır `accelerator`.

```
__declspec(property(get= get_default_view)) accelerator_view default_view;
```

##  <a name="description"></a> Açıklaması

Kısa bir açıklamasını alır `accelerator` cihaz.

```
__declspec(property(get= get_description)) std::wstring description;
```

##  <a name="device_path"></a> device_path

Hızlandırıcının yolunu alır. Sistemde benzersiz yoludur.

```
__declspec(property(get= get_device_path)) std::wstring device_path;
```

##  <a name="direct3d_ref"></a> direct3d_ref

Bir dize için bir Direct3D başvurusu Hızlandırıcı sabiti alır.

```
static const wchar_t direct3d_ref[];
```

##  <a name="direct3d_warp"></a> direct3d_warp

İçin dizeyi sabit alır bir `accelerator` , Streaming SIMD uzantılarını (SSE) kullanan çok çekirdekli CPU üzerinde C++ AMP kodunuzu yürütmek için kullanabileceğiniz nesne.

```
static const wchar_t direct3d_warp[];
```

##  <a name="get_all"></a> get_all

Bir vektör döndürür `accelerator` tüm kullanılabilir Hızlandırıcıları temsil eden nesneleri.

```
static inline std::vector<accelerator> get_all();
```

### <a name="return-value"></a>Dönüş Değeri

Kullanılabilir Hızlandırıcıları vektörü

##  <a name="get_auto_selection_view"></a> get_auto_selection_view

Otomatik Seçim accelerator_view döndürür olan çalışma zamanı tarafından otomatik olarak seçilecek şekilde parallel_for_each çekirdeğini yürütmek için hedef accelerator_view sonuçlarda parallel_for_each hedef olarak belirtilir. Diğer tüm amaçlar için bu yöntemle döndürülen accelerator_view varsayılan hızlandırıcının varsayılan accelerator_view aynıdır

```
static accelerator_view __cdecl get_auto_selection_view();
```

### <a name="return-value"></a>Dönüş Değeri

Otomatik Seçim accelerator_view.

##  <a name="get_dedicated_memory"></a> get_dedicated_memory

Ayrılmış belleği döndürür `accelerator`, kilobayt cinsinden.

```
size_t get_dedicated_memory() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılmış belleği `accelerator`, kilobayt cinsinden.

##  <a name="get_default_cpu_access_type"></a> get_default_cpu_access_type

Bu hızlandırıcıda oluşturulan arabellekler için varsayılan cpu access_type alır.

```
access_type get_default_cpu_access_type() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu hızlandırıcıda oluşturulan arabellekler için varsayılan cpu access_type.

##  <a name="get_default_view"></a> get_default_view

Varsayılan döndürür `accelerator_view` ile ilişkili nesne `accelerator`.

```
accelerator_view get_default_view() const;
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan `accelerator_view` ile ilişkili nesne `accelerator`.

##  <a name="get_description"></a> get_description

Kısa bir açıklamasını döndürür `accelerator` cihaz.

```
std::wstring get_description() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kısa bir açıklamasını `accelerator` cihaz.

##  <a name="get_device_path"></a> get_device_path

Hızlandırıcının yolunu döndürür. Sistemde benzersiz yoludur.

```
std::wstring get_device_path() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sistem genelinde benzersiz cihaz örnek yolu.

##  <a name="get_has_display"></a> get_has_display

Belirten bir Boole değeri döndürür olmadığını `accelerator` bir görüntü cihazına çıktısı alınabilen.

```
bool get_has_display() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa `accelerator` ; bir görüntü cihazına çıktısı alınabilen Aksi takdirde, **false**.

##  <a name="get_is_debug"></a> get_is_debug

Belirler olmadığını `accelerator` ayrıntılı hata raporlama için etkinleştirilen DEBUG katmanına sahip.

```
bool get_is_debug() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa `accelerator` ayrıntılı hata raporlama için etkinleştirilen DEBUG katmanına sahip. Aksi takdirde, **false**.

##  <a name="get_is_emulated"></a> get_is_emulated

Belirler olmadığını `accelerator` benzetilip benzetilmediğini.

```
bool get_is_emulated() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa `accelerator` benzetilip benzetilmediğini. Aksi takdirde, **false**.

##  <a name="get_supports_cpu_shared_memory"></a> get_supports_cpu_shared_memory

Hızlandırıcının, hem Hızlandırıcı ve CPU tarafından erişilebilir belleği destekleyip desteklemediğini gösteren bir Boole değeri döndürür.

```
bool get_supports_cpu_shared_memory() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** CPU Hızlandırıcı destekler paylaşılan bellek; Aksi takdirde, **false**.

##  <a name="get_supports_double_precision"></a> get_supports_double_precision

Hızlandırıcının çifte hassas matematik destekleyip dahil olmak üzere birleşik çarpma toplama belirten Boolean bir değer döner ekleyin (FMA), bölme, karşıtlık ve arasındaki tür **int** ve **çift**

```
bool get_supports_double_precision() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** Hızlandırıcı çift duyarlık Matematiği destekliyorsa, aksi takdirde, **false**.

##  <a name="get_supports_limited_double_precision"></a> get_supports_limited_double_precision

Hızlandırıcı çift duyarlık Matematiği için sınırlı desteğe sahip olup olmadığını gösteren bir Boole değeri döndürür. Hızlandırıcı ekleyin (FMA) birden çok kez çarpım yalnızca sınırlı destek varsa, bölme, karşıtlık ve arasındaki tür **int** ve **çift** desteklenmez.

```
bool get_supports_limited_double_precision() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** Hızlandırıcı çift duyarlık Matematiği desteği sınırlıdır, aksi takdirde, **false**.

##  <a name="get_version"></a> get_version

Sürümünü döndürür `accelerator`.

```
unsigned int get_version() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sürümü `accelerator`.

##  <a name="has_display"></a> has_display

Gösteren bir Boole değeri alır olmadığını `accelerator` bir görüntü cihazına çıktısı alınabilen.

```
__declspec(property(get= get_has_display)) bool has_display;
```

##  <a name="is_debug"></a> is_debug

Gösteren bir Boole değeri alır olmadığını `accelerator` ayrıntılı hata raporlama için etkinleştirilen DEBUG katmanına sahip.

```
__declspec(property(get= get_is_debug)) bool is_debug;
```

##  <a name="is_emulated"></a> is_emulated

Gösteren bir Boole değeri alır olmadığını `accelerator` benzetilip benzetilmediğini.

```
__declspec(property(get= get_is_emulated)) bool is_emulated;
```

##  <a name="operator_neq"></a> işleç! =

Bu karşılaştırır `accelerator` döndürür ve başka nesnesi **false** aynı; olmaları durumunda döndürür, aksi takdirde, **true**.

```
bool operator!= (const accelerator& _Other) const;
```

### <a name="parameters"></a>Parametreler

*_Diğer*<br/>
`accelerator` İle Karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

**false** varsa iki `accelerator` nesneleri aynıdır; Aksi takdirde **true**.

##  <a name="operator_eq"></a> işleç =

Belirtilen içeriğini kopyalar `accelerator` buna nesne.

```
accelerator& operator= (const accelerator& _Other);
```

### <a name="parameters"></a>Parametreler

*_Diğer*<br/>
`accelerator` Kopyalanacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Bu başvuru `accelerator` nesne.

##  <a name="operator_eq_eq"></a> işleç ==

Bu karşılaştırır `accelerator` döndürür ve başka nesnesi **true** aynı; olmaları durumunda döndürür, aksi takdirde, **false**.

```
bool operator== (const accelerator& _Other) const;
```

### <a name="parameters"></a>Parametreler

*_Diğer*<br/>
`accelerator` İle Karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa diğer `accelerator` nesne olarak aynı `accelerator` nesne; Aksi takdirde, **false**.

##  <a name="set_default"></a> set_default

Örtülü olarak varsayılan hızlandırıcıyı kullanan herhangi bir işlem için kullanılacak varsayılan hızlandırıcıyı ayarlar. Çalışma Zamanı seçili varsayılan hızlandırıcıyı örtülü olarak varsayılan hızlandırıcıyı kullanan bir işlem içinde zaten kullanılmamış, bu yöntem yalnızca başarılı

```
static inline bool set_default(std::wstring _Path);
```

### <a name="parameters"></a>Parametreler

*_Yolu*<br/>
Hızlandırıcının yolu.

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsayılan kısayol tuşu ayarlanırken çağrı başarılı olursa. Aksi takdirde, **false**.

##  <a name="set_default_cpu_access_type"></a> set_default_cpu_access_type

Bu Hızlandırıcı üzerinde oluşturulan dizileri için veya örtülü bellek ayırmaları için varsayılan cpu access_type bu hızlandırıcıda erişilen array_views'ın bir parçası olarak ayarlayın. Bu yöntem yalnızca Hızlandırıcı için default_cpu_access_type bu yönteme bir çağrı tarafından geçersiz kılınmış zaten değil ve veya bir dizi ayırma için çalışma zamanında seçilen default_cpu_access_type bu Hızlandırıcı için henüz kullanılmamış başarılı Bu hızlandırıcıda erişilen bir array_view öğesini destekleyen bir örtülü bellek ayırma.

```
bool set_default_cpu_access_type(access_type _Default_cpu_access_type);
```

### <a name="parameters"></a>Parametreler

*_Default_cpu_access_type*<br/>
Bu hızlandırıcıda array/array_view bellek ayırmaları için kullanılacak varsayılan cpu access_type.

### <a name="return-value"></a>Dönüş Değeri

Hızlandırıcı için varsayılan cpu access_type başarıyla ayarlandı gösteren bir Boole değeri.

##  <a name="supports_cpu_shared_memory"></a> supports_cpu_shared_memory

Belirten bir Boole değeri alır olmadığını `accelerator` paylaşılan belleği destekleyip.

```
__declspec(property(get= get_supports_cpu_shared_memory)) bool supports_cpu_shared_memory;
```

##  <a name="supports_double_precision"></a> supports_double_precision

Hızlandırıcı çift duyarlık Matematiği destekleyip desteklemediğini belirten bir Boole değeri alır.

```
__declspec(property(get= get_supports_double_precision)) bool supports_double_precision;
```

##  <a name="supports_limited_double_precision"></a> supports_limited_double_precision

Hızlandırıcı çift duyarlık Matematiği için sınırlı desteğe sahip olup olmadığını belirten Boolean bir değer alır. Hızlandırıcı ekleyin (FMA) birden çok kez çarpım yalnızca sınırlı destek varsa, bölme, karşıtlık ve arasındaki tür `int` ve `double` desteklenmez.

```
__declspec(property(get= get_supports_limited_double_precision)) bool supports_limited_double_precision;
```

##  <a name="version"></a> Sürüm

Sürümünü alır `accelerator`.

```
__declspec(property(get= get_version)) unsigned int version;
```

##  <a name="dtor"></a> </a> ~ accelerator_view

Yok eder [accelerator_view](accelerator-view-class.md) nesne.

```
~accelerator_view();
```

### <a name="return-value"></a>Dönüş Değeri

##  <a name="accelerator"></a> Hızlandırıcı

Alır `accelerator` nesnesi [accelerator_view](accelerator-view-class.md) nesne.

```
__declspec(property(get= get_accelerator)) Concurrency::accelerator accelerator;
```

##  <a name="ctor"></a> accelerator_view

Yeni bir örneğini başlatır [accelerator_view](accelerator-view-class.md) kopyalayarak mevcut bir sınıf `accelerator_view` nesne.

```
accelerator_view(const accelerator_view& _Other);
```

### <a name="parameters"></a>Parametreler

*_Diğer*<br/>
`accelerator_view` Kopyalanacak nesne.

##  <a name="create_marker"></a> create_marker

Şu ana kadar için verilmiş tüm komutların tamamlanmasını izlemek için bir gelecek döndürür `accelerator_view` nesne.

```
concurrency::completion_future create_marker();
```

### <a name="return-value"></a>Dönüş Değeri

Şu ana kadar için verilmiş tüm komutların tamamlanmasını izlemek için bir gelecek `accelerator_view` nesne.

##  <a name="flush"></a> Temizleme

Tüm bekleyen komutları kuyruğa gönderen [accelerator_view](accelerator-view-class.md) hızlandırıcıya yürütülmesi için nesne.

```
void flush();
```

### <a name="return-value"></a>Dönüş Değeri

Döndürür `void`.

##  <a name="get_accelerator"></a> get_accelerator

Döndürür `accelerator` nesnesi [accelerator_view](accelerator-view-class.md) nesne.

```
accelerator get_accelerator() const;
```

### <a name="return-value"></a>Dönüş Değeri

`accelerator` Nesnesi `accelerator_view` nesne.

##  <a name="get_is_auto_selection"></a> get_is_auto_selection

Accelerator_view geçirildiğinde çalışma zamanı otomatik olarak uygun bir Hızlandırıcı seçip seçmediğini gösteren bir Boole değeri döndürür bir [parallel_for_each](../../../parallel/concrt/reference/concurrency-namespace-functions.md#parallel_for_each).

```
bool get_is_auto_selection() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** çalışma zamanı otomatik olarak uygun bir Hızlandırıcı; seçer, aksi takdirde, **false**.

##  <a name="get_is_debug"></a> get_is_debug

Belirten bir Boole değeri döndürür olmadığını [accelerator_view](accelerator-view-class.md) nesne ayrıntılı hata raporlama için etkinleştirilen DEBUG katmanına sahip.

```
bool get_is_debug() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belirten Boolean bir değer olup olmadığını `accelerator_view` nesne ayrıntılı hata raporlama için etkinleştirilen DEBUG katmanına sahip.

##  <a name="get_queuing_mode"></a> get_queuing_mode

Sıralama modunu döndürür [accelerator_view](accelerator-view-class.md) nesne.

```
queuing_mode get_queuing_mode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kuyruklama modunu `accelerator_view` nesne.

##  <a name="get_version"></a> get_version

Sürümünü döndürür [accelerator_view](accelerator-view-class.md).

```
unsigned int get_version() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sürümü `accelerator_view`.

##  <a name="is_auto_selection"></a> is_auto_selection

Accelerator_view geçirildiğinde çalışma zamanı otomatik olarak uygun bir Hızlandırıcı seçip seçmediğini gösteren bir Boole değeri alır bir [parallel_for_each](../../../parallel/concrt/reference/concurrency-namespace-functions.md#parallel_for_each).

```
__declspec(property(get= get_is_auto_selection)) bool is_auto_selection;
```

##  <a name="is_debug"></a> is_debug

Gösteren bir Boole değeri alır olmadığını [accelerator_view](accelerator-view-class.md) nesne ayrıntılı hata raporlama için etkinleştirilen DEBUG katmanına sahip.

```
__declspec(property(get= get_is_debug)) bool is_debug;
```

##  <a name="operator_neq"></a> işleç! =

Bu karşılaştırır [accelerator_view](accelerator-view-class.md) döndürür ve başka nesnesi `false` aynı; olmaları durumunda döndürür, aksi takdirde, `true`.

```
bool operator!= (const accelerator_view& _Other) const;
```

### <a name="parameters"></a>Parametreler

*_Diğer*<br/>
`accelerator_view` İle Karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

**false** ise iki nesnenin aynı; Aksi takdirde, **true**.

##  <a name="operator_eq"></a> işleç =

Belirtilen içeriğini kopyalar [accelerator_view](accelerator-view-class.md) bu nesne içine.

```
accelerator_view& operator= (const accelerator_view& _Other);
```

### <a name="parameters"></a>Parametreler

*_Diğer*<br/>
`accelerator_view` Kopyalanacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Değiştirilmiş başvuru `accelerator_view` nesne.

##  <a name="operator_eq_eq"></a> işleç ==

Bu karşılaştırır [accelerator_view](accelerator-view-class.md) döndürür ve başka nesnesi **true** aynı; olmaları durumunda döndürür, aksi takdirde, **false**.

```
bool operator== (const accelerator_view& _Other) const;
```

### <a name="parameters"></a>Parametreler

*_Diğer*<br/>
`accelerator_view` İle Karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

**doğru** ise iki nesnenin aynı; Aksi takdirde, **false**.

##  <a name="queuing_mode"></a> queuing_mode

Kuyruklama modunu alır [accelerator_view](accelerator-view-class.md) nesne.

```
__declspec(property(get= get_queuing_mode)) Concurrency::queuing_mode queuing_mode;
```

##  <a name="version"></a> Sürüm

Sürümünü alır [accelerator_view](accelerator-view-class.md).

```
__declspec(property(get= get_version)) unsigned int version;
```

##  <a name="wait"></a> bekleme

Verilmiş tüm komutların bekler [accelerator_view](accelerator-view-class.md) tamamlamak için nesne.

```
void wait();
```

### <a name="return-value"></a>Dönüş Değeri

Döndürür `void`.

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
