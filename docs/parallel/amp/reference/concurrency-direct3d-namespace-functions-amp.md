---
title: CONCURRENCY::Direct3D ad alanı işlevleri (AMP) | Microsoft Docs
ms.custom: ''
ms.date: 08/31/2018
ms.topic: reference
f1_keywords:
- amp/Concurrency::direct3d::abs
- amp/Concurrency::direct3d::countbits
- amp/Concurrency::direct3d::create_accelerator_view
- amp/Concurrency::direct3d::d3d_access_lock
- amp/Concurrency::direct3d::d3d_access_unlock
- amp/Concurrency::direct3d::firstbithigh
- amp/Concurrency::direct3d::get_buffer
- amp/Concurrency::direct3d::get_device
- amp/Concurrency::direct3d::imax
- amp/Concurrency::direct3d::is_timeout_disabled
- amp/Concurrency::direct3d::mad
- amp/Concurrency::direct3d::noise
- amp/Concurrency::direct3d::radians
- amp/Concurrency::direct3d::reversebits
- amp/Concurrency::direct3d::saturate
- amp/Concurrency::direct3d::smoothstep
- amp/Concurrency::direct3d::step
- amp/Concurrency::direct3d::umin
dev_langs:
- C++
ms.assetid: 28943b62-52c9-42dc-baf1-ca7b095c1a19
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 099bd36908ef12d2cd4c6b4603dc047d7ed6e74f
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44107613"
---
# <a name="concurrencydirect3d-namespace-functions-amp"></a>CONCURRENCY::Direct3D ad alanı işlevleri (AMP)
||||
|-|-|-|
|[Abs](#abs)|[CLAMP](#clamp)|[countbits](#countbits)|
|[create_accelerator_view](#create_accelerator_view)|[d3d_access_lock](#d3d_access_lock)||
|[d3d_access_try_lock](#d3d_access_try_lock)|[d3d_access_unlock](#d3d_access_unlock)|[firstbithigh](#firstbithigh)|
|[firstbitlow](#firstbitlow)|[get_buffer](#get_buffer)|[get_device](#get_device)|
|[imax](#imax)|[imin](#imin)|[is_timeout_disabled](#is_timeout_disabled)|
|[mad](#mad)|[make_array](#make_array)|[gürültü](#noise)|
|[radyan cinsinden](#radians)|[rcp](#rcp)|[reversebits](#reversebits)|
|[Saturate](#saturate)|[sign](#sign)|[smoothstep](#smoothstep)|
|[Adım](#step)|[umax](#umax)|[umin](#umin)|

## <a name="requirements"></a>Gereksinimler
**Başlık:** amp.h **Namespace:** eşzamanlılık

##  <a name="abs"></a>  Abs
Bağımsız değişkenin mutlak değerini döndürür

```  
inline int abs(int _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin mutlak değerini döndürür.

##  <a name="clamp"></a>  CLAMP
İkinci ve üçüncü belirtilen bağımsız değişkenlerle tanımlanan aralığa kenetlenen ilk belirtilen bağımsız değişkenin değerini hesaplar.

```  
inline float clamp(
    float _X,
    float _Min,
    float _Max) restrict(amp);


inline int clamp(
    int _X,
    int _Min,
    int _Max) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kenetlenecek değer

`_Min`  
Clamping aralığının alt sınırı.

`_Max`  
Clamping aralığının üst sınırı.

### <a name="return-value"></a>Dönüş Değeri
Öğesinin kenetlenen değeri `_X`.

##  <a name="countbits"></a>  countbits
_X içindeki belirlenmiş bitleri sayar

```  
inline unsigned int countbits(unsigned int _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
İşaretsiz bir tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri
_X belirlenmiş bitleri sayısını döndürür

## <a name="create_accelerator_view"></a> create_accelerator_view
Oluşturur bir [accelerator_view](accelerator-view-class.md) nesneye bir işaretçiden Direct3D cihaz arayüzü.

## <a name="syntax"></a>Sözdizimi

```  
accelerator_view create_accelerator_view(  
    IUnknown * _D3D_device
    queuing_mode _Qmode = queuing_mode_automatic);

accelerator_view create_accelerator_view(  
    accelerator& _Accelerator,
    bool _Disable_timeout
    queuing_mode _Qmode = queuing_mode_automatic);
```  

#### <a name="parameters"></a>Parametreler
`_Accelerator`  
Üzerinde yeni Hızlandırıcı görünümünün oluşturulması için Hızlandırıcı.

`_D3D_device`  
Direct3D cihaz arayüzü işaretçisi.

`_Disable_timeout`  
Zaman aşımı yeni oluşturulan accelerator_view için devre dışı olup olmadığını belirten bir Boole parametresi. Bu, Direct3D cihaz oluşturma için d3d11_create_devıce_dısable_gpu_tımeout bayrağına karşılık gelir ve işletim sistemi cihazı Windows zaman aşımı sıfırlamadan yürütmek için birden fazla 2 saniye Süren iş yükleri izin veriyorsa belirtmek için kullanılır Algılama ve kurtarma mekanizmanızı. Accelerator_view'de zaman alıcı görevleri gerçekleştirmek gerekiyorsa bu bayrağı kullanmanız önerilir.

`_Qmode`  
[Queuing_mode](concurrency-namespace-enums-amp.md#queuing_mode) yeni oluşturulan accelerator_view için kullanılacak. Bu parametrenin varsayılan değeri `queuing_mode_automatic`.

## <a name="return-value"></a>Dönüş Değeri
`accelerator_view` Nesnesi, geçirilen Direct3D cihaz arayüzü kullanılarak oluşturulur.

## <a name="remarks"></a>Açıklamalar
Bu işlev yeni bir oluşturur `accelerator_view` nesne var olan bir işaretçiden Direct3D cihaz arabirimine. İşlev çağrısı başarılı olursa, parametre referans sayısı yoluyla artırılır bir `AddRef` çağırmak için arabirim. DirectX kodunuzda artık gerek duyduğunda, nesneyi güvenle serbest bırakabilirsiniz. Yöntem çağrısı başarısız olursa bir [runtime_exception](runtime-exception-class.md) oluşturulur.

`accelerator_view` Bu işlevi kullanarak oluşturduğunuz nesnedir iş parçacığı açısından güvenlidir. Eş zamanlı kullanımını eşitlemelisiniz `accelerator_view` nesne. Eşitlenmemiş eş zamanlı kullanımını `accelerator_view` nesne ve ham ıd3d11device arabirimi tanımlanamayan davranışa neden olur.

C++ AMP çalışma zamanı kullanırsanız, D3D hata ayıklama katmanını kullanarak hata ayıklama modunda ayrıntılı hata bilgileri sağlar. `D3D11_CREATE_DEVICE_DEBUG` bayrağı.


##  <a name="d3d_access_lock"></a>  d3d_access_lock
Güvenli şekilde D3D Hızlandırıcı görünümü ile paylaşılan kaynaklarda işlemleri gerçekleştirmek amacıyla accelerator_view üzerinde kilidi. Accelerator_view ve bu accelerator_view ile dahili olarak ilişkili tüm C++ AMP kaynaklar, işlemleri gerçekleştirirken bu kilit etkinleştirilir ve başka bir iş parçacığı D3D erişim kilidini tutan sırada engeller. Bu kilit yinelemesizdir: Bu işlev çağrısı zaten Kilit tutan bir iş parçacığından tanımlı bir davranıştır. Accelerator_view veya accelerator_view D3D erişim kilit tuttuğunda iş parçacığından ilişkili herhangi bir veri kapsayıcısına işlemleri tanımsız bir davranıştır. Ayrıca bkz: scoped_d3d_access_lock, kapsam tabanlı D3D erişim kilidi için bir RAII stil sınıf.

```  
void __cdecl d3d_access_lock(accelerator_view& _Av);
```  

### <a name="parameters"></a>Parametreler
`_Av`  
Kilitlenecek accelerator_view.

##  <a name="d3d_access_try_lock"></a>  d3d_access_try_lock
Engelleme olmadan accelerator_view üzerinde D3D erişim kilidi edinmeye çalışın.

```  
bool __cdecl d3d_access_try_lock(accelerator_view& _Av);
```  

### <a name="parameters"></a>Parametreler
`_Av`  
Kilitlenecek accelerator_view.

### <a name="return-value"></a>Dönüş Değeri
Kilit alındıysa doğru ya da şu anda başka bir iş parçacığı tarafından tutuluyorsa yanlış.

##  <a name="d3d_access_unlock"></a>  d3d_access_unlock
Verilen accelerator_view üzerindeki D3D erişim kilidini serbest bırakın. Çağıran iş parçacığı accelerator_view üzerinde kilidi tutmazsa sonuçlar tanımsızdır.

```  
void __cdecl d3d_access_unlock(accelerator_view& _Av);
```  

### <a name="parameters"></a>Parametreler
`_Av`  
Kilidin serbest bırakılacağı accelerator_view.

##  <a name="firstbithigh"></a>  firstbithigh
En yüksek sıralı bitten başlayarak ve en düşük sıralı bite ilerleyerek _X içinde ilk belirlenen bitin konumunu alır.

```  
inline int firstbithigh(int _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri
İlk bit kümesinin konumu

##  <a name="firstbitlow"></a>  firstbitlow
En düşük sıralı bitten başlayarak ve en yüksek sıralı bite çalışarak _X içinde ilk belirlenen bitin konumunu alır.

```  
inline int firstbitlow(int _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri
İlk set bit konumunu döndürür

##  <a name="get_buffer"></a>  get_buffer
Belirtilen diziye temel olan Direct3D arabellek arayüzünü alın.

```  
template<
    typename value_type,
    int _Rank
>
IUnknown *get_buffer(
    const array<value_type, _Rank>& _Array)  ;
```  

### <a name="parameters"></a>Parametreler
`value_type`  
Dizideki öğelerin türü.

`_Rank`  
Dizinin boyut.

`_Array`  
Altındaki Direct3D arabellek arayüzünün bir Direct3D accelerator_view üzerindeki dizi döndürülür.

### <a name="return-value"></a>Dönüş Değeri
Dizinin altındaki Direct3D arabelleğine karşılık gelen IUnknown arabirim işaretçisi.

## <a name="a-namegetdevice-getdevice"></a><a name="get_device"> get_device
Temel alınan bir accelerator_view D3D cihaz arayüzünü alın.

```
IUnknown* get_device(const accelerator_view Av);
```

### <a name="parameters"></a>Parametreler
*AV*<br/>
Kendisi için temel D3D cihaz arabirimi döndürülür D3D Hızlandırıcı görünümü.


### <a name="return-value"></a>Dönüş değeri
`IUnknown` Temel accelerator_view D3D cihazı arayüz işaretçisi.

##  <a name="imax"></a>  imax
Bağımsız değişkenlerin en büyük sayısal değerini belirler

```  
inline int imax(
    int _X,
    int _Y) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Tamsayı değeri

`_Y`  
Tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenlerin en büyük sayısal değerini döndürür

##  <a name="imin"></a>  imin
Bağımsız değişkenlerin en küçük sayısal değerini belirler

```  
inline int imin(
    int _X,
    int _Y) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Tamsayı değeri

`_Y`  
Tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenlerin en düşük sayısal değerini döndürür

##  <a name="is_timeout_disabled"></a>  is_timeout_disabled
Zaman aşımı için belirtilen Hızlandırıcı görünümü devre dışı olup olmadığını belirten bir Boole bayrağı döndürür. Bu, Direct3D cihaz oluşturma için d3d11_create_devıce_dısable_gpu_tımeout karşılık gelir.

```  
bool __cdecl is_timeout_disabled(const accelerator_view& _Accelerator_view);
```  

### <a name="parameters"></a>Parametreler
`_Accelerator_view`  
Sorgulanacağı accelerator_view için zaman aşımı ayarını devre dışı olduğundan.

### <a name="return-value"></a>Dönüş Değeri
Zaman aşımı için belirtilen Hızlandırıcı görünümü devre dışı olup olmadığını belirten bir Boole bayrağı.

##  <a name="mad"></a>  MAD
Birinci ve ikinci belirtilen bağımsız değişken ürününü hesaplar ve ardından üçüncü belirtilen bağımsız değişkeni ekler.

```  
inline float mad(
    float _X,
    float _Y,
    float _Z) restrict(amp);


inline double mad(
    double _X,
    double _Y,
    double _Z) restrict(amp);


inline int mad(
    int _X,
    int _Y,
    int _Z) restrict(amp);


inline unsigned int mad(
    unsigned int _X,
    unsigned int _Y,
    unsigned int _Z) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
İlk belirtilen bağımsız değişken.

`_Y`  
İkinci belirtilen bağımsız değişken.

`_Z`  
Üçüncü belirtilen bağımsız değişken.

### <a name="return-value"></a>Dönüş Değeri
Sonucu `_X` \* `_Y`  +  `_Z`.

##  <a name="make_array"></a>  make_array
Bir Direct3D arabellek arayüz işaretçisinden bir dizi oluşturun.

```  
template<
    typename value_type,
    int _Rank
>
array<value_type, _Rank> make_array(
    const extent<_Rank>& _Extent,
    const Concurrency::accelerator_view& _Rv,
    IUnknown* _D3D_buffer)  ;
```  

### <a name="parameters"></a>Parametreler
`value_type`  
Oluşturulacak dizinin öğe türü.

`_Rank`  
Oluşturulacak dizinin derecesi.

`_Extent`  
Dizi toplamanın şeklini açıklayan uzantı.

`_Rv`  
Üzerinde dizinin oluşturulması bir D3D Hızlandırıcısı görünümü.

`_D3D_buffer`  
Diziden oluşturulacağı D3D arabellek IUnknown arabirim işaretçisi.

### <a name="return-value"></a>Dönüş Değeri
Sağlanan Direct3D arabelleği kullanılarak oluşturulan bir dizi.

##  <a name="noise"></a>  gürültü
Perlin gürültü algoritmasını kullanarak rastgele bir değer oluşturur

```  
inline float noise(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Perlin gürültü içinden kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
-1 ile 1 arasında bir aralık içinde Perlin gürültü değeri döndürür

##  <a name="radians"></a>  radyan cinsinden
_X'i dereceden radyana çevirir.

```  
inline float radians(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
_X'i dereceden radyana dönüştürülecek döndürür

##  <a name="rcp"></a>  rcp
Hızlı bir yaklaşık değer belirleme kullanarak belirtilen bağımsız değişkenin tersini hesaplar.

```  
inline float rcp(float _X) restrict(amp);


inline double rcp(double _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Karşıtının istediğiniz değer.

### <a name="return-value"></a>Dönüş Değeri
Belirtilen bağımsız değişkenin karşıtı.

##  <a name="reversebits"></a>  reversebits
_X'deki bitlerin sırasını tersine çevirir

```  
inline unsigned int reversebits(unsigned int _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
İşaretsiz bir tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri
_X ters bit sıradaki değerini döndürür.

##  <a name="saturate"></a>  Saturate
0 ile 1 aralığında _x'i sıkıştırır.

```  
inline float saturate(float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
_X'in, 0 ile 1 aralığında kenetlenen döndürür

##  <a name="sign"></a>  oturum
Belirtilen bağımsız değişkenin işaretini belirler.

```  
inline int sign(int _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenin işaretini.

##  <a name="smoothstep"></a>  smoothstep
_X [_Min, _Max] aralığında ise, 0 ile 1 arasında düzgün bir Hermite enterpolasyon döndürür.

```  
inline float smoothstep(
    float _Min,
    float _Max,
    float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_Min`  
Kayan nokta değeri

`_Max`  
Kayan nokta değeri

`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
_X _Min küçükse, 0 döndürür; _X _Max büyükse, 1; Aksi halde, 0 ile _X [_Min, _Max] aralığında ise 1 arasında bir değer

##  <a name="step"></a>  Adım
İki değer, 0 veya 1 hangi değerin daha büyük olduğuna göre karşılaştırır.

```  
inline float step(
    float _Y,
    float _X) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_Y`  
Kayan nokta değeri

`_X`  
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri
_X'i büyüktür veya eşittir _Y ise 1 döndürür; Aksi takdirde 0

##  <a name="umax"></a>  UMAX
Bağımsız değişkenlerin en büyük sayısal değerini belirler

```  
inline unsigned int umax(
    unsigned int _X,
    unsigned int _Y) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Tamsayı değeri

`_Y`  
Tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenlerin en büyük sayısal değerini döndürür

##  <a name="umin"></a>  umin
Bağımsız değişkenlerin en küçük sayısal değerini belirler

```  
inline unsigned int umin(
    unsigned int _X,
    unsigned int _Y) restrict(amp);
```  

### <a name="parameters"></a>Parametreler
`_X`  
Tamsayı değeri

`_Y`  
Tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri
Bağımsız değişkenlerin en düşük sayısal değerini döndürür

## <a name="see-also"></a>Ayrıca Bkz.
[Concurrency::direct3d Ad Alanı](concurrency-direct3d-namespace.md)
