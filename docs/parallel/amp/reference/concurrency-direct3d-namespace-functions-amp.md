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
ms.openlocfilehash: e21b1f2869ab81973b341abc5371714fbf8580e2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375927"
---
# <a name="concurrencydirect3d-namespace-functions-amp"></a>Concurrency::direct3d ad alanı işlevleri (AMP)

||||
|-|-|-|
|[Abs](#abs)|[Kelepçe](#clamp)|[countbits](#countbits)|
|[create_accelerator_view](#create_accelerator_view)|[d3d_access_lock](#d3d_access_lock)||
|[d3d_access_try_lock](#d3d_access_try_lock)|[d3d_access_unlock](#d3d_access_unlock)|[firstbithigh](#firstbithigh)|
|[firstbitlow](#firstbitlow)|[get_buffer](#get_buffer)|[get_device](#get_device)|
|[imax](#imax)|[imin](#imin)|[is_timeout_disabled](#is_timeout_disabled)|
|[Mad](#mad)|[make_array](#make_array)|[Gürültü](#noise)|
|[Radyan](#radians)|[Rcp](#rcp)|[ters bitler](#reversebits)|
|[Doymuş](#saturate)|[Işareti](#sign)|[smoothstep](#smoothstep)|
|[Adım](#step)|[Umax](#umax)|[umin](#umin)|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** amp.h **Namespace:** Eşzamanlılık

## <a name="abs"></a><a name="abs"></a>Abs

Bağımsız değişkenin mutlak değerini verir

```cpp
inline int abs(int _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenin mutlak değerini verir.

## <a name="clamp"></a><a name="clamp"></a>Kelepçe

İkinci ve üçüncü belirtilen bağımsız değişkenler tarafından tanımlanan bir arayla kenetlenmiş ilk belirtilen bağımsız değişkenin değerini hesaplar.

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

*_x*<br/>
Kenetlenecek değer

*_Min*<br/>
Bağlama aralığının alt sınırı.

*_Max*<br/>
Bağlama aralığının üst sınırı.

### <a name="return-value"></a>Dönüş Değeri

Sıkıştırılmış `_X`değeri.

## <a name="countbits"></a><a name="countbits"></a>countbits

_X'daki ayarlı bit sayısını sayar

```cpp
inline unsigned int countbits(unsigned int _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
İmzasız tümseci değeri

### <a name="return-value"></a>Dönüş Değeri

_X'daki ayarlı bit sayısını verir

## <a name="create_accelerator_view"></a><a name="create_accelerator_view"></a>create_accelerator_view

Bir [işaretçiden](accelerator-view-class.md) Direct3D aygıt arabirimine accelerator_view nesnesi oluşturur.

## <a name="syntax"></a>Sözdizimi

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
Yeni accelerator_view oluşturulacak hızlandırıcı.

*_D3D_device*<br/>
Direct3D aygıt arabiriminin işaretçisi.

*_Disable_timeout*<br/>
Yeni oluşturulan accelerator_view için zaman anındevre dışı bırakılıp atılmayacağını belirten bir Boolean parametresi. Bu, Direct3D aygıt oluşturma için D3D11_CREATE_DEVICE_DISABLE_GPU_TIMEOUT bayrağına karşılık gelir ve işletim sisteminin aygıtı Windows zaman aşım algılama ve kurtarma mekanizmasına göre sıfırlamadan yürütmesi 2 saniyeden fazla süren iş yüklerinin izin verilip vermediğini belirtmek için kullanılır. accelerator_view zaman alıcı görevleri gerçekleştirmeniz gerekiyorsa bu bayrağın kullanılması önerilir.

*_Qmode*<br/>
Yeni oluşturulan accelerator_view için kullanılacak [queuing_mode.](concurrency-namespace-enums-amp.md#queuing_mode) Bu parametrenin varsayılan `queuing_mode_automatic`değeri .

## <a name="return-value"></a>Dönüş Değeri

Geçen `accelerator_view` Direct3D aygıt arabiriminden oluşturulan nesne.

## <a name="remarks"></a>Açıklamalar

Bu işlev, varolan bir işaretçiden Direct3D aygıt arabirimine yeni `accelerator_view` bir nesne oluşturur. İşlev çağrısı başarılı olursa, parametrenin başvuru sayısı arabirime yapılan `AddRef` bir çağrı ile artımlanır. DirectX kodunuzda artık gerekkalmadığında nesneyi güvenle serbest bırakabilirsiniz. Yöntem çağrısı başarısız olursa, [bir runtime_exception](runtime-exception-class.md) atılır.

Bu `accelerator_view` işlevi kullanarak oluşturduğunuz nesne iş parçacığı güvenlidir. Nesnenin `accelerator_view` eşzamanlı kullanımını eşitlemeniz gerekir. Nesnenin ve ham ID3D11Device arabiriminin `accelerator_view` senkronize edilmemiş eşzamanlı kullanımı tanımlanmamış davranışlara neden olur.

C++ AMP çalışma süresi, `D3D11_CREATE_DEVICE_DEBUG` bayrağı kullanırsanız D3D Hata Ayıklama katmanını kullanarak hata ayıklama modunda ayrıntılı hata bilgileri sağlar.

## <a name="d3d_access_lock"></a><a name="d3d_access_lock"></a>d3d_access_lock

accelerator_view paylaşılan kaynaklarda D3D işlemlerini güvenli bir şekilde gerçekleştirmek amacıyla bir accelerator_view kilitleyin. Bu accelerator_view ilişkili accelerator_view ve tüm C++ AMP kaynakları işlemleri gerçekleştirirken bu kilidi dahili olarak alır ve başka bir iş parçacığı D3D erişim kilidi tutarken engeller. Bu kilit özyinelemeli değildir: Bu işlevi kilidi zaten tutan bir iş parçacığından çağırmak tanımlanmamış davranıştır. D3D erişim kilidi tutan iş parçacığı ndan accelerator_view veya accelerator_view ilişkili herhangi bir veri kapsayıcısı üzerinde işlem gerçekleştirmek için tanımlanmamış davranıştır. Ayrıca, kapsam tabanlı D3D erişim kilidi için RAII tarzı bir sınıf olan scoped_d3d_access_lock da bakın.

```cpp
void __cdecl d3d_access_lock(accelerator_view& _Av);
```

### <a name="parameters"></a>Parametreler

*_Av*<br/>
Kilitleme accelerator_view.

## <a name="d3d_access_try_lock"></a><a name="d3d_access_try_lock"></a>d3d_access_try_lock

Engellemeden bir accelerator_view D3D erişim kilidi elde etmeye çalış.

```cpp
bool __cdecl d3d_access_try_lock(accelerator_view& _Av);
```

### <a name="parameters"></a>Parametreler

*_Av*<br/>
Kilitleme accelerator_view.

### <a name="return-value"></a>Dönüş Değeri

kilit elde edildiyse doğru veya şu anda başka bir iş parçacığı tarafından tutuluyorsa yanlış.

## <a name="d3d_access_unlock"></a><a name="d3d_access_unlock"></a>d3d_access_unlock

Verilen accelerator_view D3D erişim kilidini bırakın. Arama iş parçacığı kilidi kilit tutmazsa accelerator_view sonuçlar tanımsız.

```cpp
void __cdecl d3d_access_unlock(accelerator_view& _Av);
```

### <a name="parameters"></a>Parametreler

*_Av*<br/>
Kilidin serbest bırakılabilmek için accelerator_view.

## <a name="firstbithigh"></a><a name="firstbithigh"></a>firstbithigh

En yüksek sıralı bitle başlayıp en düşük sıralı bite doğru hareket eden ilk ayar bitinin _X'daki yerini alır.

```cpp
inline int firstbithigh(int _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri

İlk ayar bitinin konumu

## <a name="firstbitlow"></a><a name="firstbitlow"></a>firstbitlow

en düşük sıralı bitle başlayıp en yüksek sıralı bitdoğru çalışarak _X ilk ayar bitinin konumunu alır.

```cpp
inline int firstbitlow(int _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri

İlk ayar bitinin konumunu döndürür

## <a name="get_buffer"></a><a name="get_buffer"></a>get_buffer

Belirtilen dizinin altında yatan Direct3D arabellek arabirimini alın.

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
Dizinin sıralaması.

*_Array*<br/>
Direct3D accelerator_view'nde temel Direct3D arabellek arabiriminin döndürüldildiği bir dizi.

### <a name="return-value"></a>Dönüş Değeri

Dizinin altında yatan Direct3D arabelleğine karşılık gelen IUnknown arabirim işaretçisi.

## <a name="a-nameget_device-get_device"></a><a name="get_device">get_device

bir accelerator_view altında yatan D3D aygıt arabirimini alın.

```cpp
IUnknown* get_device(const accelerator_view Av);
```

### <a name="parameters"></a>Parametreler

*Av*<br/>
Altta yatan D3D aygıt arabiriminin döndürüldeği D3D accelerator_view.

### <a name="return-value"></a>Döndürülen değer

accelerator_view `IUnknown` altında yatan D3D aygıtının arabirim işaretçisi.

## <a name="imax"></a><a name="imax"></a>ımax

Bağımsız değişkenlerin maksimum sayısal değerini belirleme

```cpp
inline int imax(
    int _X,
    int _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Tamsayı değeri

*_Y*<br/>
Tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenlerin maksimum sayısal değerini döndürme

## <a name="imin"></a><a name="imin"></a>imin

Bağımsız değişkenlerin minimum sayısal değerini belirleme

```cpp
inline int imin(
    int _X,
    int _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Tamsayı değeri

*_Y*<br/>
Tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenlerin minimum sayısal değerini döndürme

## <a name="is_timeout_disabled"></a><a name="is_timeout_disabled"></a>is_timeout_disabled

Belirtilen accelerator_view için zaman adedinin devre dışı bırakıldığını belirten bir boolean bayrağı döndürür. Bu, Direct3D aygıt oluşturma için D3D11_CREATE_DEVICE_DISABLE_GPU_TIMEOUT bayrağına karşılık gelir.

```cpp
bool __cdecl is_timeout_disabled(const accelerator_view& _Accelerator_view);
```

### <a name="parameters"></a>Parametreler

*_Accelerator_view*<br/>
Zaman ayarı devre dışı bırakılan accelerator_view sorgulanacak.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen accelerator_view için zaman anına mı devre dışı bırakıldığını belirten bir boolean bayrağı.

## <a name="mad"></a><a name="mad"></a>Mad

Birinci ve ikinci belirtilen bağımsız değişkenin ürünlerini hesaplar, ardından üçüncü belirtilen bağımsız değişkeni ekler.

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

*_x*<br/>
İlk belirtilen bağımsız değişken.

*_Y*<br/>
İkinci belirtilen bağımsız değişken.

*_Z*<br/>
Üçüncü belirtilen bağımsız değişken.

### <a name="return-value"></a>Dönüş Değeri

`_X` \* `_Y`  + Bunun `_Z`sonucu.

## <a name="make_array"></a><a name="make_array"></a>make_array

Direct3D arabellek arabirimi işaretçisinden bir dizi oluşturun.

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
Oluşturulacak dizinin sıralaması.

*_Extent*<br/>
Dizi toplamının şeklini açıklayan bir boyut.

*_Rv*<br/>
Dizinin oluşturulacak olduğu Bir D3D hızlandırıcı görünümü.

*_D3D_buffer*<br/>
D3D arabelleği IUnknown arabirim işaretçisi dizi oluşturmak için.

### <a name="return-value"></a>Dönüş Değeri

Sağlanan Direct3D arabelleği kullanılarak oluşturulan bir dizi.

## <a name="noise"></a><a name="noise"></a>Gürültü

Perlin gürültü algoritmasını kullanarak rasgele bir değer oluşturur

```cpp
inline float noise(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Perlin gürültüsü oluşturmak için kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

-1 ve 1 arasındaki bir aralıkta Perlin gürültü değerini verir

## <a name="radians"></a><a name="radians"></a>Radyan

_X derecelerden radyanlara dönüştürür

```cpp
inline float radians(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

Derecelerden radyanlara dönüştürülen _X döndürür

## <a name="rcp"></a><a name="rcp"></a>Rcp

Hızlı bir yaklaşım kullanarak belirtilen bağımsız değişkenin karşıtlıklarını hesaplar.

```cpp
inline float rcp(float _X) restrict(amp);

inline double rcp(double _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Karşılığı hesaplayabilmek için gereken değer.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen bağımsız değişkenin karşılığı.

## <a name="reversebits"></a><a name="reversebits"></a>ters bitler

_X'daki bitsırasını tersine çevirir

```cpp
inline unsigned int reversebits(unsigned int _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
İmzasız tümseci değeri

### <a name="return-value"></a>Dönüş Değeri

_X ters çevrilmiş bit sırası ile değeri verir

## <a name="saturate"></a><a name="saturate"></a>Doymuş

Kelepçeler 0 -1 aralığında _X

```cpp
inline float saturate(float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

0 ile 1 arasında kenetlenmiş _X döndürür

## <a name="sign"></a><a name="sign"></a>Işareti

Belirtilen bağımsız değişkenin işaretini belirler.

```cpp
inline int sign(int _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri

Tartışmanın işareti.

## <a name="smoothstep"></a><a name="smoothstep"></a>smoothstep

_X aralığındaysa 0 ile 1 arasında düzgün bir Hermite enterpolasyonu verir [_Min, _Max].

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

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X _Min'den azsa 0 döndürür; _X _Max büyükse 1; aksi takdirde, _X aralığındaysa 0 ile 1 arasındaki bir değer [_Min, _Max]

## <a name="step"></a><a name="step"></a>Adım

Değeri daha büyük olan 0 veya 1 döndürerek iki değeri karşılaştırır

```cpp
inline float step(
    float _Y,
    float _X) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Y*<br/>
Kayan nokta değeri

*_x*<br/>
Kayan nokta değeri

### <a name="return-value"></a>Dönüş Değeri

_X _Y'den büyük veya eşitse 1 döndürür; aksi takdirde, 0

## <a name="umax"></a><a name="umax"></a>Umax

Bağımsız değişkenlerin maksimum sayısal değerini belirleme

```cpp
inline unsigned int umax(
    unsigned int _X,
    unsigned int _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Tamsayı değeri

*_Y*<br/>
Tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenlerin maksimum sayısal değerini döndürme

## <a name="umin"></a><a name="umin"></a>umin

Bağımsız değişkenlerin minimum sayısal değerini belirleme

```cpp
inline unsigned int umin(
    unsigned int _X,
    unsigned int _Y) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_x*<br/>
Tamsayı değeri

*_Y*<br/>
Tamsayı değeri

### <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkenlerin minimum sayısal değerini döndürme

## <a name="see-also"></a>Ayrıca bkz.

[Concurrency::direct3d Ad Alanı](concurrency-direct3d-namespace.md)
