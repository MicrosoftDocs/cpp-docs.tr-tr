---
title: CONCURRENCY::Direct3D ad alanı işlevleri (AMP) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- amp/Concurrency::direct3d::abs
- amp/Concurrency::direct3d::countbits
- amp/Concurrency::direct3d::create_accelerator_view
- amp/Concurrency::direct3d::d3d_access_lock
- amp/Concurrency::direct3d::d3d_access_unlock
- amp/Concurrency::direct3d::firstbithigh
- amp/Concurrency::direct3d::get_buffer
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
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b200ce8329c10fe2257ca3ce9ca8cb61125390fc
ms.sourcegitcommit: 0523c88b24d963c33af0529e6ba85ad2c6ee5afb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2018
---
# <a name="concurrencydirect3d-namespace-functions-amp"></a>CONCURRENCY::Direct3D ad alanı işlevleri (AMP)
||||  
|-|-|-|  
|[Abs](#abs)|[clamp](#clamp)|[countbits](#countbits)|
|[create_accelerator_view](#create_accelerator_view)|||
|[d3d_access_lock](#d3d_access_lock)|[d3d_access_try_lock](#d3d_access_try_lock)|[d3d_access_unlock](#d3d_access_unlock)|  
|[firstbithigh](#firstbithigh)|[firstbitlow](#firstbitlow)|[get_buffer](#get_buffer)|  
|[imax](#imax)|[imin](#imin)|[is_timeout_disabled](#is_timeout_disabled)|  
|[mad](#mad)|[make_array](#make_array)|[noise](#noise)|  
|[radyan cinsinden](#radians)|[rcp](#rcp)|[reversebits](#reversebits)|  
|[saturate](#saturate)|[sign](#sign)|[smoothstep](#smoothstep)|  
|[step](#step)|[umax](#umax)|[umin](#umin)|  

## <a name="requirements"></a>Gereksinimler
**Başlık:** amp.h **Namespace:** eşzamanlılık
  
##  <a name="abs"></a>  Abs  
 Bağımsız değişken mutlak değerini döndürür  
  
```  
inline int abs(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Tamsayı değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişken mutlak değerini döndürür.  
  
##  <a name="clamp"></a>  CLAMP  
 İkinci ve üçüncü belirtilen bağımsız değişkenler tarafından tanımlanan bir aralıkla clamped ilk belirtilen bağımsız değişkenin değeri hesaplar.  
  
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
 Clamped için değeri  
  
 `_Min`  
 Clamping aralığının alt sınırı.  
  
 `_Max`  
 Clamping aralığın üst sınırı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Clamped değeri `_X`.  
  
##  <a name="countbits"></a>  countbits  
 _X kümesi bit sayısını sayar  
  
```  
inline unsigned int countbits(unsigned int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 İmzasız tamsayı değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 İçinde _X kümesi bit sayısını döndürür  

## <a name="create_accelerator_view"></a> create_accelerator_view  
Oluşturur bir [accelerator_view](accelerator-view-class.md) bir işaretçi bir nesneden bir Direct3D aygıt arabirimi.  
  
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
 Oluşturulması olduğu yeni accelerator_view Hızlandırıcı.  
  
 `_D3D_device`  
 Direct3D aygıt arabirimi yönelik işaretçi.  
  
 `_Disable_timeout`  
 Zaman aşımı için yeni oluşturulan accelerator_view devre olup olmadığını belirten bir Boole parametresi. Bu Direct3D cihaz oluşturma için D3D11_CREATE_DEVICE_DISABLE_GPU_TIMEOUT bayrağı karşılık gelir ve işletim sistemi Windows zaman aşımı her aygıt için sıfırlamadan yürütmek için birden fazla 2 saniye sürebilir iş yükleri izin veriyorsa göstermek için kullanılır Algılama ve kurtarma mekanizması. Uzun süren görevler üzerinde accelerator_view gerçekleştirmeniz gerekiyorsa, bu bayrak kullanılması önerilir.  
  
 `_Qmode`  
 [Queuing_mode](concurrency-namespace-enums-amp.md#queuing_mode) yeni oluşturulan accelerator_view için kullanılacak. Bu parametrenin varsayılan değeri olan `queuing_mode_automatic`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `accelerator_view` Geçirilen Direct3D cihaz arabiriminden oluşturulan nesne.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev bir yeni oluşturur `accelerator_view` var olan bir işaretçi bir nesneden bir Direct3D aygıt arabirimi. İşlev çağrısı başarılı olursa, parametre başvurusu sayısı yoluyla artırılır bir `AddRef` çağırmak için arabirim. DirectX kodunuzda artık gerekli olduğunda, güvenli bir şekilde nesne serbest bırakabilirsiniz. Yöntem çağrısının başarısız olursa, bir [runtime_exception](runtime-exception-class.md) atılır.  
  
 `accelerator_view` Bu işlevi kullanarak oluşturduğunuz nesnesidir iş parçacığı açısından güvenlidir. Eşzamanlı kullanımı eşitlenmelidir `accelerator_view` nesnesi. Eşitlenmeyen eşzamanlı kullanımını `accelerator_view` nesne ve raw ID3D11Device arabirimi tanımsız davranış neden olur.  
  
 C++ AMP çalışma zamanı hata ayıklama modunda ayrıntılı hata bilgileri kullanırsanız D3D hata ayıklama katmanı kullanarak sağlar `D3D11_CREATE_DEVICE_DEBUG` bayrağı.  
  
  
##  <a name="d3d_access_lock"></a>  d3d_access_lock  
 Güvenli bir şekilde D3D işlemleri ile accelerator_view paylaşılan kaynaklar amacıyla bir accelerator_view üzerinde bir kilit. Accelerator_view ve dahili olarak bu accelerator_view ile ilişkili tüm C++ AMP kaynakları işlemleri yaparken bu kilit etkinleştirilir ve başka bir iş parçacığı D3D erişim kilidi tutan sırada engeller. Bu kilit özyinelemeli olmayan olduğu: zaten kilidi tutan bir iş parçacığından bu işlevi çağırmak için tanımlanmamış bir davranıştır. Accelerator_view veya D3D erişim kilit tutar iş accelerator_view ile ilişkili herhangi bir veri kapsayıcısı üzerinde işlem gerçekleştirmek için tanımlanmamış bir davranıştır. Scoped_d3d_access_lock, RAII stili sınıfı bir kapsam tabanlı D3D erişim kilidi için Ayrıca bkz.  
  
```  
void __cdecl d3d_access_lock(accelerator_view& _Av);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Av`  
 Kilitleme accelerator_view.  
  
##  <a name="d3d_access_try_lock"></a>  d3d_access_try_lock  
 D3D erişim bir accelerator_view engellenmeden Kilitle girişimi.  
  
```  
bool __cdecl d3d_access_try_lock(accelerator_view& _Av);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Av`  
 Kilitleme accelerator_view.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kilit alınırsa true, ya da şu anda başka bir iş parçacığı tarafından tutulan yoksa false.  
  
##  <a name="d3d_access_unlock"></a>  d3d_access_unlock  
 Verilen accelerator_view D3D erişim kilidi serbest bırakın. Çağıran iş parçacığı üzerinde accelerator_view kilidi barındırmıyorsa sonuçları tanımlanmamış.  
  
```  
void __cdecl d3d_access_unlock(accelerator_view& _Av);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Av`  
 Kilidi serbest bırakılacak olduğu accelerator_view.  
  
##  <a name="firstbithigh"></a>  firstbithigh  
 İlk en üst sıradaki bit ile başlayan ve doğru sırada düşük bit taşıma _X kümesi bit konumunu alır.  
  
```  
inline int firstbithigh(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Tamsayı değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk kümesi bit konumu  
  
##  <a name="firstbitlow"></a>  firstbitlow  
 İlk sipariş düşük bit ile başlayan ve doğru sırada yüksek bit çalışma _X kümesi bit konumunu alır.  
  
```  
inline int firstbitlow(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Tamsayı değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bit ayarlamak ilk konumunu döndürür  
  
##  <a name="get_buffer"></a>  get_buffer  
 Belirtilen dizi temel Direct3D arabellek arabirimi alın.  
  
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
 Dizi derecesini.  
  
 `_Array`  
 Temel alınan Direct3D arabellek arabirimi Direct3D accelerator_view üzerinde bir dizi döndürdü.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizi temel Direct3D arabellek karşılık gelen IUnknown arabirimi işaretçisi.  
  
##  <a name="imax"></a>  imax  
 Bağımsız değişkenler en büyük sayısal değerini belirleme  
  
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
 Bağımsız değişkenler en büyük sayısal değeri döndürür  
  
##  <a name="imin"></a>  imin  
 Bağımsız değişkenler en küçük sayısal değeri belirleme  
  
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
 Bağımsız değişkenler en küçük sayısal değeri döndürür  
  
##  <a name="is_timeout_disabled"></a>  is_timeout_disabled  
 Zaman aşımı için belirtilen accelerator_view devre dışı olup olmadığını gösteren bir Boole bayrağı döndürür. Bu Direct3D cihaz oluşturma için D3D11_CREATE_DEVICE_DISABLE_GPU_TIMEOUT bayrağı karşılık gelir.  
  
```  
bool __cdecl is_timeout_disabled(const accelerator_view& _Accelerator_view);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Accelerator_view`  
 Ayarını devre dışı zaman aşımını Sorgulanacak olduğu accelerator_view.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Zaman aşımı için belirtilen accelerator_view devre dışı olup olmadığını belirten bir boolean bayrak.  
  
##  <a name="mad"></a>  mad  
 Birinci ve ikinci belirtilen bağımsız değişken çarpımını hesaplar, sonra üçüncü belirtilen bağımsız değişken ekler.  
  
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
 İlk bağımsız değişken belirtilmiş.  
  
 `_Y`  
 İkinci bağımsız değişken belirtilmiş.  
  
 `_Z`  
 Üçüncü bağımsız değişken belirtilmiş.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sonucu `_X`  *  `_Y`  +  `_Z`.  
  
##  <a name="make_array"></a>  make_array  
 Bir dizi Direct3D arabellek arabirimi işaretçi oluşturun.  
  
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
 Oluşturulacak dizisinin öğe türü.  
  
 `_Rank`  
 Oluşturulacak dizi derecesini.  
  
 `_Extent`  
 Dizi toplama şeklini açıklar bir uzantı.  
  
 `_Rv`  
 Üzerinde oluşturulacak dizidir D3D Hızlandırıcı görüntüleyin.  
  
 `_D3D_buffer`  
 IUnknown arabirimi işaretçisi diziden oluşturmak için D3D arabellek.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sağlanan Direct3D arabellek kullanılarak oluşturulmuş bir dizi.  
  
##  <a name="noise"></a>  gürültü  
 Perlin gürültü algoritmasını kullanarak rastgele bir değeri oluşturur  
  
```  
inline float noise(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri Perlin gürültü oluşturmak için  
  
### <a name="return-value"></a>Dönüş Değeri  
 -1 ile 1 arasında bir aralık içinde Perlin gürültü değeri döndürür  
  
##  <a name="radians"></a>  radyan cinsinden  
 _X derece radyan için dönüştürür.  
  
```  
inline float radians(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Radyan cinsinden için derece dönüştürülen _X döndürür  
  
##  <a name="rcp"></a>  rcp  
 Belirtilen bağımsız değişken devrik hızlı yaklaşık kullanarak hesaplar.  
  
```  
inline float rcp(float _X) restrict(amp);

 
inline double rcp(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Devrik işlem istediğiniz değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen bağımsız değişken devrik.  
  
##  <a name="reversebits"></a>  reversebits  
 _X bitleri sırasını tersine çevirir  
  
```  
inline unsigned int reversebits(unsigned int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 İmzasız tamsayı değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 İçinde _X ters bit sırasına sahip değeri döndürür  
  
##  <a name="saturate"></a>  saturate  
 0 ve 1 aralığında _X clamps  
  
```  
inline float saturate(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Kayan nokta değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 0 ve 1 aralığında clamped _X döndürür  
  
##  <a name="sign"></a>  Oturum  
 Belirtilen bağımsız değişkenin işaretini belirler.  
  
```  
inline int sign(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_X`  
 Tamsayı değeri  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişkeni oturum.  
  
##  <a name="smoothstep"></a>  smoothstep  
 _X [_Min, _en] aralığında bir kesintisiz Hermite ilişkilendirme 0 ile 1 arasında döndürür.  
  
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
 _X _Min küçükse 0 döndürür; _X _en büyükse, 1; Aksi takdirde, 0 ve _X [_Min, _en] aralığında ise 1 arasında bir değer  
  
##  <a name="step"></a>  Adım  
 İki değer, 0 veya 1 hangi değerin büyük olduğuna bağlı olarak döndüren karşılaştırır  
  
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
 _X _Y eşit veya daha büyük ise 1 döndürür; Aksi takdirde, 0  
  
##  <a name="umax"></a>  UMAX  
 Bağımsız değişkenler en büyük sayısal değerini belirleme  
  
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
 Bağımsız değişkenler en büyük sayısal değeri döndürür  
  
##  <a name="umin"></a>  umin  
 Bağımsız değişkenler en küçük sayısal değeri belirleme  
  
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
 Bağımsız değişkenler en küçük sayısal değeri döndürür  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Concurrency::direct3d Ad Alanı](concurrency-direct3d-namespace.md)
