---
title: Grafikler (C++ AMP) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 190a98a4-5f7d-442e-866b-b374ca74c16f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 97c673e564a91447854dc02a18ced0b4f0061a9f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46408225"
---
# <a name="graphics-c-amp"></a>Grafikler (C++ AMP)

C++ AMP alanındaki birkaç API içeren [Concurrency::graphics](../../parallel/amp/reference/concurrency-graphics-namespace.md) Gpu'lar üzerindeki doku desteğine erişmek için kullanabileceğiniz bir ad alanı. Bazı yaygın senaryolar şunlardır:

- Kullanabileceğiniz [doku](../../parallel/amp/reference/texture-class.md) sınıfını hesaplama için bir veri depolayıcı olarak *uzamsal yerelliğinden* düzenleri GPU donanımının doku önbelleğinin ve. Uzamsal yerelliğinden veri öğelerinin fiziksel olarak birbirlerine yakın olan bir özelliktir.

- Çalışma zamanı işlem olmayan gölgelendiriciler ile birlikte verimli karşılıklı sağlar. Piksel, Tepe noktası, Mozaik döşeme ve Kabuk gölgelendiriciler sıklıkla kullanan veya C++ AMP hesaplamalarınızda kullanabileceğiniz dokular üretir.

- Grafik API'leri, C++ AMP altı paketlenmiş arabelleklere erişmenin alternatif yollarını word sağlar. Temsil eden biçimlerdeki dokular *texel'in* (doku öğeleri) 8-bit oluşan ya da 16 bitlik skalerlerden gibi paket veri depolarına erişmesine izin verin.

## <a name="the-norm-and-unorm-types"></a>Norm ve unorm türleri

`norm` Ve `unorm` türleridir aralığını sınırlayan skaler türler **float** değerleri; bu olarak bilinir *clamping*. Bu türler, diğer skaler türlerden açıkça oluşturulabilir. Dönüştürme değeri ilk türüne dönüştürülür **float** ve ardından norm [-1.0, 1.0] veya [0.0, 1.0] unorm tarafından izin verilen ilgili bölgeye kenetlenen. +/-Sonsuzdan +/-1 döndürür. Nan'dan tanımsızdır. Bir norm örtük olarak bir unorm oluşturulabilir ve veri kaybı olmadan yoktur. Kayan nokta değerine örtülü dönüştürme işleci bu türlerde tanımlıdır. İkili işleçler tanımlanmış bu türleri ve diğer yerleşik skaler türler arasında gibi **float** ve **int**: +, -, \*, /, ==,! =, >, \<, > =, < =. Bileşik atama işleçleri de destekler: +=,-=, \*=, / =. Tekli değilleme işleci (-) norm türleri için tanımlanır.

## <a name="short-vector-library"></a>Kısa vektör kitaplığı

Kısa vektör kitaplığı bazı işlevlerini sağlar [vektör türü](http://go.microsoft.com/fwlink/p/?linkid=248500) HLSL'de tanımlı olan ve genellikle texel'in tanımlamak için kullanılır. Bir kısa vektörü aynı türde bir ile dört değerleri içeren bir veri yapısıdır. Desteklenen türler **çift**, **float**, **int**, `norm`, `uint`, ve `unorm`. Tür adları aşağıdaki tabloda gösterilmektedir. Her türü için var. Ayrıca karşılık gelen **typedef** adı, alt çizgi yoktur. Altçizginin olduğu türler bulunan [Concurrency::graphics Namespace](../../parallel/amp/reference/concurrency-graphics-namespace.md). Alt çizgileri olmayan türleri bulunan [CONCURRENCY::Graphics:: Direct3D Namespace](../../parallel/amp/reference/concurrency-graphics-direct3d-namespace.md) bunlar açıkça benzer şekilde adlandırılmış temel türlerden gibi şekilde isimlendirilmiş **__int8** ve **__int16**.

||Uzunluğu 2|Uzunluğu 3|Uzunluğu 4|
|-|--------------|--------------|--------------|
|çift|double_2<br /><br /> double2|double_3<br /><br /> double3|double_4<br /><br /> double4|
|float|float_2<br /><br /> float2|float_3<br /><br /> float3|float_4<br /><br /> float4|
|int|int_2<br /><br /> int2|int_3<br /><br /> ınt3|int_4<br /><br /> int4|
|norm|norm_2<br /><br /> norm2|norm_3<br /><br /> norm3|norm_4<br /><br /> norm4|
|uint|uint_2<br /><br /> uint2|uint_3<br /><br /> uint3|uint_4<br /><br /> uint4|
|unorm|unorm_2<br /><br /> unorm2|unorm_3<br /><br /> unorm3|unorm_4<br /><br /> unorm4|

### <a name="operators"></a>İşleçler

Bir işleç iki kısa vektör arasında tanımlıysa, ardından bunu ayrıca bir kısa vektörü ile bir skaler değer arasında tanımlanır. Ayrıca, bunlardan biri doğru olmalıdır:

- Skaler değerin türü kısa vektörün öğe türü ile aynı olması gerekir.

- Skaler değerin türü, bir vektörün öğe türü için yalnızca bir kullanıcı tanımlı dönüştürme kullanılarak örtük olarak dönüştürülebilir.

İşlem, kısa vektörün her bileşeni ve skaler arasında bileşene odaklı taşınır. Geçerli işleçler şunlardır:

|İşleç türü|Geçerli türler|
|-------------------|-----------------|
|İkili işleçler|Tüm türlerde geçerlidir: +, -, \*, /,<br /><br /> Tamsayı türlerinde geçerlidir: %, ^, &#124;&, <\<, >><br /><br /> İki vektörün aynı boyutta olması gerekir ve sonuç aynı boyutta bir vektördür.|
|İlişkisel işleçleri|Tüm türlerde geçerlidir: == ve! =|
|Bileşik atama işleci|Tüm türlerde geçerlidir: +=,-=, \*=, / =<br /><br /> Tamsayı türlerinde geçerlidir: % =, ^ =, &#124;= & =, <\<= >> =|
|Artırma ve azaltma işleçleri|Tüm türlerde geçerlidir: ++,--<br /><br /> Gerek önek, gerekse sonek geçerli değil.|
|Bit düzeyinde NOT işleci (~)|Tamsayı türlerinde geçerlidir.|
|Birli - işleç|Geçerli dışında tüm türler `unorm` ve `uint`.|

### <a name="swizzling-expressions"></a>Swizzling ifadeleri

Kısa vektör kitaplığı destekler `vector_type.identifier` kısa vektörün bileşenlerine erişmek için erişimci kalıbını. `identifier`, Olarak bilinen bir *swizzling ifadesi*, vektörün bileşenlerini belirtir. İfade, bir l-değeri ya da bir r olabilir. Tanımlayıcı tek karakterler olabilir: x, y, z ve w; ya da r, g, b ve a. "x" ve "r" sıfırıncı bileşen, "y" ve "g" ortalama ilk bileşen ve benzeri anlamına gelir. (Bildirim "x" ve "r" aynı tanımlayıcıda kullanılamaz.) Dolayısıyla "rgba" ve "xyzw" aynı sonucu döndürür. "X" gibi tek bileşenli erişimciler ve "y" skaler değer türleridir. Çok bileşenli erişimciler kısa vektör türleridir. Örneğin, oluşturmak, bir `int_4` adlı vektör `fourInts` ve değer 2, 4, 6 ve 8, ardından `fourInts.y` tamsayı 4 değerini ve `fourInts.rg` döndürür bir `int_2` 2 ve 4 değerlerine sahip nesne.

## <a name="texture-classes"></a>Doku sınıfları

Çoğu GPU'nun, donanım ve piksel ve doku hücreleri getirmek ve görüntü ve dokuları işlemek için optimize edilmiş önbellekleri vardır. [Doku\<T, N >](../../parallel/amp/reference/texture-class.md) doku hücresi nesneler için bir kapsayıcı sınıfı olan sınıfı bu Gpu'lar doku işlevini kullanıma sunar. Bir texel şunlar olabilir:

- Bir **int**, `uint`, **float**, **çift**, `norm`, veya `unorm` skaler.

- İki veya dört bileşeni olan kısa bir vektör. Tek özel durum `double_4`, hangi izin verilmiyor.

`texture` Nesnesi 1, 2 veya 3 derecesine sahip olabilir. `texture` Nesne, yalnızca başvuru ile yapılan bir çağrının tarafından tutulabilir `parallel_for_each`. Doku, GPU üzerinde Direct3D Doku nesneleri olarak saklanır. Dokular ve doku hücresi Direct3D'deki hakkında daha fazla bilgi için bkz: [Direct3D 11'de dokulara giriş](http://go.microsoft.com/fwlink/p/?linkid=248502).

Kullandığınız görüntü doku hücresi türü, grafik programlamada kullanılan pek çok doku biçiminden biri olabilir. Örneğin, RGBA biçimi, 32 bit 8 bit her R, G, B ve A skaler değer öğelerinin için kullanabilirsiniz. Grafik kartının doku donanımı, biçimi temel alarak tek tek öğelerine erişebilirsiniz. Örneğin, RGBA biçimi kullanıyorsanız, doku donanımı 8 bitlik her öğeyi bir 32 bitlik biçimde ayıklayabilir. C++ AMP'de, koddaki tek tek skaler öğelere bit kaydırma kullanmadan otomatik olarak erişebilir, böylece texel'inizin skaler öğe başına bit ayarlayabilirsiniz.

### <a name="instantiating-texture-objects"></a>Doku nesnelerini başlatma

Bir doku nesnesine atamadan bildirebilirsiniz. Aşağıdaki kod örneği, birkaç doku nesnesi bildirir.

```cpp
#include <amp.h>
#include <amp_graphics.h>
using namespace concurrency;
using namespace concurrency::graphics;

void declareTextures() {
    // Create a 16-texel texture of int.
    texture<int, 1> intTexture1(16);
    texture<int, 1> intTexture2(extent<1>(16));

    // Create a 16 x 32 texture of float_2.
    texture<float_2, 2> floatTexture1(16, 32);
    texture<float_2, 2> floatTexture2(extent<2>(16, 32));

    // Create a 2 x 4 x 8 texture of uint_4.
    texture<uint_4, 3> uintTexture1(2, 4, 8);
    texture<uint_4, 3> uintTexture2(extent<3>(2, 4, 8));
}
```

Bildirmek ve başlatmak için bir oluşturucu kullanabilirsiniz bir `texture` nesne. Aşağıdaki kod örnek bir `texture` nesneden oluşan bir vektörü `float_4` nesneleri. Skaler öğe başına bit varsayılan değere ayarlanır. Bu Oluşturucu ile kullanamazsınız `norm`, `unorm`, ya da kısa vektörleri `norm` ve `unorm`, skaler öğe başına varsayılan bit olmadığı için.

```cpp
#include <amp.h>
#include <amp_graphics.h>
#include <vector>
using namespace concurrency;
using namespace concurrency::graphics;

void initializeTexture() {
    std::vector<int_4> texels;
    for (int i = 0; i < 768 * 1024; i++) {
        int_4 i4(i, i, i, i);
        texels.push_back(i4);
    }

    texture<int_4, 2> aTexture(768, 1024, texels.begin(), texels.end());
}
```

Ayrıca bildirmek ve başlatmak bir `texture` kaynak verilerin, kaynak verilerin bayt cinsinden boyutunu ve skaler öğe başına bit bir işaretçi alan bir oluşturucu aşırı yüklemesini kullanarak nesne.

```cpp
void createTextureWithBPC() { // Create the source data.
    float source[1024* 2];
    for (int i = 0; i <1024* 2; i++) {
        source[i] = (float)i;
    }
    // Initialize the texture by using the size of source in bytes // and bits per scalar element.
    texture<float_2, 1> floatTexture(1024, source, (unsigned int)sizeof(source), 32U);
}
```

Bu örneklerdeki dokular varsayılan hızlandırıcının varsayılan görünümünde oluşturulur. Belirtmek isterseniz oluşturucunun diğer aşırı yüklemeler kullanabileceğiniz bir `accelerator_view` nesne. Bir CPU hızlandırıcısında bir doku nesnesi oluşturamazsınız.

Her boyutunun boyutuna sınırları vardır `texture` aşağıdaki tabloda gösterildiği gibi nesne. Sınırları aşarsanız, bir çalışma zamanı hatası oluşturulur.

|Doku|Boyut başına boyut sınırlaması|
|-------------|---------------------|
|Doku\<T, 1 >|16384|
|Doku\<T, 2 >|16384|
|Doku\<T, 3 >|2048|

### <a name="reading-from-texture-objects"></a>Doku nesnelerinden okuma

Okuma yapabilirsiniz bir `texture` kullanarak nesne [texture::operator\[\]](reference/texture-class.md#operator_at), [texture:: operator() işleci](reference/texture-class.md#operator_call), veya [texture::get metodu](reference/texture-class.md#get). İki işleç bir başvuru değil bir değer döndürür. Bu nedenle, yazamazsınız bir `texture` kullanarak nesne `texture::operator\[\]`.

```cpp
void readTexture() {
    std::vector<int_2> src;
    for (int i = 0; i <16 *32; i++) {
        int_2 i2(i, i);

        src.push_back(i2);
    }

    std::vector<int_2> dst(16* 32);

    array_view<int_2, 2> arr(16, 32, dst);

    arr.discard_data();

    const texture<int_2, 2> tex9(16, 32, src.begin(), src.end());

    parallel_for_each(tex9.extent, [=, &tex9] (index<2> idx) restrict(amp) { // Use the subscript operator.
        arr[idx].x += tex9[idx].x; // Use the function () operator.
        arr[idx].x += tex9(idx).x; // Use the get method.
        arr[idx].y += tex9.get(idx).y; // Use the function () operator.
        arr[idx].y += tex9(idx[0], idx[1]).y;
    });

    arr.synchronize();
}
```

Aşağıdaki kod örneği, doku kanallarının kısa bir vektörde depolamak ve ardından ayrı ayrı skaler öğelere kısa vektörün özellikleri olarak erişim gösterilmektedir.

```cpp
void UseBitsPerScalarElement() { // Create the image data. // Each unsigned int (32-bit) represents four 8-bit scalar elements(r,g,b,a values).
    const int image_height = 16;
    const int image_width = 16;
    std::vector<unsigned int> image(image_height* image_width);

    extent<2> image_extent(image_height, image_width);

    // By using uint_4 and 8 bits per channel, each 8-bit channel in the data source is // stored in one 32-bit component of a uint_4.
    texture<uint_4, 2> image_texture(image_extent, image.data(), image_extent.size()* 4U,  8U);

    // Use can access the RGBA values of the source data by using swizzling expressions of the uint_4.
    parallel_for_each(image_extent,
        [&image_texture](index<2> idx) restrict(amp)
        { // 4 bytes are automatically extracted when reading.
            uint_4 color = image_texture[idx];
            unsigned int r = color.r;
            unsigned int g = color.g;
            unsigned int b = color.b;
            unsigned int a = color.a;
        });
}
```

Aşağıdaki tabloda, her sıralama vektörü türü için kanal başına geçerli bit sayısını listeler.

|Doku veri türü|Skaler öğe başına geçerli bit|
|-----------------------|-----------------------------------|
|int, int_2, int_4<br /><br /> uint_2, uint_4 uint|8, 16, 32|
|int_3, uint_3|32|
|float, float_2, float_4|16, 32|
|float_3|32|
|çift double_2|64|
|Norm, norm_2, norm_4<br /><br /> unorm, unorm_2, unorm, 4|8, 16|

### <a name="writing-to-texture-objects"></a>Doku nesnelerine yazma

Kullanım [texture::set](reference/texture-class.md#set) yönteminin yazma `texture` nesneleri. Bir doku nesnesi salt okunur veya okunur/yazılır olabilir. Doku nesnesinin okunabilir ve yazılabilir olması aşağıdaki koşulların doğru olması gerekir:

- T, yalnızca bir skaler bileşene sahiptir. (Kısa vektörler kullanılamaz.)

- T değil **çift**, `norm`, veya `unorm`.

- `texture::bits_per_scalar_element` Özelliği 32'dir.

Üç true, değilse sonra `texture` salt okunur bir nesnedir. İlk iki koşul derleme sırasında denetlenir. Yazmaya çalışan kodunuz varsa, bir derleme hatası üretilir bir `readonly` doku nesnesi. Koşul için `texture::bits_per_scalar_element` çalışma zamanında algılanır ve çalışma zamanının oluşturduğu [unsupported_feature](../../parallel/amp/reference/unsupported-feature-class.md) salt okunur bir yazmaya çalışırsanız, özel durum `texture` nesne.

Aşağıdaki kod örneği bir doku nesnesine değerler yazar.

```cpp
void writeTexture() {
    texture<int, 1> tex1(16);

    parallel_for_each(tex1.extent, [&tex1] (index<1> idx) restrict(amp) {
        tex1.set(idx, 0);
    });
}
```

### <a name="copying-texture-objects"></a>Doku nesnelerini kopyalama

Kullanarak doku nesneleri arasında kopyalama [kopyalama](reference/concurrency-namespace-functions-amp.md#copy) işlevi veya [copy_async](reference/concurrency-namespace-functions-amp.md#copy_async) , aşağıdaki kod örneğinde gösterildiği gibi işlev.

```cpp
void copyHostArrayToTexture() { // Copy from source array to texture object by using the copy function.
    float floatSource[1024* 2];
    for (int i = 0; i <1024* 2; i++) {
        floatSource[i] = (float)i;
    }
    texture<float_2, 1> floatTexture(1024);

    copy(floatSource, (unsigned int)sizeof(floatSource), floatTexture);

    // Copy from source array to texture object by using the copy function.
    char charSource[16* 16];
    for (int i = 0; i <16* 16; i++) {
        charSource[i] = (char)i;
    }
    texture<int, 2> charTexture(16, 16, 8U);

    copy(charSource, (unsigned int)sizeof(charSource), charTexture);
    // Copy from texture object to source array by using the copy function.
    copy(charTexture, charSource, (unsigned int)sizeof(charSource));
}
```

Ayrıca bir dokudan diğerine kullanarak kopyalayabilirsiniz [texture::copy_to](reference/texture-class.md#copy_to) yöntemi. Bu iki doku, farklı Hızlandırıcı görünümlerinde olabilir. Kopyaladığınızda bir `writeonly_texture_view` nesne, temel alınan veri kopyalanır `texture` nesne. Skaler öğe ve kapsam başına bit kaynak ve hedef aynı olmalıdır `texture` nesneleri. Bu gereksinimler karşılanmazsa, çalışma zamanı özel durum oluşturur.

## <a name="texture-view-classes"></a>Doku görüntüleme sınıfları

C++ AMP tanıtır [texture_view sınıfı](../../parallel/amp/reference/texture-view-class.md) Visual Studio 2013'te. Doku görünümleri desteklemek için aynı doku hücresi türlerini ve derecelerini olarak [texture sınıfı](../../parallel/amp/reference/texture-class.md), ancak dokulardan farklı doku örnekleme ve Mipmap gibi ek donanım özelliklerine erişim sağlar. Doku görünümleri alttaki doku verilerine salt okunur, salt yazılır ve okunur-yazılır erişimi destekler.

- Salt okunur erişim sağlayan `texture_view<const T, N>` 1, 2 ya da 4 bileşenleri olan öğeler destekler, şablon uzmanlığı, doku örneklemesini ve dinamik erişim görünümün örneği oluşturulduğunda, belirlenen bir mipmap düzeylerinin bir dizi.

- Salt yazma erişimi özelleştirilmemiş Şablon sınıfı tarafından sağlanan `texture_view<T, N>`, 2 veya 4 bileşeni olan ve ne zaman görünümün örneği belirlenen bir mipmap düzeyine erişebildiklerinden öğeleri destekler. Örneklemeyi desteklemez.

- Okuma-yazma erişimi özelleştirilmemiş Şablon sınıfı tarafından sağlanan `texture_view<T, N>`, dokular gibi destekleyen yalnızca bir bileşene sahip öğeleri; görünüm, örneklemede belirlenen bir mipmap düzeyine erişebilirsiniz. Örneklemeyi desteklemez.

Doku görünümleri dizi görünümlerine benzer, ancak otomatik veri yönetimi ve hareket işlevselliğini sağlamaz [array_view sınıfı](../../parallel/amp/reference/array-view-class.md) sağlayan [array sınıfı](../../parallel/amp/reference/array-class.md). A `texture_view` yalnızca alttaki doku verisinin yer aldığı Hızlandırıcı görünümünde erişilebilir.

### <a name="writeonlytextureview-deprecated"></a>writeonly_texture_view kullanım dışı

Visual Studio 2013 için C++ AMP gibi örnekleme ve Mipmap, hangi tarafından desteklenemeyen donanımsal doku özellikleri için daha iyi destek sunar. [writeonly_texture_view sınıfı](../../parallel/amp/reference/writeonly-texture-view-class.md). Yeni çıkan `texture_view` işlevselliğin bir üst sınıf destekler `writeonly_texture_view`; sonuç olarak, `writeonly_texture_view` kullanım dışı bırakılmıştır.

Öneririz — en azından yeni kodda — kullandığınız `texture_view` önceden tarafından sağlanan erişim işlevselliği için `writeonly_texture_view`. İki bileşeni (int_2) olan bir doku nesnesine yazan aşağıdaki iki kod örnekleri karşılaştırın. Her iki durumda da, görünümü dikkat `wo_tv4`, lambda ifadesindeki değer tarafından yakalanması gerekir. İşte yeni kullanan örnek `texture_view` sınıfı:

```cpp
void write2ComponentTexture() {
    texture<int_2, 1> tex4(16);

    texture_view<int_2, 1> wo_tv4(tex4);

    parallel_for_each(extent<1>(16), [=] (index<1> idx) restrict(amp) {
        wo_tv4.set(idx, int_2(1, 1));
    });
}
```

Ve işte kullanım dışı `writeonly_texture_view` sınıfı:

```cpp
void write2ComponentTexture() {
    texture<int_2, 1> tex4(16);

    writeonly_texture_view<int_2, 1> wo_tv4(tex4);

    parallel_for_each(extent<1>(16), [=] (index<1> idx) restrict(amp) {
        wo_tv4.set(idx, int_2(1, 1));
    });
}
```

Gördüğünüz gibi birincil mipmap düzeyine tüm yaptığınız yazmak olduğunda iki kod örneği neredeyse aynıdır. Kullandıysanız `writeonly_texture_view` mevcut kodunuzu ve siz kodu, bunu değiştirmeniz gerekmez, geliştirmek planlamıyorsanız. Bu kodu öne çıkarmayı düşünüyorsanız, ancak kullanacak şekilde yeniden öneririz `texture_view` çünkü içindeki geliştirmeler yeni donanım doku özelliklerini desteklemektedir. Bu yeni özellikler hakkında daha fazla bilgi için okumaya devam edin.

Kullanımdan kaldırılması hakkında daha fazla bilgi için `writeonly_texture_view`, bkz: [C++ amp'de doku görünümü tasarımına genel bakış](http://blogs.msdn.com/b/nativeconcurrency/archive/2013/07/25/overview-of-the-texture-view-design-in-c-amp.aspx) paralel programlama yerel kod blog içinde.

### <a name="instantiating-texture-view-objects"></a>Doku görünüm nesnelerini başlatma

Bildirme bir `texture_view` bildirmek için benzer bir `array_view` ile ilişkili bir **dizi**. Aşağıdaki kod örneği birkaç bildirir `texture` nesneleri ve `texture_view` bunlarla ilişkili nesneleri.

```cpp
#include <amp.h>
#include <amp_graphics.h>
using namespace concurrency;
using namespace concurrency::graphics;

void declareTextureViews()
{
    // Create a 16-texel texture of int, with associated texture_views.
    texture<int, 1> intTexture(16);
    texture_view<const int, 1> intTextureViewRO(intTexture);  // read-only
    texture_view<int, 1> intTextureViewRW(intTexture);        // read-write

    // Create a 16 x 32 texture of float_2, with associated texture_views.
    texture<float_2, 2> floatTexture(16, 32);
    texture_view<const float_2, 2> floatTextureViewRO(floatTexture);  // read-only
    texture_view<float_2, 2> floatTextureViewRO(floatTexture);        // write-only

    // Create a 2 x 4 x 8 texture of uint_4, with associated texture_views.
    texture<uint_4, 3> uintTexture(2, 4, 8);
    texture_view<const uint_4, 3> uintTextureViewRO(uintTexture);  // read-only
    texture_view<uint_4, 3> uintTextureViewWO(uintTexture);        // write-only
}
```

Okuma-yazma nasıl bir doku görüntülemek, öğe türü sabit-olmayan olan ve bir bileşen içeren dikkat edin, ancak öğe türü sabit-olmayan olan ancak birden fazla bileşen içeren bir doku görünümü salt yazılır. Const öğesi türlerinin doku görünümleri her zaman salt okunurdur, ancak öğe türü sabit-olmayan olan olursa öğedeki bileşen sayısı okuma-yazma (1 Bileşen) olup olmadığını belirler veya salt yazılır (birden çok bileşen).

Öğe türü bir `texture_view`—, const-ness ve ayrıca bileşen sayısı — ayrıca görünümün doku örnekleme destekleyip desteklemediğini ve mipmap düzeylerine nasıl erişilebileceğini belirlemede bir rol oynar:

|Tür|Bileşenler|Oku|Write|Örnekleme|Mipmap erişimi|
|----------|----------------|----------|-----------|--------------|-------------------|
|texture_view\<const T, N >|1, 2, 4|Evet|Hayır (1)|Evet|Evet, dizini oluşturulabilir. Aralık, oluşturma sırasında belirlenir.|
|Texture_view\<T, N >|1.<br /><br /> 2, 4|Evet<br /><br /> Hayır (2)|Evet<br /><br /> Evet|Hayır (1)<br /><br /> Hayır (1)|Evet, bir düzey. Düzey, oluşturma sırasında belirlenir.<br /><br /> Evet, bir düzey. Düzey, oluşturma sırasında belirlenir.|

Bu tabloda, salt okunur doku görünümlerinin görünüme yükleyememeyle lisanslarınıza yeni yetenekleri tam destek görebilirsiniz. Yazılabilir doku görünümleri, yalnızca bir adet mipmap düzeyine erişebilirsiniz, sınırlıdır. Okuma-yazma doku görünümleri yazılabilir olanlardan çok daha fazla özelleştirilmiştir, çünkü bunlar doku görünümünün öğe türü yalnızca bir bileşene sahip olması gerekliliğini ekler. Okuma yönelik bir işlem olduğu için örnekleme yazılabilir doku görünümleri için desteklenmediğini unutmayın.

### <a name="reading-from-texture-view-objects"></a>Doku görünümü nesnelerinden okuma

Doku görünümleri değere göre yakalanan ise Dokuların başvuru tarafından yakalanması örneklenmemiş doku verilerin bir doku görünümü üzerinden okunması, dokunun kendisinden yalnızca okuma gibi olmasıdır. Aşağıdaki iki kod örneklerinde gösterilmektedir; ilk kullanarak `texture` yalnızca:

```cpp
void write2ComponentTexture() {
    texture<int_2, 1> text_data(16);

    parallel_for_each(extent<1>(16), [&] (index<1> idx) restrict(amp) {
        tex_data.set(idx, int_2(1, 1));
    });
}
```

Burada da aynı örneği artık kullanıyor hariç `texture_view` sınıfı:

```cpp
void write2ComponentTexture() {
    texture<int_2, 1> tex_data(16);

    texture_view<int_2, 1> tex_view(tex_data);

    parallel_for_each(extent<1>(16), [=] (index<1> idx) restrict(amp) {
        tex_view.set(idx, int_2(1, 1));
    });
}
```

Doku görünümleri öğeleri, kayan nokta türlerine dayanan dayalı — Örneğin, float, float_2 veya float_4 — ayrıca çeşitli donanım desteği avantajlarından yararlanmak için doku örnekleme kullanarak okuma filtreleme modları ve adresleme modları. C++ AMP, hesaplama senaryolarında en yaygın iki filtreleme modunu destekler; nokta filtreleme (en yakın komşu) ve doğrusal filtreleme (Ağırlıklı ortama) — ve dört adresleme modunu — kaydırılmış, yansıtılan, kenetlenen ve sınır. Adresleme modları hakkında daha fazla bilgi için bkz. [address_mode numaralandırması](reference/concurrency-graphics-namespace-enums.md#address_mode).

C++ AMP'nin doğrudan desteklediği modlara ek olarak, diğer filtreleme modlarına ve adresleme modlarına temel platform, doğrudan platformun API'leri kullanılarak oluşturulmuş bir doku örnekleyicisini benimsemek için Interop API'leri kullanarak erişebilirsiniz. Örneğin Direct3D anizotropik filtreleme gibi diğer filtreleme modlarını destekler ve bir dokunun her boyut için farklı bir adresleme modu uygulayabilir. Direct3D API'leri kullanılarak anizotropik filtreleme ile koordinatları dikey olarak sarılan, yatay olarak yansıtılan ve örneklenen bir doku örnekleyici oluşturabilir ve kullanarak bu örnekleyici C++ AMP kodunuzda yararlanarak `make_sampler` interop API'sini. Daha fazla bilgi için [C++ amp'de doku örnekleme](http://blogs.msdn.com/b/nativeconcurrency/archive/2013/07/18/texture-sampling-in-c-amp.aspx) paralel programlama yerel kod blog içinde.

Doku görünümleri ayrıca Mipmap okumayı da destekler. Salt okunur doku görünümlerinin örneklemede belirlenen bir dizi Orta-düzeylerini dinamik olarak örneklenebilir ve çünkü 1, 2 ya da 4 bileşenleri olan öğeler desteklenir (bir const öğe türüne sahip olanlar) en fazla esnekliği sunar. Bir bileşene sahip öğeleri olan okuma-yazma doku görünümleri ayrıca Mipmap, ancak yalnızca örneklemede belirlenen bir düzeyi destekler. Daha fazla bilgi için [mipmap'lar ile doku](http://blogs.msdn.com/b/nativeconcurrency/archive/2013/08/22/texture-with-mipmaps.aspx) paralel programlama yerel kod blog içinde.

### <a name="writing-to-texture-view-objects"></a>Doku görünüm nesnelerine yazma

Kullanım [texture_view::get metodu](reference/texture-view-class.md#get) temel alınan yazılacak `texture` aracılığıyla `texture_view` nesne. Bir doku görünümü salt okunur, salt okunur veya salt yazılır olabilir. Bir doku görünümünün yazılabilir olması sabit olmayan bir öğe türüne sahip olmalıdır; bir doku görünümü okunabilir ve yazılabilir olması öğe türünün ayrıca yalnızca bir bileşene sahip olmalıdır. Aksi halde doku görünümü salt okunurdur. Bir doku görünümü üzerinden bir anda yalnızca tek mipmap düzeyine erişebilirsiniz bir doku yapabilir ve görünümün örneği oluşturulduğunda düzey belirtilir.

Bu örnek, 4 mipmap düzeyi olan bir dokunun ikinci en ayrıntılı mipmap düzeyine yazma işlemi gösterilmektedir. En ayrıntılı mipmap düzeyi 0 düzeyidir.

```cpp
// Create a texture that has 4 mipmap levels : 16x16, 8x8, 4x4, 2x2
texture<int, 2> tex(extent<2>(16, 16), 16U, 4);

// Create a writable texture view to the second mipmap level :4x4
texture_view<int, 2> w_view(tex, 1);

parallel_for_each(w_view.extent, [=](index<2> idx) restrict(amp)
{
    w_view.set(idx, 123);
});
```

## <a name="interoperability"></a>Birlikte Çalışabilirlik

C++ AMP çalışma zamanı çalıştırılabilirliği Desteler `texture<T,1>` ve [ıd3d11texture1d arabirimi](http://go.microsoft.com/fwlink/p/?linkId=248503), arasında `texture<T,2>` ve [ıd3d11texture2d arabirimi](http://go.microsoft.com/fwlink/p/?linkId=255317), arasında `texture<T,3>`ve [ıd3d11texture3d arabirimi](http://go.microsoft.com/fwlink/p/?linkId=255377). [Get_texture](reference/concurrency-graphics-direct3d-namespace-functions.md#get_texture) yöntemi bir `texture` nesne ve döndürür bir `IUnknown` arabirimi. [Make_texture](reference/concurrency-graphics-direct3d-namespace-functions.md#make_texture) yöntemi bir `IUnknown` arabirimi ve `accelerator_view` nesne ve döndürür bir `texture` nesne.

## <a name="see-also"></a>Ayrıca Bkz.

[double_2 Sınıfı](../../parallel/amp/reference/double-2-class.md)<br/>
[double_3 Sınıfı](../../parallel/amp/reference/double-3-class.md)<br/>
[double_4 Sınıfı](../../parallel/amp/reference/double-4-class.md)<br/>
[float_2 Sınıfı](../../parallel/amp/reference/float-2-class.md)<br/>
[float_3 Sınıfı](../../parallel/amp/reference/float-3-class.md)<br/>
[float_4 Sınıfı](../../parallel/amp/reference/float-4-class.md)<br/>
[int_2 Sınıfı](../../parallel/amp/reference/int-2-class.md)<br/>
[int_3 Sınıfı](../../parallel/amp/reference/int-3-class.md)<br/>
[int_4 Sınıfı](../../parallel/amp/reference/int-4-class.md)<br/>
[norm_2 Sınıfı](../../parallel/amp/reference/norm-2-class.md)<br/>
[norm_3 Sınıfı](../../parallel/amp/reference/norm-3-class.md)<br/>
[norm_4 Sınıfı](../../parallel/amp/reference/norm-4-class.md)<br/>
[short_vector Yapısı](../../parallel/amp/reference/short-vector-structure.md)<br/>
[short_vector_traits Yapısı](../../parallel/amp/reference/short-vector-traits-structure.md)<br/>
[uint_2 Sınıfı](../../parallel/amp/reference/uint-2-class.md)<br/>
[uint_3 Sınıfı](../../parallel/amp/reference/uint-3-class.md)<br/>
[uint_4 Sınıfı](../../parallel/amp/reference/uint-4-class.md)<br/>
[unorm_2 Sınıfı](../../parallel/amp/reference/unorm-2-class.md)<br/>
[unorm_3 Sınıfı](../../parallel/amp/reference/unorm-3-class.md)<br/>
[unorm_4 Sınıfı](../../parallel/amp/reference/unorm-4-class.md)