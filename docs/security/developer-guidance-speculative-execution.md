---
title: Kurgusal yürütme tarafı kanalları için C++ Geliştirici Kılavuzu
ms.date: 07/10/2018
helpviewer_keywords:
- Visual C++, security
- security [C++]
- security [C++], best practices
- Spectre
- CVE-2017-5753
- Speculative Execution
ms.openlocfilehash: 72dffd25eef847d1bdffe61c4a18a27d9cb33644
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88842461"
---
# <a name="c-developer-guidance-for-speculative-execution-side-channels"></a>Kurgusal yürütme tarafı kanalları için C++ Geliştirici Kılavuzu

Bu makale, geliştiricilerin C++ yazılımlarında yansımalı yürütme tarafı kanal donanım açıklarını tanımlamaya ve azaltmaya yardımcı olmak için rehberlik içerir. Bu güvenlik açıkları, güven sınırları genelinde hassas bilgileri açığa çıkarabilir ve yönergelerin, kurgusal ve sıra dışı yürütmeyi destekleyen işlemcilerde çalışan yazılımları etkileyebilir. Bu güvenlik açığı sınıfı ilk olarak Ocak, 2018 ve ek arka planda açıklanmıştı ve [Microsoft 'un güvenlik danışmanlığı](https://portal.msrc.microsoft.com/security-guidance/advisory/ADV180002)içinde rehberlik bulunabilir.

Bu makale tarafından sunulan kılavuz, tarafından temsil edilen güvenlik açıklarına yönelik sınıflarla ilgilidir:

1. CVE-2017-5753, Spectre Variant 1 olarak da bilinir. Bu donanım güvenlik açığı sınıfı, koşullu bir dalın yanlış tahmin sonucu olarak oluşan yansımalı yürütme nedeniyle ortaya çıkabilecek yan kanallar ile ilgilidir. Visual Studio 2017 ' de Microsoft C++ derleyicisi (Version 15.5.5 ile başlayarak), `/Qspectre` CVE-2017-5753 ile ilgili sınırlı olabilecek güvenlik açıklarına yönelik kodlama desenlerine yönelik derleme zamanı azaltma sağlayan anahtar için destek içerir. Bu `/Qspectre` anahtar, Visual Studio 2015 güncelleştirme 3 Ile [KB 4338871](https://support.microsoft.com/help/4338871)arasında da kullanılabilir. Bayrağa yönelik belgeler, [`/Qspectre`](../build/reference/qspectre.md) etkileri ve kullanımı hakkında daha fazla bilgi sağlar.

2. CVE-2018-3639, Ayrıca, [Specutive deposu atlama (SSB)](https://aka.ms/sescsrdssb)olarak da bilinir. Bu donanım güvenlik açığı sınıfı, bellek erişiminin yanlış tahmin sonucu olarak bağımlı bir deponun önünde oluşan bir yükün önünde yürütülebileceği için ortaya çıkabilecek yan kanallar ile ilgilidir.

Bu sorunları tespit eden araştırma takımlarından biri tarafından [Spectre ve Meltüksel olma durumu](https://www.youtube.com/watch?v=_4O0zMW-Zu4) başlıklı sunuda, yansımalı yürütme tarafı kanalı güvenlik açıklarına erişilebilir bir giriş bulabilirsiniz.

## <a name="what-are-speculative-execution-side-channel-hardware-vulnerabilities"></a>Spectıcı yürütme tarafı kanal donanımı güvenlik açıkları nelerdir?

Modern CPU 'Lar, yönergelerin öngörülebilir ve sıra dışı yürütmesini kullanarak daha yüksek performans sağlar. Örneğin, bu genellikle, CPU 'nun tahmin edilen dal hedefinde yönergeleri tahmin etmeye başlamasını sağlayan dalların (koşullu ve dolaylı) hedefi tahmine dayalı olarak gerçekleştirilir ve bu sayede gerçek dal hedefi çözümlenene kadar bir cepten kaçının. CPU 'nun daha sonra yanlış tahmin oluştuğunu bulduğu durumda, hesaplanan tüm makine durumları atılır. Bu durum, yanlış tahmin edilen öngörülere ilişkin mimari açıdan görünür etkileri olmamasını sağlar.

Yansımalı yürütme, mimari türsel görünür durumunu etkilemez, ancak CPU tarafından kullanılan çeşitli önbellekler gibi, farklı izlemeler mimari olmayan bir durumda kalabilir. Bu, daha fazla yüz kanallı güvenlik açıklarına neden olan belirgin yürütmenin daha açık izlemelerinden oluşur. Bunu daha iyi anlamak için, CVE-2017-5753 (sınır denetimi atlama) örneği sağlayan aşağıdaki kod parçasını göz önünde bulundurun:

```cpp
// A pointer to a shared memory region of size 1MB (256 * 4096)
unsigned char *shared_buffer;

unsigned char ReadByte(unsigned char *buffer, unsigned int buffer_size, unsigned int untrusted_index) {
    if (untrusted_index < buffer_size) {
        unsigned char value = buffer[untrusted_index];
        return shared_buffer[value * 4096];
    }
}
```

Bu örnekte, `ReadByte` bir arabellek, arabellek boyutu ve bu arabellekteki bir dizin sağlanır. Tarafından belirtilen dizin parametresi, `untrusted_index` yönetici olmayan bir işlem gibi daha az ayrıcalıklı bir bağlam tarafından sağlanır. `untrusted_index`Değerinden küçükse `buffer_size` , bu dizindeki karakter `buffer` tarafından okunan ve tarafından başvurulan paylaşılan bellek bölgesinde dizin oluşturma için kullanılır `shared_buffer` .

Mimari perspektifinden, bu kod dizisi `untrusted_index` her zaman en az bir değer olacak şekilde mükemmel bir güvendedir `buffer_size` . Ancak, yansımalı yürütmenin olması durumunda CPU 'nun koşullu dalı yanlış tahmin edebilmesi ve IF ifadesinin gövdesini daha `untrusted_index` büyük veya buna eşit olduğunda bile yürütmesi mümkündür `buffer_size` . Bunun bir sonucu olarak CPU, sınırının ötesinde `buffer` (gizli olabilir) bir bayt okuyabilir ve daha sonra bu bayt değerini kullanarak sonraki yükün adresini hesaplatabiliriz `shared_buffer` .

CPU sonunda bu yanlış tahmin tespit ederken, kalan kenar etkileri, sınırların dışına okunan bayt değeri hakkındaki bilgileri açığa çıkarmak üzere CPU önbelleğinde kalabilir `buffer` . Bu yan etkiler, içindeki her bir önbellek satırına ne kadar hızlı erişildiğini inceleyerek sistemde çalışan daha az ayrıcalıklı bir bağlam tarafından algılanabilir `shared_buffer` . Bunu gerçekleştirmek için gerçekleştirilebilecek adımlar şunlardır:

1. ** `ReadByte` `untrusted_index` Birden `buffer_size` az kez çağırın **. Saldırma bağlamı, kurban 'in, `ReadByte` dal tahmine dayalı olarak alınmamasına benzer şekilde (örneğin, RPC aracılığıyla) çağırmasına yol açabilir `untrusted_index` `buffer_size` .

2. **İçindeki `shared_buffer` tüm önbellek çizgilerini temizler **. Saldırma bağlamı, tarafından başvurulan paylaşılan bellek bölgesindeki tüm önbellek çizgilerini boşaltmalıdır `shared_buffer` . Bellek bölgesi paylaşıldığından bu, basittir ve gibi iç bilgiler kullanılarak gerçekleştirilebilir `_mm_clflush` .

3. ** `ReadByte` `untrusted_index` Değerinden `buffer_size` büyük olan öğesini çağırın **. Saldırıda bulunan bağlam, kurban 'in `ReadByte` dalın alınmamasını, yanlış tahmin edecek şekilde çağırmasına neden olur. Bu, işlemcinin, IF bloğunun gövdesini daha büyük bir şekilde yürütmesine olanak sağlar ve bu `untrusted_index` `buffer_size` nedenle, bir sınırların dışında bir okuma ile başa çıkar `buffer` . Sonuç olarak, `shared_buffer` sınır dışında okunan bir gizli dizi değeri kullanılarak dizine alınır ve bu nedenle ilgili önbellek SATıRıNıN CPU tarafından yüklenmesine neden olur.

4. ** `shared_buffer` En hızlı şekilde erişildiğini görmek için içindeki her bir önbellek satırını okuyun**. Saldırıda bulunan bağlam, içindeki her bir önbellek satırını okuyabilir `shared_buffer` ve diğerlerinden önemli ölçüde daha hızlı yüklenen önbellek satırını tespit edebilir. Bu, adım 3 ' te getirilen, büyük olasılıkla önbellek satırdır. Bu örnekteki bayt değeri ile Önbellek satırı arasında 1:1 bir ilişki olduğundan, bu, saldırganın sınırların dışında okunan baytın gerçek değerini çıkarması için izin verir.

Yukarıdaki adımlar, bir CVE-2017-5753 örneğini kullanmaktan yararlanarak TEMIZLEME + yeniden yükleme olarak bilinen bir tekniği kullanmanın bir örneğini sağlar.

## <a name="what-software-scenarios-can-be-impacted"></a>Hangi yazılım senaryolarında etkilenebilirsiniz?

[Güvenlik geliştirme yaşam döngüsü](https://www.microsoft.com/sdl/) (SDL) gibi bir işlemi kullanarak güvenli yazılım geliştirme, genellikle geliştiricilerin uygulamasında mevcut olan güven sınırlarını belirlemesini gerektirir. Bir uygulamanın, sistemdeki başka bir işlem veya çekirdek modu cihaz sürücüsü durumunda yönetici olmayan bir Kullanıcı modu işlemi gibi daha az güvenilir bir bağlam tarafından belirtilen verilerle etkileşime girebileceği yerlerde bir güven sınırı bulunur. Yansımalı yürütme tarafı kanallarını içeren yeni güvenlik açığı sınıfı, bir cihazdaki kodu ve verileri yalıtmak için mevcut yazılım güvenlik modellerindeki birçok güven sınırıyla ilgilidir.

Aşağıdaki tabloda, geliştiricilerin bu güvenlik açıklarına karşı endişeleri olması gerekebilecek yazılım güvenlik modellerinin bir özeti verilmiştir:

|Güven sınırı|Açıklama|
|----------------|----------------|
|Sanal makine sınırı|Başka bir sanal makineden güvenilmeyen verileri alan ayrı sanal makinelerde iş yüklerini yalıtmak için uygulamalar risk altında olabilir.|
|Çekirdek sınırı|Yönetici olmayan bir kullanıcı modundan güvenilmeyen verileri alan çekirdek modu bir cihaz sürücüsü risk altında olabilir.|
|İşlem sınırı|Yerel sistemde çalışan, uzak yordam çağrısı (RPC), paylaşılan bellek veya diğer Işlem arası Iletişim (IPC) mekanizmaları gibi başka bir işlemden güvenilmeyen verileri alan bir uygulama risk altında olabilir.|
|Şifreleme sınırı|Güvenli bir kuşatma (örneğin, Intel SGX) içinde yürütülen ve güvenilir olmayan verileri şifreleme dışından alan bir uygulama risk altında olabilir.|
|Dil sınırı|Daha yüksek düzeyde bir dilde yazılan güvenilmeyen kodu, ya da tam zamanında (JıT) derleyen ve yürüten bir uygulama riskli olabilir.|

Yukarıdaki güven sınırlarının herhangi birine açık saldırı yüzeyi olan uygulamaların, öngörülebilir yürütme tarafı kanalı güvenlik açıklarının olası örneklerini belirlemek ve azaltmak için saldırı yüzeyinde kodu gözden geçirmesi gerekir. Uzak ağ protokolleri gibi uzak saldırı yüzeylerine sunulan güven sınırlarının, öngörülebilir yürütme tarafı kanalı güvenlik açıklarına karşı risk altında gösterilmediğini not edilmelidir.

## <a name="potentially-vulnerable-coding-patterns"></a>Savunmasız olabilecek kodlama desenleri

Yansımalı yürütme tarafı kanalları, birden çok kodlama deseninden kaynaklanan bir sonuç olabilir. Bu bölümde, savunmasız olabilecek kodlama desenleri açıklanmakta ve her biri için örnekler sağlanmaktadır, ancak bu temalarda çeşitlemelerin mevcut olabileceğini de bilmelidir. Bu nedenle, geliştiricilerin bu desenleri örnek olarak ele geçirmesine ve potansiyel olarak güvenlik açığı bulunan tüm kodlama desenlerinin ayrıntılı bir listesi olarak yerine getirilmesi önerilir. Günümüzde yazılımda mevcut olabilecek aynı bellek güvenliği güvenlik açıkları sınıfları, Ayrıca, arabellek taşmaları, sınır dışı dizi erişimleri, Başlatılmamış bellek kullanımı, tür karışıklık vb. dahil, ancak bunlarla sınırlı olmamak üzere, yürütmenin öngörülebilir ve sıra dışı yolları üzerinde de bulunabilir. Saldırganların daha fazla bellek güvenliği güvenlik açıklarına karşı kullanabileceği temel türler, mimari yollar için de ayrıca yansımalı yollar için de uygulanabilir.

Genel olarak, koşullu dalla ilgili, koşullu bir ifade, daha az güvenilir bir bağlam tarafından denetlenebilen veya etkilenerek, koşullu bir ifade üzerinde çalışırken meydana gelen yürütme tarafı kanalları olabilir. Örneğin, bu,,,, **`if`** **`for`** **`while`** **`switch`** veya üçlü deyimler içinde kullanılan koşullu ifadeler içerebilir. Bu deyimlerden her biri için, derleyici, CPU 'nun daha sonra çalışma zamanında dal hedefini tahmin edebildiğini koşullu bir dal oluşturabilir.

Her örnek için, bir geliştiricinin risk azaltma olarak bir engel tanıtabileceği "SPECULASYON ENGELI" ifadesini içeren bir açıklama eklenir. Bu, azaltmaları konusunda bölümünde daha ayrıntılı bir şekilde ele alınmıştır.

## <a name="speculative-out-of-bounds-load"></a>Yansımalı olmayan yük

Bu kodlama desenleri kategorisi, bir dizi ayırma dışı bellek erişimine yol gösteren bir koşullu dal yanlış tahminini içerir.

### <a name="array-out-of-bounds-load-feeding-a-load"></a>Dizi sınırların dışında yükleme bir yükü beslemeyi

Bu kodlama stili, ilk olarak CVE-2017-5753 için güvenlik açığı bulunan kodlama deseninin (sınır denetimi atlama) açıklanacaktır. Bu makalenin arka plan bölümünde bu model ayrıntılı olarak açıklanmaktadır.

```cpp
// A pointer to a shared memory region of size 1MB (256 * 4096)
unsigned char *shared_buffer;

unsigned char ReadByte(unsigned char *buffer, unsigned int buffer_size, unsigned int untrusted_index) {
    if (untrusted_index < buffer_size) {
        // SPECULATION BARRIER
        unsigned char value = buffer[untrusted_index];
        return shared_buffer[value * 4096];
    }
}
```

Benzer şekilde, bir dizi sınırların dışında bir yük, yanlış tahmin nedeniyle Sonlandırma koşulunu aşan bir döngüyle birlikte gerçekleşebilir. Bu örnekte, ifadeyle ilişkilendirilen koşullu dal, `x < buffer_size` **`for`** büyük veya eşit olduğunda döngünün gövdesini yanlış tahmin edebilir ve ortaya çıkabilir. bu `x` `buffer_size` nedenle, daha sonra yansımalı olmayan bir yükün oluşmasına neden olur.

```cpp
// A pointer to a shared memory region of size 1MB (256 * 4096)
unsigned char *shared_buffer;

unsigned char ReadBytes(unsigned char *buffer, unsigned int buffer_size) {
    for (unsigned int x = 0; x < buffer_size; x++) {
        // SPECULATION BARRIER
        unsigned char value = buffer[x];
        return shared_buffer[value * 4096];
    }
}
```

### <a name="array-out-of-bounds-load-feeding-an-indirect-branch"></a>Dizi sınırların dışı yükü dolaylı bir dalı besliyor

Bu kodlama düzeni, koşullu bir dalın yanlış tahmin durumunun bir dizi işlev işaretçisi dizisine neden olabileceği, daha sonra sınırların dışında okunan hedef adrese dolaylı bir dala yol açabilecek bir durum içerir. Aşağıdaki kod parçacığı bunu gösteren bir örnek sağlar.

Bu örnekte,, DispatchMessage parametresi aracılığıyla bir güvenilmeyen ileti tanımlayıcısı sağlanır `untrusted_message_id` . `untrusted_message_id`Değerinden küçükse `MAX_MESSAGE_ID` , bir işlev işaretçilerine ve dal dizisine dizin eklemek için kullanılır. Bu kod, güvenli mimari türdedir, ancak CPU koşullu dalı yanlış tahmin eder, `DispatchTable` `untrusted_message_id` değeri değerinden büyük veya buna eşit olduğunda `MAX_MESSAGE_ID` , bu nedenle bir sınır dışı erişime göre dizin oluşturma ile sonuçlanabilir. Bu durum, dizi sınırlarının ötesine türetilmiş bir dal hedefi adresinden oluşan ve yürütülen koda bağlı olarak bilgilerin açığa çıkmasına neden olabilecek bir dal hedef adresinden elde edilen yürütmenin oluşmasına neden olabilir.

```cpp
#define MAX_MESSAGE_ID 16

typedef void (*MESSAGE_ROUTINE)(unsigned char *buffer, unsigned int buffer_size);

const MESSAGE_ROUTINE DispatchTable[MAX_MESSAGE_ID];

void DispatchMessage(unsigned int untrusted_message_id, unsigned char *buffer, unsigned int buffer_size) {
    if (untrusted_message_id < MAX_MESSAGE_ID) {
        // SPECULATION BARRIER
        DispatchTable[untrusted_message_id](buffer, buffer_size);
    }
}
```

Bir dizi sınırların dışında başka bir yük beslemesiyle, bu durum, yanlış tahmin nedeniyle Sonlandırma koşulunu aşan bir döngüyle birlikte da oluşabilir.

### <a name="array-out-of-bounds-store-feeding-an-indirect-branch"></a>Dizi sınırların dışı depo bir dolaylı dalı besliyor

Önceki örnekte, bir dizi sınır dışı yükün dolaylı bir dal hedefini nasıl etkileyebileceğini gösterdi. Ayrıca, bir dizi dışı deponun, bir işlev işaretçisi veya dönüş adresi gibi bir dolaylı dal hedefini değiştirmesi de mümkündür. Bu, saldırgan tarafından belirtilen adresten yansımalı yürütmeye neden olabilir.

Bu örnekte, güvenilmeyen bir dizin parametresi aracılığıyla geçirilir `untrusted_index` . `untrusted_index` `pointers` Dizi öğesinin (256 öğeleri) öğe sayısından küçükse, içindeki girilen işaretçi değeri `ptr` `pointers` diziye yazılır. Bu kod güvenli mimaridir, ancak CPU koşullu dalı yanlış tahmin eder, `ptr` yığın tarafından ayrılan dizinin sınırlarının ötesinde yansımalı olarak yazılabilir `pointers` . Bu, için dönüş adresinin yansımalı bozulmasına yol açabilir `WriteSlot` . Bir saldırgan değerini denetleyebilse, bu durum, `ptr` rastgele bir adres üzerinde döndüğünde rastgele bir adresten rastgele yürütmeye yol açabilir `WriteSlot` .

```cpp
unsigned char WriteSlot(unsigned int untrusted_index, void *ptr) {
    void *pointers[256];
    if (untrusted_index < 256) {
        // SPECULATION BARRIER
        pointers[untrusted_index] = ptr;
    }
}
```

Benzer şekilde, bir işlev işaretçisi adlı bir yerel değişken `func` yığında ayrılmışsa, `func` koşullu dal yanlış tahmin gerçekleştiğinde buna başvuran adresi bir şekilde değiştirmek mümkün olabilir. Bu, işlev işaretçisi aracılığıyla çağrıldığında rastgele bir adresten rastgele yürütmeye neden olabilir.

```cpp
unsigned char WriteSlot(unsigned int untrusted_index, void *ptr) {
    void *pointers[256];
    void (*func)() = &callback;
    if (untrusted_index < 256) {
        // SPECULATION BARRIER
        pointers[untrusted_index] = ptr;
    }
    func();
}
```

Bu örneklerin her ikisinde de yığın tarafından ayrılan dolaylı dal işaretçilerinin yansımalı değişikliğini içeren Not edilmelidir. Genel değişkenler, yığın olarak ayrılan bellek ve hatta bazı CPU 'Larda salt okuma belleği için de yansımalı değişiklik yapılabilir. Yığın tarafından ayrılan bellek için, Microsoft C++ derleyicisi zaten, ara değerli dolaylı dal hedeflerini, örneğin, arabelleklerin derleyici güvenlik özelliğinin bir parçası olarak bir güvenlik tanımlama bilgisine yerleştirilmesi gibi yerel değişkenleri yeniden sıralayarak daha zor hale getirmek için bir adım sürer [`/GS`](../build/reference/gs-buffer-security-check.md) .

## <a name="speculative-type-confusion"></a>Spectıcı tür karışıklığı

Bu kategori, yansımalı bir tür karışıklığına izin veren kodlama desenleriyle ilgilidir. Bu durum, yansımalı yürütme sırasında mimari olmayan bir yol boyunca hatalı bir tür kullanılarak belleğe erişildiğinde meydana gelir. Hem koşullu dal yanlış tahmin hem de yansımalı depo atlama, büyük olasılıkla kurgusal bir tür karışıklığına neden olabilir.

Yansımalı mağaza atlaması için bu durum, bir derleyicinin birden çok türdeki değişkenler için yığın konumunu yeniden kullandığı senaryolarda oluşabilir. Bunun nedeni, türünde bir değişkenin mimari deposunun `A` atlanabileceği ve bu sayede tür yükünün, `A` değişken atanmadan önce yansımalı olarak yürütülmesine izin verilmesi nedeniyle oluşur. Daha önce depolanan değişken farklı bir tür ise, bu durum, bir yansımalı tür karışıklığına yönelik koşullar oluşturabilir.

Koşullu dal yanlış tahmin için aşağıdaki kod parçacığı, yansımalı tür karışıklığına izin verebileceğini belirten farklı koşulları anlatmak için kullanılacaktır.

```cpp
enum TypeName {
    Type1,
    Type2
};

class CBaseType {
public:
    CBaseType(TypeName type) : type(type) {}
    TypeName type;
};

class CType1 : public CBaseType {
public:
    CType1() : CBaseType(Type1) {}
    char field1[256];
    unsigned char field2;
};

class CType2 : public CBaseType {
public:
    CType2() : CBaseType(Type2) {}
    void (*dispatch_routine)();
    unsigned char field2;
};

// A pointer to a shared memory region of size 1MB (256 * 4096)
unsigned char *shared_buffer;

unsigned char ProcessType(CBaseType *obj)
{
    if (obj->type == Type1) {
        // SPECULATION BARRIER
        CType1 *obj1 = static_cast<CType1 *>(obj);

        unsigned char value = obj1->field2;

        return shared_buffer[value * 4096];
    }
    else if (obj->type == Type2) {
        // SPECULATION BARRIER
        CType2 *obj2 = static_cast<CType2 *>(obj);

        obj2->dispatch_routine();

        return obj2->field2;
    }
}
```

### <a name="speculative-type-confusion-leading-to-an-out-of-bounds-load"></a>Sınır dışı bir yük için yansımalı tür karışıklık lideri

Bu kodlama stili, kurgusal bir tür karışıklığın, yüklenen değer beslemelerinin sonraki bir yükleme adresi olan bir sınır dışında veya tür karışmış alan erişimine neden olduğu bir durum içerir. Bu dizi sınırların dışında kodlama düzenine benzerdir, ancak yukarıda gösterildiği gibi alternatif bir kodlama sırası aracılığıyla yapılır. Bu örnekte, bir saldırma bağlamı, kurban bağlamının `ProcessType` bir nesne türü `CType1` ( `type` alan eşittir) ile birden çok kez yürütülmesine neden olabilir `Type1` . Bu, ilk deyimin tahmin edilmesi için koşullu dala eğitim etkisine sahip olur **`if`** . Sonra da saldırın bağlamı, kurban bağlamının `ProcessType` türünde bir nesne ile yürütülmesine neden olabilir `CType2` . Bu, ilk deyimin koşullu dalı **`if`** yanlış tahmin eder ve deyim gövdesini çalıştırırsa ve bu **`if`** nedenle türünde bir nesne dönüştürdüğünden, yansımalı bir tür karışıklığına neden olabilir `CType2` `CType1` . `CType2`Öğesinden daha küçük olduğu `CType1` için bellek erişimi gizli olabilecek `CType1::field2` verilerin yansımalı olmayan bir yüküne neden olur. Daha sonra bu değer `shared_buffer` , daha önce açıklandığı gibi dizi sınırların dışında, daha sonra observable yan etkileri oluşturabileceğiniz bir yüklemede kullanılır.

### <a name="speculative-type-confusion-leading-to-an-indirect-branch"></a>Dolaylı bir dala kurgusal tür karışıklık lideri

Bu kodlama stili, yansımalı bir tür karışıklığın, öngörülebilir yürütme sırasında güvenli olmayan bir dolaylı dala neden olduğu bir durum içerir. Bu örnekte, bir saldırma bağlamı, kurban bağlamının `ProcessType` bir nesne türü `CType2` ( `type` alan eşittir) ile birden çok kez yürütülmesine neden olabilir `Type2` . Bu, ilk deyimin alınması için koşullu dala **`if`** ve bu `else if` bildirimin alınmayacak şekilde eğitim etkisine sahip olur. Sonra da saldırın bağlamı, kurban bağlamının `ProcessType` türünde bir nesne ile yürütülmesine neden olabilir `CType1` . Bu, ilk deyimin koşullu dalı **`if`** çekilirken ve `else if` deyim tahmin alınmadığından, bu, ' ın gövdesini yürütülerek `else if` ve türünde bir nesne dönüştürdüğünden, `CType1` Yansımalı bir tür karışıklığına neden olabilir `CType2` . Alan, `CType2::dispatch_routine` dizi ile örtüştüğünden **`char`** `CType1::field1` , bu durum, istenmeyen bir dal hedefine yansımalı bir dolaylı dala neden olabilir. Saldırma bağlamı dizideki bayt değerlerini denetleyebilir, bu, `CType1::field1` dal hedefi adresini denetleyebilir.

## <a name="speculative-uninitialized-use"></a>Kurgusal başlatılmamış kullanım

Bu kodlama desenleri kategorisi, speculatıcı yürütmenin başlatılmamış belleğe erişebileceği ve sonraki bir yük ya da dolaylı dalı akışa almak için kullanabileceği senaryolar içerir. Bu kodlama desenlerinin yararlanması için bir saldırganın, ' de kullanılmakta olan bağlamı tarafından başlatılmadan kullanılan bellek içeriğini denetleyebilmesi veya anlamlı bir şekilde etkilemesini sağlaması gerekir.

### <a name="speculative-uninitialized-use-leading-to-an-out-of-bounds-load"></a>Bir sınır dışı yüklemeye önde gelen başlatılmamış kullanım

Beklenmeyen bir başlatılmamış kullanım, bir saldırgan denetimli değeri kullanılarak bir sınır dışı yüklemeye neden olabilir. Aşağıdaki örnekte, değeri `index` `trusted_index` Tüm mimari yollarda atanır ve değerinden `trusted_index` küçük veya buna eşit olduğu varsayılır `buffer_size` . Ancak, derleyici tarafından üretilen koda bağlı olarak, yük, `buffer[index]` ve bağımlı deyimlere atamanın önüne yürütülmesine izin veren bir yansımalı depo atlama meydana gelebilir `index` . Bu durum oluşursa, için başlatılmamış bir değer, `index` `buffer` bir saldırganın hassas bilgileri sınırların dışına okumasını ve bunu bağımlı bir kanaldan bir yan kanal aracılığıyla bunu sağlayabileceği konum olarak kullanılacaktır `shared_buffer` .

```cpp
// A pointer to a shared memory region of size 1MB (256 * 4096)
unsigned char *shared_buffer;

void InitializeIndex(unsigned int trusted_index, unsigned int *index) {
    *index = trusted_index;
}

unsigned char ReadByte(unsigned char *buffer, unsigned int buffer_size, unsigned int trusted_index) {
    unsigned int index;

    InitializeIndex(trusted_index, &index); // not inlined

    // SPECULATION BARRIER
    unsigned char value = buffer[index];
    return shared_buffer[value * 4096];
}
```

### <a name="speculative-uninitialized-use-leading-to-an-indirect-branch"></a>Bir dolaylı dala kurgusal kullanım lideri başlatılmadı

Kurgusal bir başlatılmamış kullanım, dal hedefinin bir saldırgan tarafından denetlendiği dolaylı bir dala neden olabilir. Aşağıdaki örnekte, `routine` `DefaultMessageRoutine1` `DefaultMessageRoutine` değerine bağlı olarak ya da değerine göre atanır `mode` . Mimari yolda, bu, `routine` dolaylı daldan önce her zaman başlatılmış olur. Ancak, derleyici tarafından üretilen koda bağlı olarak, dolaylı `routine` dalın ' a atamanın önüne yürütülmesine izin veren bir yansımalı mağaza geçişi meydana gelebilir `routine` . Bu durum oluşursa, saldırgan rastgele bir adresten ayrılabilir ve bu da saldırganın başlatılmamış değerini etkileyebileceğini veya denetleyebilmesini kabul edebilir `routine` .

```cpp
#define MAX_MESSAGE_ID 16

typedef void (*MESSAGE_ROUTINE)(unsigned char *buffer, unsigned int buffer_size);

const MESSAGE_ROUTINE DispatchTable[MAX_MESSAGE_ID];
extern unsigned int mode;

void InitializeRoutine(MESSAGE_ROUTINE *routine) {
    if (mode == 1) {
        *routine = &DefaultMessageRoutine1;
    }
    else {
        *routine = &DefaultMessageRoutine;
    }
}

void DispatchMessage(unsigned int untrusted_message_id, unsigned char *buffer, unsigned int buffer_size) {
    MESSAGE_ROUTINE routine;

    InitializeRoutine(&routine); // not inlined

    // SPECULATION BARRIER
    routine(buffer, buffer_size);
}
```

## <a name="mitigation-options"></a>Risk azaltma seçenekleri

Kaynak kodda değişiklik yapılarak, yansımalı yürütme tarafı kanal güvenlik açıkları azaltılabilir. Bu değişiklikler, bir açığa *çıkarma engeli*ekleyerek ya da bir uygulamanın tasarımında değişiklik yaparak, bir güvenlik açığı oluşturarak ya da gizli bilgilerin yansımalı yürütmeye erişilememesi için değişiklikler yaparak bir güvenlik açığının belirli örneklerini azaltmaya yönelik olabilir.

### <a name="speculation-barrier-via-manual-instrumentation"></a>El ile izleme yoluyla yansımalı engel

Yansımalı yürütmenin mimari olmayan bir yol üzerinde devam etmelerini engellemek için bir geliştirici tarafından bir *Yansımalı engel* el ile eklenebilir. Örneğin, bir geliştirici, bir koşullu blok gövdesinde, bloğun başlangıcında (koşullu daldan sonra) veya sorun olan ilk yükün önünde bir, tehlikeli kodlama düzeninden önce bir yansımalı engel ekleyebilir. Bu, bir koşullu dalın yanlış tahmin çalışmasının, yürütmeyi serileştirerek mimari olmayan bir yoldaki tehlikeli kodu yürütmesini engeller. Aşağıdaki tabloda açıklandığı gibi, speculasyon engel sırası donanım mimarisine göre farklılık gösterir:

|Mimari|CVE-2017-5753 için speculasyon engel iç|CVE-2018-3639 için speculasyon engel iç|
|----------------|----------------|----------------|
|x86/x64|_mm_lfence ()|_mm_lfence ()|
|ARM|Şu anda kullanılamıyor|__dsb (0)|
|ARM64|Şu anda kullanılamıyor|__dsb (0)|

Örneğin, aşağıdaki kod deseninin, `_mm_lfence` aşağıda gösterildiği gibi iç kullanılarak azaltılabilir.

```cpp
// A pointer to a shared memory region of size 1MB (256 * 4096)
unsigned char *shared_buffer;

unsigned char ReadByte(unsigned char *buffer, unsigned int buffer_size, unsigned int untrusted_index) {
    if (untrusted_index < buffer_size) {
        _mm_lfence();
        unsigned char value = buffer[untrusted_index];
        return shared_buffer[value * 4096];
    }
}
```

### <a name="speculation-barrier-via-compiler-time-instrumentation"></a>Derleyici zamanı izleme aracılığıyla yansımalı engel

Visual Studio 2017 ' de Microsoft C++ derleyicisi (sürüm 15.5.5 ile başlayan), `/Qspectre` CVE-2017-5753 ile ilgili sınırlı olabilecek çok sayıda kodlama desenlerine yönelik bir otomatik olarak bir otomatik olarak bir otomatik olarak bir otomatik olarak belirtilen engel ekler. Bayrağa yönelik belgeler, [`/Qspectre`](../build/reference/qspectre.md) etkileri ve kullanımı hakkında daha fazla bilgi sağlar. Bu bayrağın, güvenlik açığı bulunan tüm kodlama düzenlerini kapsamadığını ve bu tür geliştiricilerin bu güvenlik açığına yönelik kapsamlı bir azaltma olarak bu şekilde güvenmediğine dikkat edin.

### <a name="masking-array-indices"></a>Dizi dizinlerini maskeleme

Belirlenen sınırların dışında bir yükün gerçekleşebileceği durumlarda, dizi dizinini açıkça bağlamak için mantık eklenerek, dizi dizini hem mimari hem de mimari olmayan yol üzerinde kesin bir şekilde bağlanabilir. Örneğin, bir dizi iki kuvvetle hizalanmış bir boyuta ayrılabileceği takdirde, basit bir maske tanıtıabilir. Bu, ikisinin gücüne hizalanmış olduğu varsayıldığı örnekte gösterilmiştir `buffer_size` . Bu, `untrusted_index` `buffer_size` koşullu dal yanlış tahmin gerçekleşirse ve ' `untrusted_index` den büyük veya buna eşit bir değer ile geçirilse bile, her zaman daha küçük olmasını sağlar `buffer_size` .

Burada gerçekleştirilen dizin maskelemenin, derleyici tarafından oluşturulan koda bağlı olarak, kurgusal depo geçişine tabi olduğunu not edilmelidir.

```cpp
// A pointer to a shared memory region of size 1MB (256 * 4096)
unsigned char *shared_buffer;

unsigned char ReadByte(unsigned char *buffer, unsigned int buffer_size, unsigned int untrusted_index) {
    if (untrusted_index < buffer_size) {
        untrusted_index &= (buffer_size - 1);
        unsigned char value = buffer[untrusted_index];
        return shared_buffer[value * 4096];
    }
}
```

### <a name="removing-sensitive-information-from-memory"></a>Hassas bilgileri bellekten kaldırma

Öngörülebilir yürütme tarafı kanalının güvenlik açıklarını azaltmak için kullanılabilecek başka bir teknik ise hassas bilgileri bellekten kaldırmalıdır. Yazılım geliştiricileri, gizli bilgilere, öngörülebilir yürütme sırasında erişilemeyecek şekilde, uygulamasını yeniden düzenleme fırsatlarına bakabilirler. Bu, hassas bilgileri ayrı işlemlere yalıtmak için bir uygulamanın tasarımını yeniden düzenleyerek gerçekleştirilebilir. Örneğin, bir Web tarayıcı uygulaması her bir Web kaynağıyla ilişkili verileri ayrı işlemlere ayırmaya çalışabilir ve bu sayede bir işlemin, öngörülebilir yürütme aracılığıyla çıkış kaynaklı verilere erişmesini önler.

## <a name="see-also"></a>Ayrıca bkz.

[Yansımalı yürütme yan kanallı güvenlik açıklarını azaltmaya yönelik kılavuz](https://portal.msrc.microsoft.com/security-guidance/advisory/ADV180002)<br/>
[Kurgusal yürütme tarafı kanal donanımı güvenlik açıklarını Azaltıcı](https://blogs.technet.microsoft.com/srd/2018/03/15/mitigating-speculative-execution-side-channel-hardware-vulnerabilities/)
