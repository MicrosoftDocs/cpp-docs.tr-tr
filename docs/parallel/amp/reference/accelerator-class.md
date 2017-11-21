---
title: "Hızlandırıcı sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
helpviewer_keywords: accelerator class
ms.assetid: 37eed593-cf87-4611-9cdc-e98df6c2377a
caps.latest.revision: "29"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5bdb3d081e9f7f1c2333d8bc577401b95ab0f858
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="accelerator-class"></a>accelerator Sınıfı
Hızlandırıcı veri paralel bilgisayarlar için optimize edilmiştir bir donanım özelliğidir. Hızlandırıcı PCIe veri yoluna (örneğin, bir GPU) bağlı bir cihaz olabilir veya genişletilmiş bir yönerge ana CPU üzerinde ayarlanmış olması olabilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class accelerator;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Hızlandırıcı Oluşturucusu](#ctor)|Yeni bir örneğini başlatır `accelerator` sınıfı.|  
|[~ accelerator yok Edicisi](#ctor)|Bozar `accelerator` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[create_view](#create_view)|Oluşturur ve döndüren bir `accelerator_view` bu Hızlandırıcı nesnesinde.|  
|[get_all](#get_all)|Bir vektör döndürür `accelerator` tüm kullanılabilir Hızlandırıcıları temsil eden nesne.|  
|[get_auto_selection_view](#get_auto_selection_view)|Otomatik Seçim döndürür `accelerator_view`.|  
|[get_dedicated_memory](#get_dedicated_memory)|İçin ayrılmış bellek döndürür `accelerator`, kilobayt cinsinden.|  
|[get_default_cpu_access_type](#get_default_cpu_access_type)|Varsayılan döndürür [access_type](concurrency-namespace-enums-amp.md#access_type) bu Hızlandırıcı üzerinde oluşturulan arabellekleri için.|  
|[get_default_view](#get_default_view)|Varsayılan döndürür `accelerator_view` ile ilişkili nesne `accelerator`.|  
|[get_description](#get_description)|Kısa bir açıklamasını döndürür `accelerator` aygıt.|  
|[get_device_path](#get_device_path)|Cihaz yolunu döndürür.|  
|[get_has_display](#get_has_display)|Belirler olup olmadığını `accelerator` bir görüntüye bağlı.|  
|[get_is_debug](#get_is_debug)|Belirler olup olmadığını `accelerator` kapsamlı hata bildirimi için etkin hata ayıklama katman vardır.|  
|[get_is_emulated](#get_is_emulated)|Belirler olup olmadığını `accelerator` öykündüğü.|  
|[get_supports_cpu_shared_memory](#get_supports_cpu_shared_memory)|Belirler olup olmadığını `accelerator` paylaşılan bellek destekler|  
|[get_supports_double_precision](#get_supports_double_precision)|Belirler olup olmadığını `accelerator` bir görüntüye bağlı.|  
|[get_supports_limited_double_precision](#get_supports_limited_double_precision)|Belirler olup olmadığını `accelerator` çift duyarlıklı matematik için destek sınırlıdır.|  
|[get_version](#get_version)|Sürümünü döndürür `accelerator`.|  
|[set_default](#set_default)|Varsayılan Hızlandırıcı yolunu döndürür.|  
|[set_default_cpu_access_type](#set_default_cpu_access_type)|Varsayılan CPU ayarlar [access_type](concurrency-namespace-enums-amp.md#access_type)diziler ve bu bilgisayarda yapılan örtük bellek ayırma için `accelerator`.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[operator! =](#operator_neq)|Bu karşılaştırır `accelerator` başka bir nesneyle ve döndürür `false` aynı; olmaları durumunda hata verir `true`.|  
|[işleç =](#operator_eq)|Belirtilen içeriğini kopyalar `accelerator` bu bir nesne.|  
|[operator ==](#operator_eq_eq)|Bu karşılaştırır `accelerator` başka bir nesneyle ve döndürür `true` aynı; olmaları durumunda hata verir `false`.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[cpu_accelerator](#cpu_accelerator)|CPU için sabit bir dize alır `accelerator`.|  
|[dedicated_memory](#dedicated_memory)|İçin ayrılmış bellek alır `accelerator`, kilobayt cinsinden.|  
|[default_accelerator](#default_accelerator)|İçin varsayılan bir dize sabit alır `accelerator`.|  
|[default_cpu_access_type](#default_cpu_access_type)|Alır veya ayarlar varsayılan CPU [access_type](concurrency-namespace-enums-amp.md#access_type)diziler ve bu bilgisayarda yapılan örtük bellek ayırma için `accelerator`.|  
|[default_view](#default_view)|Varsayılan alır `accelerator_view` ile ilişkili nesne `accelerator`.|  
|[Açıklama](#description)|Kısa bir açıklamasını alır `accelerator` aygıt.|  
|[device_path](#device_path)|Cihaz yolunu alır.|  
|[direct3d_ref](#direct3d_ref)|Direct3D başvuru için sabit bir dize alır `accelerator`.|  
|[direct3d_warp](#direct3d_warp)|Dize için sabit alır bir `accelerator` nesne Streaming SIMD Uzantıları (SSE) kullanan çok çekirdekli CPU C++ AMP kod yürütmek için kullanabilirsiniz.|  
|[has_display](#has_display)|Gösteren bir Boole değeri alır olup olmadığını `accelerator` bir görüntüye bağlı.|  
|[is_debug](#is_debug)|Gösterir olup olmadığını `accelerator` kapsamlı hata bildirimi için etkin hata ayıklama katman vardır.|  
|[is_emulated](#is_emulated)|Gösterir olup olmadığını `accelerator` öykündüğü.|  
|[supports_cpu_shared_memory](#supports_cpu_shared_memory)|Gösterir olup olmadığını `accelerator` paylaşılan bellek destekler.|  
|[supports_double_precision](#supports_double_precision)|Hızlandırıcı çift duyarlıklı matematik destekleyip desteklemediğini belirtir.|  
|[supports_limited_double_precision](#supports_limited_double_precision)|Hızlandırıcı sınırlı destek çift duyarlıklı matematik için olup olmadığını gösterir.|  
|[Sürüm](#version)|Sürümünü alır `accelerator`.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `accelerator`  
  
## <a name="remarks"></a>Açıklamalar  
 Hızlandırıcı veri paralel bilgisayarlar için optimize edilmiştir bir donanım özelliğidir. Hızlandırıcı ayrık GPU görülür, ancak bir sanal ana bilgisayar tarafı varlık DirectX REF cihazı TÜNELİ yoluyla SSE yönergeleri hızlandırılmış bir (CPU tarafı aygıt) ya da CPU gibi olabilir.  
  
 Oluşturabileceğiniz bir `accelerator` nesnesi kullanılabilir aygıtları listeleniyor ya da varsayılan cihaza, başvuru aygıt ya da TÜNELİ alınıyor.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** amprt.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="dtor"></a></a> ~ accelerator 

 Bozar `accelerator` nesnesi.  
  
```  
~accelerator();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
##  <a name="ctor"></a>Hızlandırıcı 

 Yeni bir örneğini başlatır [Hızlandırıcı sınıfı](accelerator-class.md).  
  
```  
accelerator();

 
explicit accelerator(const std::wstring& _Device_path);

 
accelerator(const accelerator& _Other);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Device_path`  
 Aygıt fiziksel yolu.  
  
 `_Other`  
 Kopyalamak için Hızlandırıcı.  
  
##  <a name="cpu_accelerator"></a>cpu_accelerator 

 Bir dize için CPU Hızlandırıcı sabit alır.  
  
```  
static const wchar_t cpu_accelerator[];  
```  
  
##  <a name="create_view"></a>create_view 

 Oluşturur ve döndüren bir `accelerator_view` belirtilen sıraya alma modunu kullanarak bu Hızlandırıcı nesnesinde. Sıralama modu değil belirtildiğinde, yeni `accelerator_view` kullanan [queuing_mode::immediate](concurrency-namespace-enums-amp.md#queuing_mode) sıraya alma modu.  
  
```  
accelerator_view create_view(queuing_mode qmode = queuing_mode_automatic);
```  
  
### <a name="parameters"></a>Parametreler  
 `qmode`  
 Sıraya alma modu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni bir `accelerator_view` belirtilen sıraya alma modunu kullanarak bu Hızlandırıcı nesnesinde.  
  
##  <a name="dedicated_memory"></a>dedicated_memory 

 İçin ayrılmış bellek alır `accelerator`, kilobayt cinsinden.  
  
```  
__declspec(property(get= get_dedicated_memory)) size_t dedicated_memory;  
```  
  
##  <a name="default_accelerator"></a>default_accelerator 

 İçin varsayılan bir dize sabit alır `accelerator`.  
  
```  
static const wchar_t default_accelerator[];  
```  
  
##  <a name="default_cpu_access_type"></a>default_cpu_access_type 

 Varsayılan cpu [access_type](concurrency-namespace-enums-amp.md#access_type)diziler ve bu üzerinde yapılan örtük bellek ayırma için `accelerator`.  
  
```  
__declspec(property(get= get_default_cpu_access_type)) access_type default_cpu_access_type;  
```  
  
##  <a name="default_view"></a>default_view 

 İle ilişkili varsayılan Hızlandırıcı görünümünü alır `accelerator`.  
  
```  
__declspec(property(get= get_default_view)) accelerator_view default_view;  
```  
  
##  <a name="description"></a>Açıklama 

 Kısa bir açıklamasını alır `accelerator` aygıt.  
  
```  
__declspec(property(get= get_description)) std::wstring description;  
```  
  
##  <a name="device_path"></a>device_path 

 Hızlandırıcı yolunu alır. Sistemde benzersiz yoludur.  
  
```  
__declspec(property(get= get_device_path)) std::wstring device_path;  
```  
  
##  <a name="direct3d_ref"></a>direct3d_ref 

 Bir dize için Direct3D başvuru Hızlandırıcı sabit alır.  
  
```  
static const wchar_t direct3d_ref[];  
```  
  
##  <a name="direct3d_warp"></a>direct3d_warp 

 Dize için sabit alır bir `accelerator` nesne C++ AMP kodunuzu Streaming SIMD Uzantıları (SSE) kullanarak çok çekirdekli CPU'larda yürütmek için kullanabilirsiniz.  
  
```  
static const wchar_t direct3d_warp[];  
```  
  
##  <a name="get_all"></a>get_all 

 Bir vektör döndürür `accelerator` tüm kullanılabilir Hızlandırıcıları temsil eden nesne.  
  
```  
static inline std::vector<accelerator> get_all();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kullanılabilir Hızlandırıcıları vektör  
  
##  <a name="get_auto_selection_view"></a>get_auto_selection_view 

 Otomatik Seçim accelerator_view döndürür hangi olduğunda çalışma zamanı tarafından otomatik olarak seçilmesini parallel_for_each çekirdek yürütmek hedef accelerator_view parallel_for_each hedef sonuçlarında olarak belirtilmiş. Diğer amaçlar için bu yöntem tarafından döndürülen accelerator_view varsayılan Hızlandırıcı varsayılan accelerator_view aynıdır  
  
```  
static accelerator_view __cdecl get_auto_selection_view();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Otomatik Seçim accelerator_view.  
  
##  <a name="get_dedicated_memory"></a>get_dedicated_memory 

 İçin ayrılmış bellek döndürür `accelerator`, kilobayt cinsinden.  
  
```  
size_t get_dedicated_memory() const;

 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İçin ayrılmış bellek `accelerator`, kilobayt cinsinden.  
  
##  <a name="get_default_cpu_access_type"></a>get_default_cpu_access_type 

 Bu Hızlandırıcı üzerinde oluşturulan arabellekleri için varsayılan cpu access_type alır  
  
```  
access_type get_default_cpu_access_type() const;

 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan cpu access_type bu Hızlandırıcı üzerinde oluşturulan arabellekleri için.  
  
##  <a name="get_default_view"></a>get_default_view 

 Varsayılan döndürür `accelerator_view` ile ilişkili nesne `accelerator`.  
  
```  
accelerator_view get_default_view() const;

 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan `accelerator_view` ile ilişkili nesne `accelerator`.  
  
##  <a name="get_description"></a>get_description 

 Kısa bir açıklamasını döndürür `accelerator` aygıt.  
  
```  
std::wstring get_description() const;

 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kısa bir açıklamasını `accelerator` aygıt.  
  
##  <a name="get_device_path"></a>get_device_path 

 Hızlandırıcı yolunu döndürür. Sistemde benzersiz yoludur.  
  
```  
std::wstring get_device_path() const;

 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sistem genelinde benzersiz cihaz örnek yolu.  
  
##  <a name="get_has_display"></a>get_has_display 

 Gösteren bir Boole değeri döndürür olup olmadığını `accelerator` bir ekrana çıkarabilirsiniz.  
  
```  
bool get_has_display() const;

 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`varsa `accelerator` bir ekrana; çıkarabilirsiniz Aksi halde, `false`.  
  
##  <a name="get_is_debug"></a>get_is_debug 

 Belirler olup olmadığını `accelerator` kapsamlı hata bildirimi için etkin hata ayıklama katman vardır.  
  
```  
bool get_is_debug() const;

 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`varsa `accelerator` kapsamlı hata bildirimi için etkin hata ayıklama katman vardır. Aksi takdirde `false`.  
  
##  <a name="get_is_emulated"></a>get_is_emulated 

 Belirler olup olmadığını `accelerator` öykündüğü.  
  
```  
bool get_is_emulated() const;

 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`varsa `accelerator` öykündüğü. Aksi takdirde `false`.  
  
##  <a name="get_supports_cpu_shared_memory"></a>get_supports_cpu_shared_memory 

 Hızlandırıcı bellek hem Hızlandırıcı ve CPU tarafından erişilebilir destekleyip desteklemediğini belirten bir Boole değeri döndürür.  
  
```  
bool get_supports_cpu_shared_memory() const;

 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Hızlandırıcı CPU paylaşılan bellek destekliyorsa; Aksi takdirde `false`.  
  
##  <a name="get_supports_double_precision"></a>get_supports_double_precision 

 Çarp dahil olmak üzere çift duyarlık matematik Hızlandırıcı destekleyip desteklemediğini Sigortalı gösteren bir Boole değeri döndürür (FMA) eklemek atama arasında bölme ve devrik `int` ve `double`.  
  
```  
bool get_supports_double_precision() const;

 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Hızlandırıcı çift duyarlık matematik destekliyorsa; Aksi takdirde `false`.  
  
##  <a name="get_supports_limited_double_precision"></a>get_supports_limited_double_precision 

 Hızlandırıcı sınırlı destek çift duyarlık matematik için olup olmadığını gösteren bir Boole değeri döndürür. Hızlandırıcı (FMA) eklemek Çarp Sigortalı yalnızca sınırlı destek varsa bölme, devrik ve atama arasında `int` ve `double` desteklenmez.  
  
```  
bool get_supports_limited_double_precision() const;

 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Hızlandırıcı çift duyarlık matematik; desteği sınırlaması durumunda Aksi takdirde `false`.  
  
##  <a name="get_version"></a>get_version 

 Sürümünü döndürür `accelerator`.  
  
```  
unsigned int get_version() const;

 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sürümü `accelerator`.  
  
##  <a name="has_display"></a>has_display 

 Gösteren bir Boole değeri alır olup olmadığını `accelerator` bir ekrana çıkarabilirsiniz.  
  
```  
__declspec(property(get= get_has_display)) bool has_display;  
```  
  
##  <a name="is_debug"></a>is_debug 

 Gösteren bir Boole değeri alır olup olmadığını `accelerator` kapsamlı hata bildirimi için etkin hata ayıklama katman vardır.  
  
```  
__declspec(property(get= get_is_debug)) bool is_debug;  
```  
  
##  <a name="is_emulated"></a>is_emulated 

 Gösteren bir Boole değeri alır olup olmadığını `accelerator` öykündüğü.  
  
```  
__declspec(property(get= get_is_emulated)) bool is_emulated;  
```  
  
##  <a name="operator_neq"></a>operator! = 

 Bu karşılaştırır `accelerator` başka bir nesneyle ve döndürür `false` aynı; olmaları durumunda hata verir `true`.  
  
```  
bool operator!= (const accelerator& _Other) const;

 
```  
  
### <a name="parameters"></a>Parametreler  
 `_Other`  
 `accelerator` İle Karşılaştırılacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `false`iki `accelerator` nesneleri aynıdır; Aksi halde, `true`.  
  
##  <a name="operator_eq"></a>işleç = 

 Belirtilen içeriğini kopyalar `accelerator` bu bir nesne.  
  
```  
accelerator& operator= (const accelerator& _Other);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Other`  
 `accelerator` Kopyalanacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu başvuru `accelerator` nesnesi.  
  
##  <a name="operator_eq_eq"></a>operator == 

 Bu karşılaştırır `accelerator` başka bir nesneyle ve döndürür `true` aynı; olmaları durumunda hata verir `false`.  
  
```  
bool operator== (const accelerator& _Other) const;

 
```  
  
### <a name="parameters"></a>Parametreler  
 `_Other`  
 `accelerator` İle Karşılaştırılacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`varsa diğer `accelerator` nesnesidir bu aynı `accelerator` nesne; Aksi halde, `false`.  
  
##  <a name="set_default"></a>set_default 

 Varsayılan Hızlandırıcı örtük olarak kullanan herhangi bir işlem için kullanılacak varsayılan Hızlandırıcı ayarlar. Çalışma zamanı seçilen varsayılan Hızlandırıcı varsayılan Hızlandırıcı örtük olarak kullanan bir işlem zaten kullanılmamış, bu yöntem yalnızca başarılı  
  
```  
static inline bool set_default(std::wstring _Path);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Path`  
 Hızlandırıcı yolu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`varsayılan Hızlandırıcı ayarı adresindeki çağrı başarılı olursa. Aksi takdirde `false`.  
  
##  <a name="set_default_cpu_access_type"></a>set_default_cpu_access_type 

 Bu Hızlandırıcı veya örtük bellek ayırmaları array_views parçası bu bilgisayarda bu Hızlandırıcı erişilen olarak oluşturulan diziler için varsayılan cpu access_type ayarlayın. Bu yöntem yalnızca Hızlandırıcı default_cpu_access_type kılınmadı bu yöntem için önceki bir çağrı tarafından zaten değil ve veya bir dizi ayırma için bu Hızlandırıcı seçili çalışma zamanı default_cpu_access_type henüz kullanılmamış başarılı Bu Hızlandırıcı üzerinde erişilen array_view yedekleme bir örtük bellek ayırma.  
  
```  
bool set_default_cpu_access_type(access_type _Default_cpu_access_type);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Default_cpu_access_type`  
 Bu Hızlandırıcı üzerinde dizi/array_view bellek ayırma için kullanılacak varsayılan cpu access_type.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan cpu access_type Hızlandırıcı için başarıyla ayarlandı gösteren bir Boole değeri.  
  
##  <a name="supports_cpu_shared_memory"></a>supports_cpu_shared_memory 

 Belirten bir Boole değeri alır olup olmadığını `accelerator` paylaşılan bellek destekler.  
  
```  
__declspec(property(get= get_supports_cpu_shared_memory)) bool supports_cpu_shared_memory;  
```  
  
##  <a name="supports_double_precision"></a>supports_double_precision 

 Hızlandırıcı çift duyarlıklı matematik destekleyip desteklemediğini belirten bir Boole değeri alır.  
  
```  
__declspec(property(get= get_supports_double_precision)) bool supports_double_precision;  
```  
  
##  <a name="supports_limited_double_precision"></a>supports_limited_double_precision 

 Hızlandırıcı sınırlı destek çift duyarlık matematik için olup olmadığını gösteren bir Boole değeri alır. Hızlandırıcı (FMA) eklemek Çarp Sigortalı yalnızca sınırlı destek varsa bölme, devrik ve atama arasında `int` ve `double` desteklenmez.  
  
```  
__declspec(property(get= get_supports_limited_double_precision)) bool supports_limited_double_precision;  
```  
  
##  <a name="version"></a>Sürüm 

 Sürümünü alır `accelerator`.  
  
```  
__declspec(property(get= get_version)) unsigned int version;  
```  
  
##  <a name="dtor"></a></a> ~ accelerator_view 

 Bozar [accelerator_view](accelerator-view-class.md) nesnesi.  
  
```  
~accelerator_view();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
##  <a name="accelerator"></a>Hızlandırıcı 

 Alır `accelerator` için nesne [accelerator_view](accelerator-view-class.md) nesnesi.  
  
```  
__declspec(property(get= get_accelerator)) Concurrency::accelerator accelerator;  
```  
  
##  <a name="ctor"></a>accelerator_view 

 Yeni bir örneğini başlatır [accelerator_view](accelerator-view-class.md) varolan kopyalayarak sınıfı `accelerator_view` nesnesi.  
  
```  
accelerator_view(const accelerator_view& _Other);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Other`  
 `accelerator_view` Kopyalamak için nesne.  
  
##  <a name="create_marker"></a>create_marker 

 Tamamlandığında şu ana kadar bu için gönderilen tüm komutlar, izlemek için gelecek döndürür `accelerator_view` nesnesi.  
  
```  
concurrency::completion_future create_marker();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tamamlandığında şu ana kadar bu için gönderilen tüm komutlar, izlemek için gelecek `accelerator_view` nesnesi.  
  
##  <a name="flush"></a>Temizleme 

 Tüm komutları bekleyen kuyruğa gönderen [accelerator_view](accelerator-view-class.md) yürütme için Hızlandırıcı nesnesine.  
  
```  
void flush();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `void`.  
  
##  <a name="get_accelerator"></a>get_accelerator 

 Döndürür `accelerator` için nesne [accelerator_view](accelerator-view-class.md) nesnesi.  
  
```  
accelerator get_accelerator() const;

 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `accelerator` İçin nesne `accelerator_view` nesne.  
  
##  <a name="get_is_auto_selection"></a>get_is_auto_selection 

 Accelerator_view geçirildiğinde çalışma zamanı otomatik olarak uygun Hızlandırıcı seçip olup olmadığını gösteren bir Boole değeri döndürür bir [parallel_for_each](../../../parallel/concrt/reference/concurrency-namespace-functions.md#parallel_for_each).  
  
```  
bool get_is_auto_selection() const;

 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`çalışma zamanı uygun Hızlandırıcı otomatik olarak seçer Aksi takdirde `false`.  
  
##  <a name="get_is_debug"></a>get_is_debug 

 Gösteren bir Boole değeri döndürür olup olmadığını [accelerator_view](accelerator-view-class.md) nesnenin kapsamlı hata bildirimi için etkin hata ayıklama katman vardır.  
  
```  
bool get_is_debug() const;

 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Gösteren bir Boole değeri olup olmadığını `accelerator_view` nesnenin kapsamlı hata bildirimi için etkin hata ayıklama katman vardır.  
  
##  <a name="get_queuing_mode"></a>get_queuing_mode 

 Sıralama modu için döndürür [accelerator_view](accelerator-view-class.md) nesnesi.  
  
```  
queuing_mode get_queuing_mode() const;

 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıralama modu için `accelerator_view` nesnesi.  
  
##  <a name="get_version"></a>get_version 

 Sürümünü döndürür [accelerator_view](accelerator-view-class.md).  
  
```  
unsigned int get_version() const;

 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sürümü `accelerator_view`.  
  
##  <a name="is_auto_selection"></a>is_auto_selection 

 Accelerator_view geçirildiğinde çalışma zamanı otomatik olarak uygun Hızlandırıcı seçip olup olmadığını gösteren bir Boole değeri alır bir [parallel_for_each](../../../parallel/concrt/reference/concurrency-namespace-functions.md#parallel_for_each).  
  
```  
__declspec(property(get= get_is_auto_selection)) bool is_auto_selection;  
```  
  
##  <a name="is_debug"></a>is_debug 

 Gösteren bir Boole değeri alır olup olmadığını [accelerator_view](accelerator-view-class.md) nesnenin kapsamlı hata bildirimi için etkin hata ayıklama katman vardır.  
  
```  
__declspec(property(get= get_is_debug)) bool is_debug;  
```  
  
##  <a name="operator_neq"></a>operator! = 

 Bu karşılaştırır [accelerator_view](accelerator-view-class.md) başka bir nesneyle ve döndürür `false` aynı; olmaları durumunda hata verir `true`.  
  
```  
bool operator!= (const accelerator_view& _Other) const;

 
```  
  
### <a name="parameters"></a>Parametreler  
 `_Other`  
 `accelerator_view` İle Karşılaştırılacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `false`iki nesnenin aynı olup olmadığını; Aksi takdirde `true`.  
  
##  <a name="operator_eq"></a>işleç = 

 Belirtilen içeriğini kopyalar [accelerator_view](accelerator-view-class.md) bunu nesnesine.  
  
```  
accelerator_view& operator= (const accelerator_view& _Other);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Other`  
 `accelerator_view` Kopyalanacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir başvuru değiştirilmiş `accelerator_view` nesnesi.  
  
##  <a name="operator_eq_eq"></a>operator == 

 Bu karşılaştırır [accelerator_view](accelerator-view-class.md) başka bir nesneyle ve döndürür `true` aynı; olmaları durumunda hata verir `false`.  
  
```  
bool operator== (const accelerator_view& _Other) const;

 
```  
  
### <a name="parameters"></a>Parametreler  
 `_Other`  
 `accelerator_view` İle Karşılaştırılacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`iki nesnenin aynı olup olmadığını; Aksi takdirde `false`.  
  
##  <a name="queuing_mode"></a>queuing_mode 

 Sıraya alma modunu alır [accelerator_view](accelerator-view-class.md) nesnesi.  
  
```  
__declspec(property(get= get_queuing_mode)) Concurrency::queuing_mode queuing_mode;  
```  
  
##  <a name="version"></a>Sürüm 

 Sürümünü alır [accelerator_view](accelerator-view-class.md).  
  
```  
__declspec(property(get= get_version)) unsigned int version;  
```  
  
##  <a name="wait"></a>bekleme 

 Gönderilen tüm komutlar için bekleyeceği [accelerator_view](accelerator-view-class.md) tamamlamak için nesne.  
  
```  
void wait();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `void`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)
