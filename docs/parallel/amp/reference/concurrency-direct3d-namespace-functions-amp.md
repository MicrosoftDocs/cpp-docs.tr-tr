---
title: Concurrency::direct3d ad alanı işlevleri (AMP)
ms.date: 08/31/2018
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
ms.assetid: 28943b62-52c9-42dc-baf1-ca7b095c1a19
ms.openlocfilehash: bf98249001c2b8227581fbbbcceeebd085e5d820
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88831118"
---
# <a name="concurrencydirect3d-namespace-functions-amp"></a>Concurrency::direct3d ad alanı işlevleri (AMP)

:::row:::
   :::column span="":::
      [mutlak](#abs)\
      [Clamp](#clamp)\
      [countbits](#countbits)\
      [create_accelerator_view](#create_accelerator_view)\
      [d3d_access_lock](#d3d_access_lock)\
      [d3d_access_try_lock](#d3d_access_try_lock)\
      [d3d_access_unlock](#d3d_access_unlock)
   :::column-end:::
   :::column span="":::
      [firstbithigh](#firstbithigh)\
      [firstbitlow](#firstbitlow)\
      [get_buffer](#get_buffer)\
      [get_device](#get_device)\
      [IMAX](#imax)\
      [imin](#imin)\
      [is_timeout_disabled](#is_timeout_disabled)
   :::column-end:::
   :::column span="":::
      [Mad](#mad)\
      [make_array](#make_array)\
      [gürültü](#noise)\
      [radyan](#radians)\
      [rcp](#rcp)\
      [reversebits](#reversebits)
   :::column-end:::
   :::column span="":::
      [saturate](#saturate)\
      [imzalayabilirsiniz](#sign)\
      [smoothstep](#smoothstep)\
      [ından](#step)\
      ['ın](#umax)\
      [umın](#umin)
   :::column-end:::
:::row-end:::

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** amp. h **ad alanı:** eşzamanlılık

## <a name="abs"></a><a name="abs"></a> mutlak

Bağımsız değişkenin mutlak değerini döndürür

```cpp
inline int abs(int _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin mutlak değerini döndürür.

## <a name="clamp"></a><a name="clamp"></a> Clamp

İkinci ve üçüncü belirtilen bağımsız değişkenlerle tanımlanan bir aralığa çakışılan ilk belirtilen bağımsız değişkenin değerini hesaplar.

```cpp
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

*_X*<br/>
Çakışılan değer

*_Min*<br/>
Clamping aralığının alt sınırı.

*_Max*<br/>
Clamping aralığının üst sınırı.

### <a name="return-value"></a>Dönüş Değeri

Öğesinin çakışan değeri `_X` .

## <a name="countbits"></a><a name="countbits"></a> countbits

_X içindeki küme bitlerinin sayısını sayar

```cpp
inline unsigned int countbits(unsigned int _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
İşaretsiz tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri

_X içindeki küme bitlerinin sayısını döndürür

## <a name="create_accelerator_view"></a><a name="create_accelerator_view"></a> create_accelerator_view

Direct3D cihaz arabirimine yönelik bir işaretçiden [accelerator_view](accelerator-view-class.md) nesnesi oluşturur.

## <a name="syntax"></a>Söz dizimi

```cpp
accelerator_view create_accelerator_view(
    IUnknown * _D3D_device
    queuing_mode _Qmode = queuing_mode_automatic);

accelerator_view create_accelerator_view(
    accelerator& _Accelerator,
    bool _Disable_timeout
    queuing_mode _Qmode = queuing_mode_automatic);
```

### <a name="parameters"></a>Parametreler

*_Accelerator*<br/>
Yeni accelerator_view oluşturulacağı hızlandırıcı.

*_D3D_device*<br/>
Direct3D cihaz arabirimine yönelik işaretçi.

*_Disable_timeout*<br/>
Yeni oluşturulan accelerator_view için zaman aşımının devre dışı bırakılıp bırakılmadığını belirten bir Boole parametresi. Bu, Direct3D cihaz oluşturma için D3D11_CREATE_DEVICE_DISABLE_GPU_TIMEOUT bayrağına karşılık gelir ve işletim sisteminin, Windows zaman aşımı algılama ve kurtarma mekanizmasına göre cihazı sıfırlamadan 2 saniyeden uzun sürme iş yüklerinin yürütülmesi gerekip gerekmediğini belirtmek için kullanılır. Accelerator_view üzerinde zaman alan görevler gerçekleştirmeniz gerekirse bu bayrağın kullanılması önerilir.

*_Qmode*<br/>
Yeni oluşturulan accelerator_view için kullanılacak [queuing_mode](concurrency-namespace-enums-amp.md#queuing_mode) . Bu parametrenin varsayılan değeri vardır `queuing_mode_automatic` .

## <a name="return-value"></a>Dönüş Değeri

`accelerator_view`Geçirilen Direct3D cihaz arabiriminden oluşturulan nesne.

## <a name="remarks"></a>Açıklamalar

Bu işlev, varolan bir `accelerator_view` Işaretçiden Direct3D cihaz arabirimine yeni bir nesne oluşturur. İşlev çağrısı başarılı olursa, parametrenin başvuru sayısı, arabirime yapılan çağrı yoluyla artırılır `AddRef` . DirectX kodunuzda artık gerekli olmadığında nesneyi güvenle serbest bırakabilirsiniz. Yöntem çağrısı başarısız olursa, bir [runtime_exception](runtime-exception-class.md) oluşturulur.

`accelerator_view`Bu işlevi kullanarak oluşturduğunuz nesne, iş parçacığı güvenlidir. Nesnenin eşzamanlı kullanımını eşitlemeniz gerekir `accelerator_view` . `accelerator_view`Nesne ve ham ID3D11Device arabiriminin eşitlenmemiş eşzamanlı kullanımı tanımsız davranışa neden olur.

C++ AMP Runtime, bayrağını kullanırsanız D3D hata ayıklama katmanını kullanarak hata ayıklama modunda ayrıntılı hata bilgileri sağlar `D3D11_CREATE_DEVICE_DEBUG` .

## <a name="d3d_access_lock"></a><a name="d3d_access_lock"></a> d3d_access_lock

Accelerator_view paylaşılan kaynaklarda D3D işlemlerini güvenle gerçekleştirmek amacıyla accelerator_view bir kilit elde edin. Accelerator_view ve bu accelerator_view ilişkili tüm C++ AMP kaynakları, işlem gerçekleştirirken bu kilidi dahili olarak alır ve başka bir iş parçacığında D3D erişim kilidi tutulduğu zaman engellenir. Bu kilit özyinelemeli değil: Bu işlevi kilidi zaten tutan bir iş parçacığından çağırmak tanımsız bir davranıştır. Accelerator_view veya D3D erişim kilidini tutan iş parçacığından accelerator_view ilişkili herhangi bir veri kapsayıcısı üzerinde işlem gerçekleştirmek için tanımsız bir davranıştır. Ayrıca bkz. scoped_d3d_access_lock, kapsam tabanlı D3D erişim kilidi için bir ÇII stili sınıf.

```cpp
void __cdecl d3d_access_lock(accelerator_view& _Av);
```

### <a name="parameters"></a>Parametreler

*_Av*<br/>
Kilitlenecek accelerator_view.

## <a name="d3d_access_try_lock"></a><a name="d3d_access_try_lock"></a> d3d_access_try_lock

Blok olmadan bir accelerator_view D3D erişim kilidi alma girişimi.

```cpp
bool __cdecl d3d_access_try_lock(accelerator_view& _Av);
```

### <a name="parameters"></a>Parametreler

*_Av*<br/>
Kilitlenecek accelerator_view.

### <a name="return-value"></a>Dönüş Değeri

kilit alınırsa doğru veya şu anda başka bir iş parçacığı tarafından tutuluyorsa yanlış olur.

## <a name="d3d_access_unlock"></a><a name="d3d_access_unlock"></a> d3d_access_unlock

Belirtilen accelerator_view D3D erişim kilidini serbest bırakın. Çağıran iş parçacığı accelerator_view kilidi tutamaz, sonuçlar tanımsız olur.

```cpp
void __cdecl d3d_access_unlock(accelerator_view& _Av);
```

### <a name="parameters"></a>Parametreler

*_Av*<br/>
Kilit yayımlanacak accelerator_view.

## <a name="firstbithigh"></a><a name="firstbithigh"></a> firstbithigh

En yüksek sıralı bitten başlayarak ve en düşük sıra bitine geçerek _X ilk küme bitinin konumunu alır.

```cpp
inline int firstbithigh(int _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri

İlk küme bitinin konumu

## <a name="firstbitlow"></a><a name="firstbitlow"></a> firstbitlow

En düşük sıralı bitden başlayarak ve en yüksek sıralı bit 'e doğru çalışarak, _X ilk küme bitinin konumunu alır.

```cpp
inline int firstbitlow(int _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri

İlk küme bitinin konumunu döndürür

## <a name="get_buffer"></a><a name="get_buffer"></a> get_buffer

Belirtilen diziyi temel alan Direct3D arabellek arabirimini alın.

```cpp
template<
    typename value_type,
    int _Rank
>
IUnknown *get_buffer(
    const array<value_type, _Rank>& _Array)  ;
```

### <a name="parameters"></a>Parametreler

*value_type*<br/>
Dizideki öğelerin türü.

*_Rank*<br/>
Dizinin derecesi.

*_Array*<br/>
Temel alınan Direct3D arabellek arabiriminin döndürüldüğü Direct3D accelerator_view bir dizi.

### <a name="return-value"></a>Dönüş Değeri

Dizinin temelindeki Direct3D arabelleğine karşılık gelen IUnknown arabirim işaretçisi.

## <a name="a-nameget_device-get_device"></a><a name="get_device"> get_device

Accelerator_view temel alan D3D cihaz arabirimini alın.

```cpp
IUnknown* get_device(const accelerator_view Av);
```

### <a name="parameters"></a>Parametreler

*Virüsten*<br/>
Temel alınan D3D cihaz arabiriminin döndürüldüğü D3D accelerator_view.

### <a name="return-value"></a>Döndürülen değer

`IUnknown`Accelerator_view temel alan D3D cihazının arabirim işaretçisi.

## <a name="imax"></a><a name="imax"></a> IMAX

Bağımsız değişkenlerin en büyük sayısal değerini belirleme

```cpp
inline int imax(
    int _X,
    int _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Tamsayı değeri

*_Y*<br/>
Tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenlerin en büyük sayısal değerini döndürür

## <a name="imin"></a><a name="imin"></a> imin

Bağımsız değişkenlerin en küçük sayısal değerini belirleme

```cpp
inline int imin(
    int _X,
    int _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Tamsayı değeri

*_Y*<br/>
Tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenlerin en küçük sayısal değerini döndürür

## <a name="is_timeout_disabled"></a><a name="is_timeout_disabled"></a> is_timeout_disabled

Belirtilen accelerator_view için zaman aşımının devre dışı bırakılıp bırakılmadığını belirten bir Boole bayrağı döndürür. Bu, Direct3D cihaz oluşturma için D3D11_CREATE_DEVICE_DISABLE_GPU_TIMEOUT bayrağına karşılık gelir.

```cpp
bool __cdecl is_timeout_disabled(const accelerator_view& _Accelerator_view);
```

### <a name="parameters"></a>Parametreler

*_Accelerator_view*<br/>
Zaman aşımı devre dışı ayarının sorgulanacağı accelerator_view.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen accelerator_view için zaman aşımının devre dışı bırakılıp bırakılmadığını belirten bir Boole bayrağı.

## <a name="mad"></a><a name="mad"></a> Mad

Birinci ve ikinci belirtilen bağımsız değişkenin ürününü hesaplar ve ardından üçüncü belirtilen bağımsız değişkeni ekler.

```cpp
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

*_X*<br/>
Belirtilen ilk bağımsız değişken.

*_Y*<br/>
Belirtilen ikinci bağımsız değişken.

*_Z*<br/>
Belirtilen üçüncü bağımsız değişken.

### <a name="return-value"></a>Dönüş Değeri

Sonucu `_X` \* `_Y`  +  `_Z` .

## <a name="make_array"></a><a name="make_array"></a> make_array

Direct3D arabellek arabirim işaretçisinden bir dizi oluşturun.

```cpp
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

*value_type*<br/>
Oluşturulacak dizinin öğe türü.

*_Rank*<br/>
Oluşturulacak dizinin derecesi.

*_Extent*<br/>
Dizi toplamanın şeklini açıklayan bir uzantı.

*_Rv*<br/>
Dizinin oluşturulacağı D3D Hızlandırıcısı görünümü.

*_D3D_buffer*<br/>
Dizi oluşturmak için D3D arabelleğinin IUnknown arabirim işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen Direct3D arabelleği kullanılarak oluşturulan dizi.

## <a name="noise"></a><a name="noise"></a> gürültü

Perlin gürültü algoritmasını kullanarak rastgele bir değer üretir

```cpp
inline float noise(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Perlin gürültüsü oluşturulacak kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

-1 ile 1 arasında bir Aralık içindeki perlin gürültü değerini döndürür

## <a name="radians"></a><a name="radians"></a> radyan

_X dereceden radyana dönüştürür

```cpp
inline float radians(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Dereceden radyana dönüştürülecek _X döndürür

## <a name="rcp"></a><a name="rcp"></a> rcp

Hızlı bir yaklaşık kullanarak belirtilen bağımsız değişkenin tersini hesaplar.

```cpp
inline float rcp(float _X) restrict(amp);

inline double rcp(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Devrik değerin hesaplanması için değer.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen bağımsız değişkenin tersi.

## <a name="reversebits"></a><a name="reversebits"></a> reversebits

_X içindeki bitlerin sırasını tersine çevirir

```cpp
inline unsigned int reversebits(unsigned int _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
İşaretsiz tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri

Bit sırası ters çevrilen değeri _X döndürür

## <a name="saturate"></a><a name="saturate"></a> saturate

Clamps, 0 ile 1 arasında _X

```cpp
inline float saturate(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

0 ile 1 arasında bir _X çakışıyor döndürür

## <a name="sign"></a><a name="sign"></a> imzalayabilirsiniz

Belirtilen bağımsız değişkenin işaretini belirler.

```cpp
inline int sign(int _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin işareti.

## <a name="smoothstep"></a><a name="smoothstep"></a> smoothstep

_X [_Min, _Max] aralığalıyorsa, 0 ile 1 arasında yumuşak bir Hermite ilişkilendirmeyi döndürür.

```cpp
inline float smoothstep(
    float _Min,
    float _Max,
    float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Min*<br/>
Kayan nokta değeri

*_Max*<br/>
Kayan nokta değeri

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X _Min daha küçükse 0 döndürür; _X _Max daha büyükse 1; Aksi takdirde, _X Aralık içinde ise 0 ile 1 arasında bir değer [_Min, _Max]

## <a name="step"></a><a name="step"></a> ından

İki değeri karşılaştırır; 0 veya 1 döndüren değerin daha büyük olması gerekir

```cpp
inline float step(
    float _Y,
    float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Y*<br/>
Kayan nokta değeri

*_X*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X _Y eşit veya daha büyükse 1 döndürür; Aksi takdirde, 0

## <a name="umax"></a><a name="umax"></a> 'ın

Bağımsız değişkenlerin en büyük sayısal değerini belirleme

```cpp
inline unsigned int umax(
    unsigned int _X,
    unsigned int _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Tamsayı değeri

*_Y*<br/>
Tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenlerin en büyük sayısal değerini döndürür

## <a name="umin"></a><a name="umin"></a> umın

Bağımsız değişkenlerin en küçük sayısal değerini belirleme

```cpp
inline unsigned int umin(
    unsigned int _X,
    unsigned int _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_X*<br/>
Tamsayı değeri

*_Y*<br/>
Tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenlerin en küçük sayısal değerini döndürür

## <a name="see-also"></a>Ayrıca bkz.

[Concurrency::direct3d Ad Alanı](concurrency-direct3d-namespace.md)
