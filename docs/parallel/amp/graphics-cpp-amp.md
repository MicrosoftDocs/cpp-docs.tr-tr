---
title: Grafikler (C++ AMP)
ms.date: 11/04/2016
ms.assetid: 190a98a4-5f7d-442e-866b-b374ca74c16f
ms.openlocfilehash: 97fd433387aac809053ea6dd8ac59a56207a4fc8
ms.sourcegitcommit: d77159732a8e782b2a1b7abea552065f2b6f61c1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2020
ms.locfileid: "93344728"
---
# <a name="graphics-c-amp"></a>Grafikler (C++ AMP)

C++ AMP, bir [concurrency:: Graphics](../../parallel/amp/reference/concurrency-graphics-namespace.md) ad alanında GPU 'lara doku desteğine erişmek için kullanabileceğiniz çeşitli API 'ler içerir. Bazı yaygın senaryolar şunlardır:

- [Doku](../../parallel/amp/reference/texture-class.md) sınıfını hesaplama için bir veri kapsayıcısı olarak kullanabilir ve doku ÖNBELLEĞININ ve GPU donanımının düzenlerindeki *uzamsal konum* açısından yararlanabilirsiniz. Uzamsal konum fiziksel olarak birbirlerine yakın olan veri öğelerinin özelliğidir.

- Çalışma zamanı, işlem dışı gölgelendiriciler ile verimli birlikte çalışabilirlik sağlar. Piksel, köşe, mozaik ve kabuk gölgelendiriciler sıklıkla C++ amp hesaplamalarında kullanabileceğiniz dokuları kullanır veya üretir.

- C++ AMP 'deki grafik API 'Leri, alt sözcük paketlenmiş arabelleklerine erişmenin alternatif yollarını sağlar. 8 bit veya 16 bit yapı karakterlerinden oluşan *biçimleri temsil eden* biçimlerin bulunduğu dokular, bu tür paketlenmiş veri depolamasına erişime izin verir.

## <a name="the-norm-and-unorm-types"></a>Norm ve unorm türleri

`norm`Ve `unorm` türleri, değer aralığını sınırlayan skaler türlerdir **`float`** ; Bu, *clamping* olarak bilinir. Bu türler, diğer skaler türlerden açık bir şekilde oluşturulabilir. Atama sırasında, değer ilk olarak öğesine ayarlanır **`float`** ve sonra norm [-1,0, 1,0] veya unorm [0,0, 1,0] tarafından izin verilen ilgili bölgeye çakışıyor. +/-Infinity atama +/-1 döndürür. NaN 'dan atama tanımsız. Bir norm, bir unorm 'den örtülü olarak oluşturulabilir ve veri kaybı olmaz. Kayan kapalı dönüştürme işleci bu türlerde tanımlanmıştır. İkili işleçler bu türler ve ve gibi diğer yerleşik skaler türler arasında tanımlanır **`float`** **`int`** : +,-, \* ,/, = =,! =, >, \<, > =, <=. Bileşik atama işleçleri de desteklenir: + =,-=, \* =,/=. Birli olumsuzlama işleci (-), norm türleri için tanımlanır.

## <a name="short-vector-library"></a>Kısa vektör kitaplığı

Kısa vektör kitaplığı, HLSL ' de tanımlı [vektör türünün](/windows/win32/direct3dhlsl/dx-graphics-hlsl-vector) bazı işlevlerini sağlar ve genellikle dokcası tanımlamak için kullanılır. Kısa bir vektör, aynı türde bir ile dört arasında değer tutan bir veri yapısıdır. Desteklenen türler,,,, ve ' dir **`double`** **`float`** **`int`** `norm` `uint` `unorm` . Tür adları aşağıdaki tabloda gösterilmiştir. Her tür için, adında alt çizgi olmayan karşılık gelen bir de vardır **`typedef`** . Alt çizgileri olan türler [concurrency:: Graphics ad uzayında](../../parallel/amp/reference/concurrency-graphics-namespace.md)bulunur. Alt çizgilere sahip olmayan türler, ve gibi benzer adlandırılmış temel türlerden açıkça ayrılmaları için [concurrency:: Graphics::d Irect3d ad alanında](../../parallel/amp/reference/concurrency-graphics-direct3d-namespace.md) yer alırlar **`__int8`** **`__int16`** .

|Tür|Uzunluk 2|Uzunluk 3|Uzunluk 4|
|-|--------------|--------------|--------------|
|double|double_2<br /><br /> double2|double_3<br /><br /> double3|double_4<br /><br /> double4|
|float|float_2<br /><br /> float2|float_3<br /><br /> float3|float_4<br /><br /> float4|
|int|int_2<br /><br /> int2|int_3<br /><br /> int3|int_4<br /><br /> int4|
|norm|norm_2<br /><br /> norm2|norm_3<br /><br /> norm3|norm_4<br /><br /> norm4|
|uint|uint_2<br /><br /> uint2|uint_3<br /><br /> uint3|uint_4<br /><br /> uint4|
|unorm|unorm_2<br /><br /> unorm2|unorm_3<br /><br /> unorm3|unorm_4<br /><br /> unorm4|

### <a name="operators"></a>İşleçler

İki kısa vektör arasında bir operatör tanımlanmışsa, kısa bir vektör ve skaler arasında da tanımlanır. Ayrıca, bunlardan biri doğru olmalıdır:

- Skaler türünün türü, kısa vektörün öğe türüyle aynı olmalıdır.

- Skalar öğenin türü, yalnızca bir Kullanıcı tanımlı dönüştürme kullanılarak vektörin öğe türüne örtük olarak dönüştürülebilir.

İşlem, kısa vektör ve skaler bileşenin her bileşeni arasında bileşen temelinde yürütülür. Geçerli işleçler şunlardır:

|İşleç türü|Geçerli türler|
|-------------------|-----------------|
|İkili işleçler|Tüm türlerde geçerlidir: +,-, \* ,/,<br /><br /> Tamsayı türlerinde geçerlidir:%, ^, &#124;, &, <\<, >><br /><br /> İki vektörün aynı boyutta olması gerekir ve sonuç aynı boyutta bir vektördür.|
|İlişkisel işleçler|Tüm türlerde geçerlidir: = = ve! =|
|Bileşik atama işleci|Tüm türlerde geçerlidir: + =,-=, \* =,/=<br /><br /> Tamsayı türlerinde geçerlidir:% =, ^ =, &#124;=, &=, <\<=, >>=|
|Artırma ve azaltma işleçleri|Tüm türlerde geçerlidir: + +,--<br /><br /> Önek ve sonek geçerlidir.|
|Bit düzeyinde NOT işleci (~)|Tamsayı türlerinde geçerlidir.|
|Birli işleci|Ve dışındaki tüm türlerde geçerlidir `unorm` `uint` .|

### <a name="swizzling-expressions"></a>Swizzling Ifadeleri

Kısa vektör kitaplığı, `vector_type.identifier` bir kısa vector bileşenine erişmek için erişimci yapısını destekler. `identifier` *Swizzling ifadesi* olarak bilinen, vector bileşenlerini belirtir. İfade bir l değeri veya r değeri olabilir. Tanımlayıcıdaki tek karakterler şu olabilir: x, y, z ve w; ya da r, g, b ve a. "x" ve "r", sıfır-bir bileşen anlamına gelir, "y" ve "g" ilk bileşen anlamına gelir ve bu şekilde devam eder. ("X" ve "r" nin aynı tanımlayıcıda kullanılamayacağını unutmayın.) Bu nedenle, "rgba" ve "xyzw" aynı sonucu döndürür. "X" ve "y" gibi tek bileşen erişimcileri skaler değer türleridir. Çoklu bileşen erişimcileri kısa vektör türlerdir. Örneğin, `int_4` adlı bir vektör oluşturursanız `fourInts` ve 2, 4, 6 ve 8 değerlerini içeriyorsa, `fourInts.y` 4 tamsayı ve `fourInts.rg` `int_2` 2 ve 4 değerlerini içeren bir nesne döndürür.

## <a name="texture-classes"></a>Doku sınıfları

Birçok GPU, pikselleri ve dokuları getirmek ve görüntüleri ve dokuları işlemek için optimize edilmiş donanım ve önbelleklerdir. Doku hücresi değerinin nesnelerine yönelik bir kapsayıcı sınıfı olan [doku \<T,N> ](../../parallel/amp/reference/texture-class.md) sınıfı, bu GPU 'ların doku işlevlerini gösterir. Bir doku hücresi değerinin şu olabilir:

- ,,,, **`int`** `uint` **`float`** **`double`** `norm` Veya `unorm` skaler.

- İki veya dört bileşeni olan kısa bir vektör. Tek özel durum `double_4` , buna izin verilmez.

`texture`Nesne, 1, 2 veya 3 derecesine sahip olabilir. `texture`Nesne yalnızca öğesine yapılan çağrının lambda öğesinde başvuruya göre yakalanamaz `parallel_for_each` . Doku, GPU 'da Direct3D doku nesneleri olarak depolanır. Direct3D 'de dokular ve dokun hakkında daha fazla bilgi için bkz. [Direct3D 11 ' de dokuya giriş](/windows/win32/direct3d11/overviews-direct3d-11-resources-textures-intro).

Kullandığınız doku hücresi değerinin türü, grafik programlamada kullanılan birçok doku biçiminden biri olabilir. Örneğin, bir RGBA biçimi, R, G, B ve skaler öğeler için 8 bit ile 32 bit kullanabilir. Grafik kartının doku donanımı, biçime göre ayrı ayrı öğelere erişebilir. Örneğin, RGBA biçimini kullanıyorsanız, doku donanımı her 8 bitlik öğeyi 32 bitlik bir biçimde ayıklayabilir. C++ amp ' de, doku hücresi değerinin 'nin skalar öğe başına bitlerini ayarlayabilirsiniz. böylece, bit kaydırma kullanmadan koddaki tek tek skalar öğelerine otomatik olarak erişebilirsiniz.

### <a name="instantiating-texture-objects"></a>Doku nesnelerini örnekleme

Bir doku nesnesini, başlatma olmadan bildirebilirsiniz. Aşağıdaki kod örneği, çeşitli doku nesnelerini bildirir.

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

Bir nesne bildirmek ve başlatmak için bir Oluşturucu da kullanabilirsiniz `texture` . Aşağıdaki kod örneği bir `texture` nesne vektöründen bir nesne oluşturur `float_4` . Skaler öğe başına bit sayısı varsayılan değer olarak ayarlanır. `norm` `unorm` `norm` `unorm` Skalar öğe başına varsayılan bir bit olmadığından, bu oluşturucuyu ve ' nin kısa vektörleriyle kullanamazsınız.

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

Ayrıca, `texture` kaynak verilere işaretçi alan bir Oluşturucu aşırı yüklemesi, bayt cinsinden kaynak verilerinin boyutu ve skaler öğe başına bit sayısı ile bir nesne bildirebilir ve başlatabilirsiniz.

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

Bu örneklerdeki dokular varsayılan hızlandırıcının varsayılan görünümünde oluşturulur. Bir nesne belirtmek istiyorsanız oluşturucunun diğer aşırı yüklerini kullanabilirsiniz `accelerator_view` . Bir CPU hızlandırıcısında doku nesnesi oluşturamazsınız.

`texture`Aşağıdaki tabloda gösterildiği gibi, her nesne boyutunun boyutu için sınırlar vardır. Sınırları aşarsanız bir çalışma zamanı hatası oluşturulur.

|Doku|Boyut başına boyut sınırlaması|
|-------------|---------------------|
|uyla\<T,1>|16384|
|uyla\<T,2>|16384|
|uyla\<T,3>|2048|

### <a name="reading-from-texture-objects"></a>Doku nesnelerinden okuma

`texture` [Doku:: \[ \] operator](reference/texture-class.md#operator_at), [doku:: operator () işleci](reference/texture-class.md#operator_call)veya [texture:: Get metodunu](reference/texture-class.md#get)kullanarak bir nesneden okuyabilirsiniz. İki işleç bir başvuru değil, bir değer döndürür. Bu nedenle, kullanarak bir nesnesine yazamaz `texture` `texture::operator\[\]` .

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

Aşağıdaki kod örneği, doku kanallarının kısa bir vektörde nasıl depolanacağını ve ardından tek tek skalar öğelerine kısa vektörün özellikleri olarak nasıl erişileceğini gösterir.

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

Aşağıdaki tabloda her bir sıralama vektör türü için kanal başına geçerli bitler listelenmektedir.

|Doku veri türü|Skaler öğe başına geçerli bit sayısı|
|-----------------------|-----------------------------------|
|int, int_2, int_4<br /><br /> uint, uint_2, uint_4|8, 16, 32|
|int_3, uint_3|32|
|kayan, float_2, float_4|16, 32|
|float_3|32|
|Double, double_2|64|
|Norm, norm_2, norm_4<br /><br /> unorm, unorm_2, unorm, 4|8, 16|

### <a name="writing-to-texture-objects"></a>Doku nesnelerine yazma

Nesnelere yazmak için [texture:: set](reference/texture-class.md#set) metodunu kullanın `texture` . Bir doku nesnesi salt okunur veya okuma/yazma olabilir. Bir doku nesnesinin okunabilir ve yazılabilir olması için aşağıdaki koşulların doğru olması gerekir:

- T 'in yalnızca bir skaler bileşeni vardır. (Kısa vektörlerine izin verilmez.)

- T **`double`** , `norm` , veya değildir `unorm` .

- `texture::bits_per_scalar_element`Özelliği 32 ' dir.

Üçü de doğru değilse, `texture` nesne salt okunur olur. İlk iki koşul derleme sırasında denetlenir. Bir doku nesnesine yazmaya çalışan kodunuz varsa derleme hatası oluşturulur `readonly` . İçin koşulu `texture::bits_per_scalar_element` çalışma zamanında algılanır ve salt okunur bir nesneye yazmaya çalışırsanız, çalışma zamanı [unsupported_feature](../../parallel/amp/reference/unsupported-feature-class.md) özel durumu oluşturur `texture` .

Aşağıdaki kod örneği bir doku nesnesine değerler yazar.

```cpp
void writeTexture() {
    texture<int, 1> tex1(16);

    parallel_for_each(tex1.extent, [&tex1] (index<1> idx) restrict(amp) {
        tex1.set(idx, 0);
    });
}
```

### <a name="copying-texture-objects"></a>Doku nesneleri kopyalanıyor

Aşağıdaki kod örneğinde gösterildiği gibi, [Copy](reference/concurrency-namespace-functions-amp.md#copy) işlevini veya [copy_async](reference/concurrency-namespace-functions-amp.md#copy_async) işlevini kullanarak doku nesneleri arasında kopyalama yapabilirsiniz.

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

Ayrıca, [doku:: copy_to](reference/texture-class.md#copy_to) yöntemini kullanarak bir dokusundaki diğerine kopyalayabilirsiniz. İki doku farklı accelerator_views olabilir. Bir `writeonly_texture_view` nesnesine kopyaladığınızda, veriler temel alınan `texture` nesneye kopyalanır. Skaler öğe başına bitlerin ve kapsamın kaynak ve hedef nesnelerde aynı olması gerekir `texture` . Bu gereksinimler karşılanmazsa, çalışma zamanı bir özel durum oluşturur.

## <a name="texture-view-classes"></a>Doku görünümü sınıfları

C++ AMP, Visual Studio 2013 [Texture_view sınıfını](../../parallel/amp/reference/texture-view-class.md) tanıtır. Doku görünümleri [doku sınıfı](../../parallel/amp/reference/texture-class.md)olarak aynı doku hücresi değerinin türlerini ve dereceleri destekler, ancak dokulardan farklı olarak doku örneklemesi ve mı haritaları gibi ek donanım özelliklerine erişim sağlar. Doku görünümleri, temel alınan doku verilerine salt okunurdur, salt yazılır ve okuma/yazma erişimini destekler.

- Salt okuma erişimi, `texture_view<const T, N>` 1, 2 veya 4 bileşeni, doku örneklemesi ve görünümün örneği oluşturulduğunda belirlenen bir dizi mipmap düzeyi olan öğeleri destekleyen şablon özelleştirmesi tarafından sağlanır.

- Salt yazılır erişim, `texture_view<T, N>` 2 veya 4 bileşeni olan öğeleri destekleyen ve görünümün örneği oluşturulduğunda belirlenen bir mipmap düzeyine erişebilen, özel olmayan şablon sınıfı tarafından sağlanır. Örneklemeyi desteklemez.

- Okuma-yazma erişimi, dokular gibi, yalnızca bir bileşeni olan öğeleri destekleyen, özelleştirilmiş olmayan şablon sınıfı tarafından sağlanır `texture_view<T, N>` ; Görünüm, örneklendiği zaman belirlenen bir mipmap düzeyine erişebilir. Örneklemeyi desteklemez.

Doku görünümleri dizi görünümlerine benzerdir, ancak [array_view sınıfının](../../parallel/amp/reference/array-view-class.md) [dizi sınıfı](../../parallel/amp/reference/array-class.md)üzerinde sağladığı otomatik veri yönetimi ve taşıma işlevlerini sağlamaz. `texture_view`Yalnızca, temel alınan doku verilerinin bulunduğu Hızlandırıcı görünümünde erişilebilir.

### <a name="writeonly_texture_view-deprecated"></a>writeonly_texture_view kullanım dışı

Visual Studio 2013 için, C++ AMP, [Writeonly_texture_view sınıfı](../../parallel/amp/reference/writeonly-texture-view-class.md)tarafından desteklenmeyen örnekleme ve mı haritaları gibi donanım doku özellikleri için daha iyi destek sunuyor. Yeni tanıtılan `texture_view` sınıf, içinde işlevselliğin bir üst kümesini destekler `writeonly_texture_view` ; Sonuç olarak `writeonly_texture_view` kullanım dışıdır.

Daha `texture_view` önce tarafından sağlanmış işlevlere erişmek için kullandığınız en az yeni kod için önerilir `writeonly_texture_view` . İki bileşeni olan bir doku nesnesine yazan aşağıdaki iki kod örneğini karşılaştırın (int_2). Her iki durumda da görünüm, `wo_tv4` lambda ifadesindeki değere göre yakalanmalıdır. Yeni sınıfını kullanan örnek aşağıda verilmiştir `texture_view` :

```cpp
void write2ComponentTexture() {
    texture<int_2, 1> tex4(16);

    texture_view<int_2, 1> wo_tv4(tex4);

    parallel_for_each(extent<1>(16), [=] (index<1> idx) restrict(amp) {
        wo_tv4.set(idx, int_2(1, 1));
    });
}
```

Kullanım dışı bırakılan sınıfı aşağıda verilmiştir `writeonly_texture_view` :

```cpp
void write2ComponentTexture() {
    texture<int_2, 1> tex4(16);

    writeonly_texture_view<int_2, 1> wo_tv4(tex4);

    parallel_for_each(extent<1>(16), [=] (index<1> idx) restrict(amp) {
        wo_tv4.set(idx, int_2(1, 1));
    });
}
```

Gördüğünüz gibi, her şey birincil mipmap düzeyine yazarken iki kod örneği neredeyse aynı olur. `writeonly_texture_view`Varolan kodda kullandıysanız ve bu kodu geliştirmeyi planlanmıyorsanız, bunu değiştirmeniz gerekmez. Bununla birlikte, bu kodu ileri doğru yapmayı düşünüyorsanız, bu bilgileri kullanmak üzere yeniden yazmanız önerilir `texture_view` çünkü bu, içindeki geliştirmeler yeni donanım dokusu özelliklerini destekliyor. Bu yeni yetenekler hakkında daha fazla bilgi için okumaya devam edin.

Kullanımdan kaldırılması hakkında daha fazla bilgi için `writeonly_texture_view` bkz. yerel kod blogu 'Nda paralel programlamada [C++ amp doku görünümü tasarımına genel bakış](/archive/blogs/nativeconcurrency/overview-of-the-texture-view-design-in-c-amp) .

### <a name="instantiating-texture-view-objects"></a>Doku görünümü nesnelerini örnekleme

Bildirim `texture_view` , bir `array_view` **dizi** ile ilişkilendirilmiş bir bildirmek için benzerdir. Aşağıdaki kod örneği, çeşitli `texture` nesneleri ve `texture_view` bunlarla ilişkili nesneleri bildirir.

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

Öğe türü const olmayan ve bir bileşen okuma-yazma olan bir doku görünümünün, ancak öğe türü const olmayan ancak birden fazla componente olan bir doku görünümünün salt yazılır olduğunu fark edebilirsiniz. Const öğe türlerinin doku görünümleri her zaman salt okunurdur, ancak öğe türü const değilse, öğedeki bileşen sayısı, okuma/yazma (1 bileşen) veya salt yazılır (birden çok bileşen) olup olmadığını belirler.

Öğesinin `texture_view` sabit düzeyi ve ayrıca sahip olduğu bileşen sayısı gibi öğe türü, ayrıca görünümün doku örneklemesi destekleyip desteklemediğini ve mipmap düzeylerine nasıl erişilebileceğini belirlemede bir rol oynar:

|Tür|Bileşenler|Okuma|Yazma|Örnekleme|Mipmap erişimi|
|----------|----------------|----------|-----------|--------------|-------------------|
|texture_view\<const T, N>|1, 2, 4|Evet|Hayır (1)|Evet|Evet, dizinlenebilir. Aralık, örnekleme sırasında belirlenir.|
|Texture_view\<T, N>|1<br /><br /> 2, 4|Evet<br /><br /> Hayır (2)|Evet<br /><br /> Evet|Hayır (1)<br /><br /> Hayır (1)|Evet, tek düzey. Düzey, örnekleme sırasında belirlenir.<br /><br /> Evet, tek düzey. Düzey, örnekleme sırasında belirlenir.|

Bu tablodan, salt okuma dokusu görünümlerinin, görünüme yazamayacak şekilde, Exchange 'deki yeni özellikleri tam olarak desteklediğini görebilirsiniz. Yazılabilir doku görünümleri yalnızca bir mipmap düzeyine erişebilmeleri için sınırlıdır. Okuma-yazma doku görünümleri, yazılabilir olanlardan daha da özelleştirilmiştir, çünkü doku görünümünün öğe türünün yalnızca bir bileşeni olduğu gereksinimi ekler. Bir okuma yönelimli işlem olduğundan, bu örnekleme yazılabilir doku görünümleri için desteklenmediğine dikkat edin.

### <a name="reading-from-texture-view-objects"></a>Doku görünümü nesnelerinden okuma

Örnek olmayan doku verilerinin bir doku görünümü aracılığıyla okunması tıpkı dokuların başvuruya göre yakalanması, ancak doku görünümlerinin değere göre yakalanmasının dışında. Aşağıdaki iki kod örneği gösterilmektedir; İlk olarak, `texture` yalnızca kullanarak:

```cpp
void write2ComponentTexture() {
    texture<int_2, 1> text_data(16);

    parallel_for_each(extent<1>(16), [&] (index<1> idx) restrict(amp) {
        tex_data.set(idx, int_2(1, 1));
    });
}
```

Aynı örnek, artık sınıfı kullandığından de aynıdır `texture_view` :

```cpp
void write2ComponentTexture() {
    texture<int_2, 1> tex_data(16);

    texture_view<int_2, 1> tex_view(tex_data);

    parallel_for_each(extent<1>(16), [=] (index<1> idx) restrict(amp) {
        tex_view.set(idx, int_2(1, 1));
    });
}
```

Öğeleri kayan nokta türlerini temel alan doku görünümleri — Örneğin, float, float_2 veya float_4 — çeşitli filtreleme modları ve adresleme modları için donanım desteğinden yararlanmak üzere doku örnekleme kullanılarak da okunabilir. C++ AMP, işlem senaryolarında en yaygın olarak kullanılan iki filtreleme modunu destekler: nokta filtreleme (en yakın komşu) ve doğrusal filtreleme (ağırlıklı ortalama) — ve dört adresleme modu — kaydırılmış, yansıtmalı, clamış ve Border. Adresleme modları hakkında daha fazla bilgi için bkz. [Address_mode numaralandırması](reference/concurrency-graphics-namespace-enums.md#address_mode).

C++ AMP doğrudan desteklediği modlara ek olarak, doğrudan platform API 'Leri kullanılarak oluşturulan bir doku örnekleyiciyi benimsemek için birlikte çalışma API 'Lerini kullanarak temel platformun diğer filtreleme modlarına ve adresleme modlarına erişebilirsiniz. Örneğin Direct3D, anısotropıc filtresi gibi diğer filtreleme modlarını destekler ve her bir dokunun boyutuna farklı bir adresleme modu uygulayabilir. Koordinatları dikey olarak sarılanmış, yatay olarak yansıtılmış ve Direct3D API 'Leri kullanılarak anısotropıc filtrelemesinde örneklendiği bir doku örnekleyici oluşturabilirsiniz ve ardından birlikte çalışma API 'sini kullanarak C++ AMP kodunuzda örnekleyiciyi kullanın `make_sampler` . Daha fazla bilgi için yerel kod blogundan paralel programlamada [C++ amp Içindeki doku örneklemesi](/archive/blogs/nativeconcurrency/texture-sampling-in-c-amp) ' ne bakın.

Doku görünümleri Ayrıca, MIN haritaları okumayı destekler. Salt yazılır doku görünümleri (const öğe türüne sahip olanlar), dinamik olarak örneklenebilir ve 1, 2 veya 4 bileşeni olan öğeler desteklendiğinden, en çok esnekliği sunar. Tek bir bileşeni olan öğeleri olan okuma-yazma doku görünümleri, yalnızca örnek oluşturma sırasında belirlenen bir düzeyde olan çok boyutlu haritaları destekler. Daha fazla bilgi için bkz. yerel kod blogundan paralel programlamada, mı [haritaları Ile doku](/archive/blogs/nativeconcurrency/texture-with-mipmaps) .

### <a name="writing-to-texture-view-objects"></a>Doku görünümü nesnelerine yazma

Nesne aracılığıyla temeldeki öğesine yazmak için [texture_view:: Get metodunu](reference/texture-view-class.md#get) kullanın `texture` `texture_view` . Doku görünümü salt okunurdur, salt okunurdur veya salt yazılır olabilir. Bir doku görünümünün yazılabilir olması için, const olmayan bir öğe türüne sahip olmalıdır; bir doku görünümünün okunabilir ve yazılabilir olması için, öğe türünün de yalnızca bir bileşeni olmalıdır. Aksi halde doku görünümü salt okunurdur. Bir dokusunun tek seferde bir mipmap düzeyine bir doku görünümü ile erişebilirsiniz ve görünüm örneği oluşturulduğunda düzey belirtilir.

Bu örnek, 4 mipmap düzeyine sahip bir dokunun ikinci en ayrıntılı mipmap düzeyine nasıl yazılacağını gösterir. En ayrıntılı mipmap düzeyi düzey 0 ' dır.

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

## <a name="interoperability"></a>Birlikte çalışabilirlik

C++ AMP çalışma zamanı `texture<T,1>` Ile [ID3D11Texture1D arabirimi](/windows/win32/api/d3d11/nn-d3d11-id3d11texture1d)arasında birlikte çalışabilirliği destekler, `texture<T,2>` ile [ID3D11Texture2D arabirimi](/windows/win32/api/d3d11/nn-d3d11-id3d11texture2d)arasında ve ile `texture<T,3>` [ID3D11Texture3D arabirimi](/windows/win32/api/d3d11/nn-d3d11-id3d11texture3d)arasında. [Get_texture](reference/concurrency-graphics-direct3d-namespace-functions.md#get_texture) yöntemi bir nesnesi alır `texture` ve bir arabirim döndürür `IUnknown` . [Make_texture](reference/concurrency-graphics-direct3d-namespace-functions.md#make_texture) yöntemi bir `IUnknown` arabirim ve bir nesnesi alır `accelerator_view` ve bir nesne döndürür `texture` .

## <a name="see-also"></a>Ayrıca bkz.

[double_2 Sınıfı](../../parallel/amp/reference/double-2-class.md)<br/>
[double_3 sınıfı](../../parallel/amp/reference/double-3-class.md)<br/>
[double_4 sınıfı](../../parallel/amp/reference/double-4-class.md)<br/>
[float_2 sınıfı](../../parallel/amp/reference/float-2-class.md)<br/>
[float_3 sınıfı](../../parallel/amp/reference/float-3-class.md)<br/>
[float_4 sınıfı](../../parallel/amp/reference/float-4-class.md)<br/>
[int_2 sınıfı](../../parallel/amp/reference/int-2-class.md)<br/>
[int_3 Sınıfı](../../parallel/amp/reference/int-3-class.md)<br/>
[int_4 sınıfı](../../parallel/amp/reference/int-4-class.md)<br/>
[norm_2 sınıfı](../../parallel/amp/reference/norm-2-class.md)<br/>
[norm_3 sınıfı](../../parallel/amp/reference/norm-3-class.md)<br/>
[norm_4 sınıfı](../../parallel/amp/reference/norm-4-class.md)<br/>
[short_vector Yapısı](../../parallel/amp/reference/short-vector-structure.md)<br/>
[short_vector_traits Yapısı](../../parallel/amp/reference/short-vector-traits-structure.md)<br/>
[uint_2 sınıfı](../../parallel/amp/reference/uint-2-class.md)<br/>
[uint_3 sınıfı](../../parallel/amp/reference/uint-3-class.md)<br/>
[uint_4 sınıfı](../../parallel/amp/reference/uint-4-class.md)<br/>
[unorm_2 sınıfı](../../parallel/amp/reference/unorm-2-class.md)<br/>
[unorm_3 sınıfı](../../parallel/amp/reference/unorm-3-class.md)<br/>
[unorm_4 Sınıfı](../../parallel/amp/reference/unorm-4-class.md)
