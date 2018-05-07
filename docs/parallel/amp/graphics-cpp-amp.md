---
title: Grafikler (C++ AMP) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
ms.assetid: 190a98a4-5f7d-442e-866b-b374ca74c16f
caps.latest.revision: 27
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c187ebc4eeb3917ce01e63c6c0769ffa0a570368
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="graphics-c-amp"></a>Grafikler (C++ AMP)
C++ AMP içeren birkaç API'leri [Concurrency::graphics](../../parallel/amp/reference/concurrency-graphics-namespace.md) GPU doku desteğini erişmek için kullanabileceği bir ad alanı. Bazı genel senaryolar şunlardır:  
  
-   Kullanabileceğiniz [doku](../../parallel/amp/reference/texture-class.md) sınıfı hesaplama ve yararlanma veri kapsayıcısı olarak *uzamsal yere göre* doku önbellek ve düzenleri GPU donanım. Uzamsal yere göre fiziksel olarak diğer yakın olan veri öğeleri özelliğidir.  
  
-   Çalışma zamanı işlem dışı gölgelendiriciler ile verimli çalışmasını sağlar. Piksel, köşe, Mozaik döşeme ve hull gölgelendiriciler sık kullanmak veya C++ AMP hesaplamalarında kullanabilirsiniz dokuları üretir.  
  
-   C++ AMP API'leri grafik erişmek için alternatif yol paketlenmiş arabellekleri alt word sağlar. Sahip dokuları biçimleri temsil eden *texels* (doku öğeleri) 8 bit sürümünün oluşur veya 16 bit skalerler böyle paketlenmiş veri depolama alanına erişim izni.  
  
## <a name="the-norm-and-unorm-types"></a>Norm ve unorm türleri  
 `norm` Ve `unorm` türleridir aralığını sınırla skaler türler `float` değerleri; bu olarak bilinir *clamping*. Bu tür, skaler diğer türlerinden açıkça oluşturulabilir. Atama, değerin ilk için dönüştürüldüğüne `float` ve norm [-1.0, 1.0] veya [0.0, 1.0] unorm tarafından izin verilen ilgili bölgeye clamped. Tür atama sonsuz +/-+/-1 döndürür. NaN gelen atama tanımlanmamıştır. Unorm bir norm örtük olarak oluşturulmuş olabilir ve hiçbir veri kaybı yok. Float için örtük dönüşüm işleci bu türlerinde tanımlanır. İkili işleçler tanımlanmış bu türleri ve diğer yerleşik skaler türler arasında gibi `float` ve `int`: +, -, *, /, ==,! =, >, \<, > =, < =. Bileşik atama işleçleri de desteklenir: +=,-=, \*= / =. Tekli değilleme işleci (-) norm türleri için tanımlanır.  
  
## <a name="short-vector-library"></a>Kısa vektör kitaplığı  
 Kısa vektör kitaplığı bazı işlevselliğini sağlar [vektör türü](http://go.microsoft.com/fwlink/p/?linkid=248500) HLSL içinde tanımlanmıştır ve genellikle texels tanımlamak için kullanılır. Kısa bir vektör aynı türde birden dörde kadar değerleri içeren bir veri yapısıdır. Desteklenen türler `double`, `float`, `int`, `norm`, `uint`, ve `unorm`. Tür adları aşağıdaki tabloda gösterilmektedir. Her tür için yoktur ayrıca karşılık gelen `typedef` , alt çizgi adına sahip değil. Alt çizgi olan türlerini bulunan [Concurrency::graphics Namespace](../../parallel/amp/reference/concurrency-graphics-namespace.md). Alt çizgi yok türleri bulunan [CONCURRENCY::Graphics:: Direct3D Namespace](../../parallel/amp/reference/concurrency-graphics-direct3d-namespace.md) böylece bunlar açıkça benzer adlandırılmış temel türlerinden gibi ayrılmış `__int8` ve `__int16`.  
  
||Uzunluğu 2|Uzunluğu 3|Uzunluk 4|  
|-|--------------|--------------|--------------|  
|çift|double_2<br /><br /> double2|double_3<br /><br /> double3|double_4<br /><br /> double4|  
|float|float_2<br /><br /> float2|float_3<br /><br /> float3|float_4<br /><br /> float4|  
|int|int_2<br /><br /> int2|int_3<br /><br /> int3|int_4<br /><br /> int4|  
|norm|norm_2<br /><br /> norm2|norm_3<br /><br /> norm3|norm_4<br /><br /> norm4|  
|uint|uint_2<br /><br /> uint2|uint_3<br /><br /> uint3|uint_4<br /><br /> uint4|  
|unorm|unorm_2<br /><br /> unorm2|unorm_3<br /><br /> unorm3|unorm_4<br /><br /> unorm4|  
  
### <a name="operators"></a>İşleçler  
 Bir işleç arasında iki kısa vektör tanımlanırsa, ardından bunu ayrıca kısa vektörü ile bir skaler arasında tanımlanır. Ayrıca, bunlardan biri doğru olmalıdır:  
  
-   Skaler 's türü kısa vector öğesinin öğe türü ile aynı olması gerekir.  
  
-   Skaler 's türü örtük olarak yalnızca bir kullanıcı tarafından tanımlanan dönüştürme kullanarak vector öğesinin öğesi türüne dönüştürülebilir.  
  
 İşlemi component-wise kısa vektör alanının her bileşeni ile skaler arasında taşınır. Geçerli işleçler şunlardır:  
  
|İşleç türü|Geçerli türler|  
|-------------------|-----------------|  
|İkili işleçler|Geçerli tüm türler: +, -, *, /,<br /><br /> Geçerli tamsayı türleri üzerinde: % ^, &#124;&, <\<, >><br /><br /> İki vektörü aynı boyutta olması gerekir ve aynı boyutta bir vektör sonucudur.|  
|İlişkisel işleçler|Geçerli tüm türler: == ve! =|  
|Bileşik atama işleci|Geçerli tüm türler: +=,-=, * = / =<br /><br /> Geçerli tamsayı türleri üzerinde: % = ^ = &#124;= & =, <\<= >> =|  
|Artırma ve azaltma işleçleri|Geçerli tüm türler: ++,--<br /><br /> Önek ve sonek geçerlidir.|  
|Bitwise NOT işleci (~)|Tamsayı türleri geçerlidir.|  
|Birli - işleci|Geçerli dışında tüm türler `unorm` ve `uint`.|  
  
### <a name="swizzling-expressions"></a>Swizzling ifadeleri  
 Kısa vektör kitaplığı destekleyen `vector_type.identifier` kısa vektör bileşenlerine erişmek için erişimci yapısı. `identifier`, Olarak bilinen bir *swizzling ifade*, vektör bileşenlerini belirtir. İfade bir l-değeri veya bir r olabilir. Tanımlayıcı tek tek karakter olabilir: x, y, z ve w; veya r, g, b ve a. "x" ve "r" sıfır th bileşeni, "y" ve "g" ortalama ilk bileşen ve benzeri anlamına gelir. (Uyarı, "x" ve "r" aynı tanımlayıcıda kullanılamaz.) Bu nedenle, "rgba" ve "xyzw" aynı sonucu verir. "X" gibi tek bileşen erişimciler ve "y" skaler değer türleri. Birden çok bileşen erişimciler kısa vektör türleridir. Örneğin, oluşturmak, bir `int_4` adlı vektör `fourInts` ve değer 2, 4, 6 ve 8, ardından `fourInts.y` 4 tamsayıyı döndürür ve `fourInts.rg` döndürür bir `int_2` 2 ve 4 değerleri içeren nesne.  
  
## <a name="texture-classes"></a>Doku sınıfları  
 Birçok GPU donanım ve piksel ve texels getirmek ve görüntüler ve dokular işlemek için optimize önbellekleri sahiptir. [Doku\<T, N >](../../parallel/amp/reference/texture-class.md) texel nesneleri için bir kapsayıcı sınıf olan sınıf bu GPU doku işlevselliğini kullanıma sunar. Bir texel olabilir:  
  
-   Bir `int`, `uint`, `float`, `double`, `norm`, veya `unorm` skaler.  
  
-   İki veya dört bileşenlere sahip kısa vektörü. Tek özel durum `double_4`, izin verilmeyen.  
  
 `texture` Nesnesi, 1, 2 veya 3 derecesini olabilir. `texture` Nesne yakalanıp yalnızca bir çağrı lambda başvuruya göre `parallel_for_each`. Doku GPU üzerinde Direct3D Doku nesneler olarak depolanır. Dokular ve Direct3D texels hakkında daha fazla bilgi için bkz: [Direct3D 11 dokular giriş](http://go.microsoft.com/fwlink/p/?linkid=248502).  
  
 Kullandığınız texel türünün grafik programlamaya kullanılan birçok doku biçimlerden birinde olabilir. Örneğin, bir RGBA biçimi 32 bit, 8 bit her R, G, B ve skaler öğeleri için kullanabilirsiniz. Grafik kartının doku donanım biçimine bağlı ayrı ayrı öğeler erişebilir. Örneğin, doku donanım RGBA biçimi kullanıyorsanız, her 8 bit öğesi 32-bit forma ayıklayabilirsiniz. Bit kaydırma kullanmadan otomatik olarak ayrı ayrı skaler öğeler kodda erişebilmeniz, C++ AMP içinde texel skaler öğesi başına bit ayarlayabilirsiniz.  
  
### <a name="instantiating-texture-objects"></a>Örnek oluşturma doku nesneleri  
 Bir doku nesnesi başlatma olmadan bildirebilirsiniz. Aşağıdaki kod örneğinde birkaç doku nesneleri bildirir.  
  
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
  
 Bildirme ve başlatmak için de bir oluşturucu kullanabilirsiniz bir `texture` nesnesi. Aşağıdaki kod örneği başlatır bir `texture` bir vektör nesnesinden `float_4` nesneleri. BITS skaler öğesi başına varsayılan olarak ayarlanır. Bu oluşturucu kullanamazsınız `norm`, `unorm`, ya da kısa vektörlerinin `norm` ve `unorm`, BITS varsayılan skaler öğesi başına olmadığı için.  
  
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
  
 Ayrıca bildirme ve başlatmak bir `texture` veri kaynağını, kaynak veri bayt cinsinden boyutu ve BITS skaler öğe başına bir işaretçi kopyalayan bir oluşturucu aşırı kullanarak nesne.  
  
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
  
 Bu örneklerde dokuları varsayılan Hızlandırıcı varsayılan görünümünü oluşturulur. Belirtmek istiyorsanız diğer aşırı yüklemeler oluşturucusunun kullanabileceğiniz bir `accelerator_view` nesnesi. Bir CPU Hızlandırıcı bir doku nesnesi oluşturulamıyor.  
  
 Her boyut boyutunu sınırları vardır `texture` aşağıdaki tabloda gösterildiği gibi nesne. Sınırı aşarsanız çalışma zamanı hatası oluşur.  
  
|Doku|Boyut başına boyutu sınırlaması|  
|-------------|---------------------|  
|Doku\<T, 1 >|16384|  
|Doku\<T, 2 >|16384|  
|Doku\<T, 2 >|2048|  
  
### <a name="reading-from-texture-objects"></a>Doku nesnelerinden okuma  
 Bilgi edinebilirsiniz bir `texture` kullanarak nesne [texture::operator\[\]](reference/texture-class.md#operator_at), [texture:: operator() işleci](reference/texture-class.md#operator_call), veya [texture::getyöntemi](reference/texture-class.md#get). İki işleç bir değer, bir başvuru döndürür. Bu nedenle, yazamaz bir `texture` kullanarak nesne `texture::operator\[\]`.  
  
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
  
 Aşağıdaki kod örneğinde, doku kanalları kısa bir Vector ve daha sonra ayrı ayrı skaler öğeler erişim kısa vektör özellikleri gösterilmiştir.  
  
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
  
 Aşağıdaki tabloda her sıralama vektör türü için kanal başına geçerli BITS listeler.  
  
|Doku veri türü|Skaler öğesi başına geçerli BITS|  
|-----------------------|-----------------------------------|  
|int, int_2, int_4<br /><br /> uint, uint_2, uint_4|8, 16, 32|  
|int_3, uint_3|32|  
|float, float_2, float_4|16, 32|  
|float_3|32|  
|Double, double_2|64|  
|Norm, norm_2, norm_4<br /><br /> unorm, unorm_2, unorm, 4|8, 16|  
  
### <a name="writing-to-texture-objects"></a>Doku nesnelere yazma  
 Kullanım [texture::set](reference/texture-class.md#set) yazmak için yöntemi `texture` nesneleri. Bir doku nesnesi salt okunur veya okuma/yazma olabilir. Bir doku nesnesi okunabilir ve yazılabilir olması aşağıdaki koşulların doğru olması gerekir:  

  
-   T yalnızca bir skaler bileşeni vardır. (Kısa vektörlerinin izin verilmez.)  
  
-   T değil `double`, `norm`, veya `unorm`.  
  
-   `texture::bits_per_scalar_element` 32 bir özelliktir.  
  
 Üç true, değilse sonra `texture` salt okunur bir nesnedir. İlk iki koşullar derleme sırasında denetlenir. Yazma girişiminde kodu varsa, bir derleme hatası oluşturulan bir `readonly` doku nesnesi. Koşul için `texture::bits_per_scalar_element` çalışma zamanında algılanır ve çalışma zamanı oluşturur [unsupported_feature](../../parallel/amp/reference/unsupported-feature-class.md) için salt okunur yazma çalışırsanız, özel durum `texture` nesnesi.  
  
 Aşağıdaki kod örneğinde bir doku nesnesine değerlerini yazar.  
  
```cpp  
void writeTexture() {  
    texture<int, 1> tex1(16);

    parallel_for_each(tex1.extent, [&tex1] (index<1> idx) restrict(amp) {      
    tex1.set(idx, 0);

 });

 
}  
 
```  
  
### <a name="copying-texture-objects"></a>Doku nesneleri kopyalama  
 Kullanarak doku nesneleri arasında kopyalayabilirsiniz [kopya](reference/concurrency-namespace-functions-amp.md#copy) işlevi veya [copy_async](reference/concurrency-namespace-functions-amp.md#copy_async) , aşağıdaki kod örneğinde gösterildiği gibi işlev.  
  
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
  
 Ayrıca bir doku diğerine kullanarak kopyalayabilirsiniz [texture::copy_to](reference/texture-class.md#copy_to) yöntemi. İki dokular üzerinde farklı accelerator_views olabilir. Ne zaman kopyalamak için bir `writeonly_texture_view` nesnesi, veri arka plandaki için kopyalanır `texture` nesnesi. Skaler öğesi ve uzantı başına bit kaynak ve hedef aynı olmalıdır `texture` nesneleri. Bu gereksinimler karşılanmazsa, çalışma zamanı özel durum oluşturur.  

  
## <a name="texture-view-classes"></a>Doku görünüm sınıfları  
 C++ AMP tanıtır [texture_view sınıfı](../../parallel/amp/reference/texture-view-class.md) içinde [!INCLUDE[vs_dev12](../../atl-mfc-shared/includes/vs_dev12_md.md)]. Doku görünümleri desteklemek aynı texel türleri ve sıralar olarak [texture sınıfı](../../parallel/amp/reference/texture-class.md), ancak doku farklı olarak, ek donanım özellikleri doku örnekleme ve mipmaps gibi erişim sağlar. Doku görünümleri temel doku verilere salt okunur, yalnızca yazma ve okuma-yazma erişimi destekler.  
  
-   Salt okunur erişim sağlayan `texture_view<const T, N>` 1, 2 veya 4 bileşenleri yüklü öğeleri destekler, şablon uzmanlık doku görünümün örneği oluşturulduğunda belirlenir mipmap düzeyleri çeşitli örnekleme ve dinamik erişim.  
  
-   Salt yazılır erişimi özel olmayan Şablon sınıfı tarafından sağlanan `texture_view<T, N>`, 2 veya 4 bileşenleri ve ne zaman görünümün örneği belirledi bir mipmap düzey erişebilirsiniz öğeleri destekler. Örnekleme desteklemez.  
  
-   Okuma-yazma erişimi özel olmayan Şablon sınıfı tarafından sağlanan `texture_view<T, N>`, hangi dokular gibi destekler yalnızca bir bileşen olan öğenin; görünüm zaman örneği belirledi bir mipmap düzey erişebilirsiniz. Örnekleme desteklemez.  
  
 Doku görünümleri dizi görünümlerine benzer, ancak otomatik veri yönetimi ve hareket işlevselliği, sağlamaz [array_view sınıfı](../../parallel/amp/reference/array-view-class.md) üzerinden sağlayan [array sınıfı](../../parallel/amp/reference/array-class.md). A `texture_view` yalnızca temel alınan doku verilerin bulunduğu Hızlandırıcı görünümde erişilebilir.  
  
### <a name="writeonlytextureview-deprecated"></a>writeonly_texture_view kullanım dışı  
 İçin [!INCLUDE[vs_dev12](../../atl-mfc-shared/includes/vs_dev12_md.md)], C++ AMP örnekleme ve tarafından desteklenen değil mipmaps gibi donanım doku özellikleri için daha iyi destek sunar [writeonly_texture_view sınıfı](../../parallel/amp/reference/writeonly-texture-view-class.md). Yeni sunulan `texture_view` sınıfı, bir alt kümesi işlevleri destekler `writeonly_texture_view`; sonuç olarak, `writeonly_texture_view` kullanım dışı bırakılmıştır.  
  
 Öneririz; en az yeni kodunun — kullandığınız `texture_view` önceden tarafından sağlanan erişim işlevselliği için `writeonly_texture_view`. İki bileşenden (int_2) sahip bir doku nesnesine yazma aşağıdaki iki kod örnekleri karşılaştırın. Her iki durumda da, görünüm dikkat `wo_tv4`, lambda ifadesi değeri tarafından yakalanan gerekir. İşte yeni örnek `texture_view` sınıfı:  
  
```cpp  
void write2ComponentTexture() {  
    texture<int_2, 1> tex4(16);

    texture_view<int_2, 1> wo_tv4(tex4);

    parallel_for_each(extent<1>(16), [=] (index<1> idx) restrict(amp) {  
    wo_tv4.set(idx, int_2(1, 1));

 });

}  
```  
  
 Burada da kullanım dışı `writeonly_texture_view` sınıfı:  
  
```  
void write2ComponentTexture() {  
    texture<int_2, 1> tex4(16);

    writeonly_texture_view<int_2, 1> wo_tv4(tex4);

    parallel_for_each(extent<1>(16), [=] (index<1> idx) restrict(amp) {     
    wo_tv4.set(idx, int_2(1, 1));

 });

}  
```  
  
 Gördüğünüz gibi tüm yapmakta olduğunuz yazılırken zaman birincil mipmap düzeyine iki kod örnekleri neredeyse aynıdır. Kullandıysanız `writeonly_texture_view` var olan kodu ve size kod, değiştirmeniz gerekmez, geliştirmek planlamanız durumunda değil. Bu kodu İleri getirme düşünüyorsanız, ancak kullanacak şekilde yeniden önerdiğimiz `texture_view` geliştirmeleri, yeni donanım doku özellikleri desteklemek için. Bu yeni özellikleri hakkında daha fazla bilgi için okumaya devam edin.  
  
 Kullanımdan hakkında daha fazla bilgi için `writeonly_texture_view`, bkz: [C++ AMP doku görünüm tasarımında genel bakış](http://blogs.msdn.com/b/nativeconcurrency/archive/2013/07/25/overview-of-the-texture-view-design-in-c-amp.aspx) paralel programlama yerel kod günlüğündeki.  
  
### <a name="instantiating-texture-view-objects"></a>Örnek oluşturma doku görünüm nesneleri  
 Bildirme bir `texture_view` bildirmek için benzer bir `array_view` ile ilişkili bir `array`. Aşağıdaki kod örneğinde birkaç bildirir `texture` nesneleri ve `texture_view` bunlarla ilişkili nesneleri.  
  
```  
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
  
 Nasıl bir doku görüntülemek, öğe türü const olmayan ve bir bileşen sahip dikkat edin, okuma-yazma olmakla birlikte, öğe türü const olmayan ancak birden fazla componenent bir doku görünüm salt yazılır. Const öğe türleri doku görünümlerini her zaman salt okunur, ancak öğe türü const olmayan, ardından öğesinde bileşenlerin sayısını okuma-yazma (1 bileşeni) olup olmadığını belirler. ya da salt yazılır (birden çok bileşeni).  
  
 Öğe türüne bir `texture_view`— kendi const şahit ve ayrıca olan bileşenlerin sayısını — ayrıca görünümü doku örnekleme destekleyip desteklemediğini ve mipmap düzeyleri nasıl erişilebileceğini belirlemede bir rol oynar:  
  
|Tür|Bileşenler|Oku|Write|Örnekleme|Mipmap erişim|  
|----------|----------------|----------|-----------|--------------|-------------------|  
|texture_view\<const T, N >|1, 2, 4|Evet|Hayır (1)|Evet|Evet, dizine eklenebilir. Aralığı, örnek oluşturma sırasında belirlenir.|  
|Texture_view\<T, N >|1.<br /><br /> 2, 4|Evet<br /><br /> Hayır (2)|Evet<br /><br /> Evet|Hayır (1)<br /><br /> Hayır (1)|Evet, bir düzey. Düzeyi örnek oluşturma sırasında belirlenir.<br /><br /> Evet, bir düzey. Düzeyi örnek oluşturma sırasında belirlenir.|  
  
 Bu tablodan salt okunur doku görünümleri tam görünümüne yazma yazdıramama karşılığında yeni özellikleri desteklemek görebilirsiniz. Yalnızca bir mipmap düzey erişebilir, yazılabilir doku görünümleri sınırlıdır. Öğe türü doku görünümün yalnızca bir bileşenin olduğunu gereksinim eklediğinden okuma-yazma doku yazılabilir olanlara kıyasla daha özelleştirilmiş görünümlerdir. Okuma odaklı bir işlem olduğundan örnekleme için yazılabilir doku görünümleri desteklenmiyor dikkat edin.  
  
### <a name="reading-from-texture-view-objects"></a>Doku görünüm nesneleri okuma  
 Doku görünümler tarafından değeri yakalanır ancak dokuları başvuruya göre yakalanır doku görünümü aracılığıyla unsampled doku veri okuma, doku kendisi yalnızca okuma gibi olmasıdır. Aşağıdaki iki kod örnekleri gösterir; ilk kullanarak `texture` yalnızca:  
  
```  
void write2ComponentTexture() {  
    texture<int_2, 1> text_data(16);

    parallel_for_each(extent<1>(16), [&] (index<1> idx) restrict(amp) {  
    tex_data.set(idx, int_2(1, 1));

 });

}  
```  
  
 Burada da aynı örneği artık kullanır dışında `texture_view` sınıfı:  
  
```  
void write2ComponentTexture() {  
    texture<int_2, 1> tex_data(16);

    texture_view<int_2, 1> tex_view(tex_data);

    parallel_for_each(extent<1>(16), [=] (index<1> idx) restrict(amp) {  
    tex_view.set(idx, int_2(1, 1));

 });

}  
```  
 Doku öğeleri kayan nokta türlerinde bağlı görünümler — Örneğin, float, float_2 veya float_4 — ayrıca donanım desteği çeşitli avantajlarından yararlanmak için doku örnekleme kullanarak okunur modları filtreleme ve modları adresleme. C++ AMP işlem senaryolarda en yaygın iki filtreleme modunu destekler — noktası filtreleme (en yakın-komşu) ve doğrusal filtreleme (Ağırlıklı ortalama) — ve dört adresleme modları — Sarmalanan, yansıtılmış, clamped ve sınır. Adresleme modları hakkında daha fazla bilgi için bkz: [address_mode numaralandırması](reference/concurrency-graphics-namespace-enums.md#address_mode).  
  
 C++ AMP doğrudan destekleyen modları ek olarak, diğer filtre modu ve temel platform adresleme modları doğrudan platform API'leri kullanılarak oluşturulmuş bir doku örneği benimsemek için birlikte çalışma API'lerini kullanarak erişebilirsiniz. Örneğin, Direct3D Eşyönsüz filtreleme gibi diğer filtre modu destekler ve her bir doku boyut için farklı bir adres modu uygulayabilirsiniz. Direct3D API'lerini kullanarak Eşyönsüz filtreleme ile olan koordinatları dikey Sarmalanan, yatay olarak yansıtılmış ve örnek bir doku örneği oluşturun ve ardından örneği C++ AMP kodunuzda kullanmanızı `make_sampler` birlikte çalışma API. Daha fazla bilgi için bkz: [doku örnekleme C++ AMP içinde](http://blogs.msdn.com/b/nativeconcurrency/archive/2013/07/18/texture-sampling-in-c-amp.aspx) paralel programlama yerel kod günlüğündeki.  
  
 Doku görünümleri de mipmaps okumayı destekler. Salt okunur doku görünümler (olanlar const bir öğe türüne sahip) örnek oluşturma sırasında belirlenir bir aralığı, MIP-düzeyleri dinamik olarak örneklenebilir olduğundan ve 1, 2 veya 4 bileşenleri olan öğenin desteklenmediğinden en fazla esnekliği sunar. Bir bileşen olan öğenin sahip okuma-yazma doku görünümleri, ancak yalnızca bir örnek oluşturma sırasında belirlenir düzeyi mipmaps de destekler. Daha fazla bilgi için bkz: [Mipmaps dokuyu](http://blogs.msdn.com/b/nativeconcurrency/archive/2013/08/22/texture-with-mipmaps.aspx) paralel programlama yerel kod günlüğündeki.  
  
### <a name="writing-to-texture-view-objects"></a>Doku görünüm nesneleri için yazma  
 Kullanım [texture_view::get yöntemi](reference/texture-view-class.md#get) temel yazmak için `texture` aracılığıyla `texture_view` nesnesi. Bir doku görünüm salt okunur, salt okunur veya sadece yazılabilir olabilir. Bir doku görünüm yazılabilir const olmayan bir öğe türü olmalıdır; bir doku görünüm okunabilir ve yazılabilir olması öğesi türünü de yalnızca bir bileşen içermelidir. Aksi durumda doku görünüm salt okunurdur. Görünümün örneği oluşturulduğunda düzeyi belirtilir ve bir doku görünümü aracılığıyla bir seferde yalnızca erişim bir mipmap düzeyini doku kullanabilirsiniz.  
  
 Bu örnek nasıl 4 mipmap düzeyleri olan doku ikinci en ayrıntılı mipmap düzeyine yazılacağını gösterir. Düzey 0 en ayrıntılı mipmap düzeyi var.  
  
```  
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

 C++ AMP çalışma zamanı arasında birlikte çalışabilirlik destekleyen `texture<T,1>` ve [ID3D11Texture1D arabirimi](http://go.microsoft.com/fwlink/p/?linkId=248503), arasında `texture<T,2>` ve [ID3D11Texture2D arabirimi](http://go.microsoft.com/fwlink/p/?linkId=255317), arasında `texture<T,3>`ve [ID3D11Texture3D arabirimi](http://go.microsoft.com/fwlink/p/?linkId=255377). [Get_texture](reference/concurrency-graphics-direct3d-namespace-functions.md#get_texture) metodu bir `texture` nesne ve döndürür bir `IUnknown` arabirimi. [Make_texture](reference/concurrency-graphics-direct3d-namespace-functions.md#make_texture) metodu bir `IUnknown` arabirimi ve bir `accelerator_view` nesne ve döndürür bir `texture` nesnesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [double_2 sınıfı](../../parallel/amp/reference/double-2-class.md)   
 [double_3 sınıfı](../../parallel/amp/reference/double-3-class.md)   
 [double_4 sınıfı](../../parallel/amp/reference/double-4-class.md)   
 [float_2 sınıfı](../../parallel/amp/reference/float-2-class.md)   
 [float_3 sınıfı](../../parallel/amp/reference/float-3-class.md)   
 [float_4 sınıfı](../../parallel/amp/reference/float-4-class.md)   
 [int_2 sınıfı](../../parallel/amp/reference/int-2-class.md)   
 [int_3 sınıfı](../../parallel/amp/reference/int-3-class.md)   
 [int_4 sınıfı](../../parallel/amp/reference/int-4-class.md)   
 [norm_2 sınıfı](../../parallel/amp/reference/norm-2-class.md)   
 [norm_3 sınıfı](../../parallel/amp/reference/norm-3-class.md)   
 [norm_4 sınıfı](../../parallel/amp/reference/norm-4-class.md)   
 [short_vector yapısı](../../parallel/amp/reference/short-vector-structure.md)   
 [short_vector_traits yapısı](../../parallel/amp/reference/short-vector-traits-structure.md)   
 [uint_2 sınıfı](../../parallel/amp/reference/uint-2-class.md)   
 [uint_3 sınıfı](../../parallel/amp/reference/uint-3-class.md)   
 [uint_4 sınıfı](../../parallel/amp/reference/uint-4-class.md)   
 [unorm_2 sınıfı](../../parallel/amp/reference/unorm-2-class.md)   
 [unorm_3 sınıfı](../../parallel/amp/reference/unorm-3-class.md)   
 [unorm_4 Sınıfı](../../parallel/amp/reference/unorm-4-class.md)
