---
title: Kurgusal yürütme yan kanal için C++ Geliştirici Kılavuzu | Microsoft Docs
ms.custom: ''
ms.date: 07/10/2018
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, security
- security [C++]
- security [C++], best practices
- Spectre
- CVE-2017-5753
- Speculative Execution
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 28d1df72efcc1fa7408922876ad91bafcd2b005a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46422675"
---
# <a name="c-developer-guidance-for-speculative-execution-side-channels"></a>Kurgusal yürütme yan kanal için C++ Geliştirici Kılavuzu

Bu makalede, tanımlamak ve C++ yazılım kurgusal yürütme yan kanal donanım güvenlik açıklarını azaltmaya yardımcı olmak üzere, geliştiriciler için kılavuz içerir. Bu güvenlik açıklarına güven sınırları boyunca hassas bilgileri açığa çıkarabileceği ve yönergeleri kurgusal, sırası yürütülmesini destekleyen işlemcilerde çalışan yazılımları etkileyebilir. Bu sınıf güvenlik açıklarının Ocak 2018 ' açıklanan first ve ek arka plan olan ve yönergeler bulunabilir [Microsoft'un güvenlik danışma belgesi](https://portal.msrc.microsoft.com/security-guidance/advisory/ADV180002).

Bu makalede tarafından sağlanan yönergeleri sınıfları tarafından temsil edilen güvenlik açıklarının ilişkilidir:

1. CVE-2017-5753, Spectre değişkeni 1 olarak da bilinir. Bu donanım güvenlik açığı sınıfı bir koşullu dalı misprediction sonucu olarak ortaya çıkan kurgusal yürütmeyi nedeniyle ortaya çıkabilecek yan kanal ilişkilidir. Visual Studio 2017 (sürüm 15.5.5 ile başlayarak) Visual C++ derleyicisi için destek içerir `/Qspectre` savunmasız kodlama desenleri sınırlı bir dizi için bir derleme zamanı azaltma sağlayan anahtar CVE-2017-5753 için ilgili. `/Qspectre` Anahtarıdır ayrıca Visual Studio 2015 güncelleştirme 3'ten kullanılabilir [KB 4338871](https://support.microsoft.com/help/4338871). Belgelerine [/qspectre](https://docs.microsoft.com/cpp/build/reference/qspectre) bayrağı kullanım ve etkileri hakkında daha fazla bilgi sağlar.

2. CVE-2018-olarak da bilinen 3639, [kurgusal Store atlama (SSB)](https://aka.ms/sescsrdssb). Bu donanım güvenlik açığı sınıfı, bir iş yükünün bellek erişim misprediction sonucunda bağımlı bir deposu önceden kurgusal yürütmeyi nedeniyle ortaya çıkabilecek yan kanal ilgilidir.

Kurgusal yürütme yan kanal güvenlik açıklarına erişilebilir giriş başlıklı sunuda bulunabilir [çalışması Spectre ve Meltdown](https://www.youtube.com/watch?v=_4O0zMW-Zu4) bu sorunları bulunan araştırma ekipler biri tarafından.

## <a name="what-are-speculative-execution-side-channel-hardware-vulnerabilities"></a>Kurgusal yürütme yan kanal donanım güvenlik açıklarını nelerdir?

Modern CPU hale getirerek daha yüksek performans derecesi sağlamak kurgusal ve sırası yürütme yönergeleri kullanın. Örneğin, bu genellikle speculatively tahmin edilen dal hedef adresindeki yönergeleri yürütmeye başlamak CPU sağlayan hedef dalı (koşullu ve dolaylı) hakkında tahminde bulunarak gerçekleştirilir gerçek dal hedefi olana kadar bu nedenle bir kabini kaçınma çözüldü. CPU, daha sonra bir misprediction oluştuğunu bulur, durumunda, tüm speculatively hesaplanan makine durumu atılır. Bu, hiçbir mimari görünür mispredicted Spekülasyon etkilerini olmasını sağlar.

Kurgusal yürütmeyi mimari görünürlük durumunu etkilemez, ancak CPU tarafından kullanılan çeşitli önbellekleri gibi mimari olmayan durumda kalan izlemeleri bırakabilirsiniz. Bu, yan kanal güvenlik açıkları ortaya çıkmasına neden veren kurgusal yürütme kalan bu izlemelerin olur. Bunu daha iyi anlamak için CVE-2017-5753 (denetleyin sınırları atlama) örneği sağlayan aşağıdaki kod parçasını göz önünde bulundurun:

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

Bu örnekte, `ReadByte` olan bir arabellek, arabellek boyutu ve bir dizin o arabelleğe sağlanan. Tarafından belirtilen dizin parametresi `untrusted_index`, daha az tarafından sağlanan yönetici olmayan bir işlem gibi ayrıcalıklı bağlamı. Varsa `untrusted_index` olduğu küçüktür `buffer_size`, sonra da bu dizindeki karakteri okuyabilir `buffer` ve bellek tarafından başvurulan paylaşılan bir bölge içinde dizin için kullanılan `shared_buffer`.

Garanti edilir gibi bir mimari açıdan bakıldığında, bu kod dizisi mükemmel güvenli `untrusted_index` her zaman küçüktür `buffer_size`. Ancak, kurgusal yürütmeyi saklanacaktır CPU koşullu bir dal yanlış tahmin ve IF işlevinin gövdesi yürütme mümkündür deyimi bile `untrusted_index` büyüktür veya eşittir `buffer_size`. Bu söz konusu kümelerdeki CPU bayt sınırları from beyond speculatively okuyabilirsiniz `buffer` (olan bir gizli dizi olabilir) ve sonra bir sonraki yük adresini hesaplamak için bu bayt değeri kullanabilirsiniz `shared_buffer`.

CPU sonunda bu misprediction algılar, ancak kalan yan etkileri je mimo rozsah okuma bayt değeri hakkında bilgi açığa CPU önbelleği bırakılabilir `buffer`. Bu yan etkileri daha az tarafından algılanabilir ayrıcalıklı içerik ne kadar hızlı yoklama işlemi tarafından sistem üzerinde çalışan her önbellek satır içinde `shared_buffer` erişilir. Bunu gerçekleştirmek için uygulanacak adımlar şunlardır:

1. **Çağırma `ReadByte` ile birden çok kez `untrusted_index` olan küçüktür `buffer_size`** . Saldırıyı gerçekleştiren bağlam çağrılacak victim bağlam neden olabilir `ReadByte` (örneğin, RPC) dal göstergesi olduğu gibi değil-taken olarak olmasını eğitilmiş `untrusted_index` olduğu küçüktür `buffer_size`.

2. **Çizgiler önbellek temizleme `shared_buffer`** . Saldırıyı gerçekleştiren bağlam tüm bellek tarafından başvurulan paylaşılan bölgedeki önbellek satırları temizlemek gerekir `shared_buffer`. Bellek bölgesini paylaşılan olduğundan, bu oldukça basittir ve yapı içleri gibi kullanılarak gerçekleştirilebilir `_mm_clflush`.

3. **Çağırma `ReadByte` ile `untrusted_index` daha büyük olan `buffer_size`** . Çağrılacak victim bağlam saldırıyı gerçekleştiren bağlam neden `ReadByte` dalın değil alınıp yanlış tahmin şekilde. IF işlevinin gövdesi speculatively yürütmek için işlemciyi block ile Bu nedenler `untrusted_index` daha büyük olan `buffer_size`, bu nedenle işlemleri okuma için önde gelen, `buffer`. Sonuç olarak, `shared_buffer` işlemleri, bu nedenle CPU tarafından yüklenmesine izin ilgili önbellek satırı neden okundu potansiyel olarak gizli bir değer kullanarak dizinlenir.

4. **Her önbellek satırı oku `shared_buffer` , en hızlı erişilir görmek için**. Saldırıyı gerçekleştiren bağlam içinde her önbellek satırı okuyabilirsiniz `shared_buffer` diğerlerinden önemli ölçüde daha hızlı yükler önbellek satırı algılayın. Adım 3'tarafından getirdiğiniz olasılığı yüksek olan bir önbellek satırı budur. Bu örnekte bayt değeri ve önbellek satırı arasında 1:1 ilişki olduğundan, bu işlemleri okunan bayt gerçek değerini çıkarsamak bir saldırgan sağlar.

Yukarıdaki adımları CVE-2017-5753 örneğini kötüye ile birlikte temizleme + yeniden bilinen bir yöntem kullanarak bir örnek sağlar.

## <a name="what-software-scenarios-can-be-impacted"></a>Hangi yazılım senaryoları etkilenebilir?

Gibi bir işlem kullanılarak güvenli yazılım geliştirme [güvenlik geliştirme yaşam döngüsü](https://www.microsoft.com/en-us/sdl/) (SDL) uygulamalarında mevcut güven sınırları belirlemek geliştiriciler genellikle gerektirir. Burada bir uygulama gibi sistem üzerinde başka bir işlem ya da yönetici olmayan kullanıcı modu işlem çekirdek modu aygıt sürücüsü olması durumunda en az güvenilen bir bağlam tarafından sağlanan verilerle etkileşimde bulunabilir yerde bir güven sınırı var. Yeni bir sınıf içeren kurgusal yürütme yan kanal güvenlik açıklarının birçok güven sınırları içinde kodu ve bir cihazdaki verileri yalıtmaya mevcut yazılım güvenlik modelleri için geçerlidir.

Aşağıdaki tabloda, burada geliştiriciler açıklarından oluşan hakkında endişe olması gerekebilir yazılım güvenlik modelleri bir özetini sunar:

|Güven sınırı|Açıklama|
|----------------|----------------|
|Sanal makine sınır|Güvenilir olmayan verileri başka bir sanal makineden alma ayrı sanal makineler'de iş yüklerini yalıtmak uygulamaları risk altında olabilir.|
|Çekirdek sınırı|Bir yönetici olmayan kullanıcı modu işlemden güvenilmeyen verileri alan bir çekirdek modu aygıt sürücüsü risk altında olabilir.|
|Bir işlem sınırı|Gibi bir uzak yordam çağrısı (RPC), paylaşılan bellek veya diğer işlem arası iletişim (IPC) mekanizmaları risk altında olabilir yerel sistem üzerinde çalışan başka bir işlemden güvenilmeyen verileri alan bir uygulama.|
|Kuşatma sınır|Kuşatma dışında güvenilmeyen verileri alır (örneğin, Intel SGX) güvenli kuşatma içinde yürüten bir uygulama risk altında olabilir.|
|Dil sınır|Yorumlar uygulama veya tam zamanında (JIT) derler ve yazılmış güvenilmeyen kod yürüten bir üst düzey dil risk altında olabilir.|

Güven sınırları belirleyip kurgusal yürütme yan kanal güvenlik açıklarına olası örneklerini gidermek için saldırı yüzeyini kodu gözden geçirmelisiniz kullanıma sunulan saldırı yüzeyini yukarıdakilerden herhangi biri için olan uygulamalar. Uzak ağ protokolleri gibi uzak saldırı yüzeylerini maruz güven sınırları kurgusal yürütme yan kanal güvenlik açıklarına risk için sergilemiştir değil olduğunu unutulmamalıdır.

## <a name="potentially-vulnerable-coding-patterns"></a>Savunmasız kodlama desenleri

Kurgusal yürütme yan kanal güvenlik açıklarına söz konusu kümelerdeki birden çok kodlama desenleri ortaya çıkabilir. Bu bölümde, savunmasız kodlama desenleri açıklar ve her biri için örnekler sağlar, ancak bu Temalar çeşidi olabileceğini tanınması gereken. Bu nedenle, geliştiriciler, örnekler ve kapsamlı bir liste tüm savunmasız kodlama düzeni olarak değil, bu desenleri yararlanmak için önerilir. Yazılım şu anda mevcut bellek güvenlik açıklarının aynı sınıfları ayrıca kurgusal boyunca mevcut olabilir ve sırası yolları dahil olmak üzere ancak bunlarla sınırlı olmamak arabellek taşmaları, yürütme işlemleri erişir, ilk değeri atanmamış bellek kullanımı, türü dizi karışıklık ve benzeri. Saldırganlar, mimari yolları boyunca bellek emniyet açıklardan yararlanmak için kullanabileceğiniz aynı temelleri kurgusal yollarını da uygulanabilir.

Genel olarak, koşullu ifade, denetlenmesi veya daha az güvenilir bir bağlam tarafından etkileyen veriler üzerinde çalıştığında kurgusal yürütme yan kanal ilgili koşullu dalı misprediction ortaya çıkabilir. Örneğin, bu koşullu ifadeler kullanılan içerebilir `if`, `for`, `while`, `switch`, veya Üçlü deyimleri. Her deyim için derleyici CPU, ardından çalışma zamanında dal hedefi tahmin koşullu bir dal oluşturabilir.

Her örnek için bir geliştirici bir risk azaltma önünde bir engel burada neden olabilirdi "SPEKÜLASYON ENGELİ" ifadesini içeren bir açıklama eklenir. Bu bölümde daha ayrıntılı aşamadaki risk azaltmalarını temel ele alınmıştır.

## <a name="speculative-out-of-bounds-load"></a>Kurgusal işlemleri yükleme

Bu kategori, kodlama desenleri işlemleri kurgusal bir müşteri adayları bir koşullu dalı misprediction içerir bellek erişimi.

### <a name="array-out-of-bounds-load-feeding-a-load"></a>Dizi işlemleri yük yük besleme

CVE-2017-5753 (sınırları atlama denetlemek) için başlangıçta açıklandığı gibi güvenlik açığı kodlama düzeni bu kodlama modelidir. Bu makalenin arka plan ayrıntılı bu deseni açıklar.

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

Benzer şekilde, yük, sonlandırma aşan bir döngü ile birlikte oluşabilir bir dizi işlemleri nedeniyle bir misprediction koşul. Bu örnekte, koşullu dalı ilişkili `x < buffer_size` ifade ve yanlış tahmin speculatively gövdesi yürütme `for` ne zaman döngü `x` büyüktür veya eşittir `buffer_size`, bu nedenle imzalanmayarak kurgusal bir işlemleri yükleyin.

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

### <a name="array-out-of-bounds-load-feeding-an-indirect-branch"></a>Dizi işlemleri yük dolaylı bir dal besleme

Bu kodlama düzeni burada koşullu dalı misprediction açabilir. durum içerir. bir işlev işaretçileri sonra hangi müşteri adaylarını dolaylı bir hedef dala yönelik bir dizi için erişim işlemleri işlemleri okundu. Aşağıdaki kod parçacığını bu gösteren bir örnek sağlar.

Bu örnekte, güvenilmeyen ileti tanımlayıcı DispatchMessage sağlanır `untrusted_message_id` parametresi. Varsa `untrusted_message_id` olduğu küçüktür `MAX_MESSAGE_ID`, işlev işaretçileri, bir dizide dizine ve dallanma kullanılırsa karşılık gelen dal hedefi. Bu kod mimari güvenlidir, ancak CPU koşullu bir dal yanlış tahminlerinin, neden `DispatchTable` tarafından dizinlenen `untrusted_message_id` büyüktür veya eşittir, değer olduğunda `MAX_MESSAGE_ID`, bu nedenle önüne bir işlemleri erişim. Bu kurgusal yürütmeyi speculatively yürütülen kod bağlı olarak bilgileri açığa çıkmasına neden olabilir dizinin sınırları ötesinde türetilmiş bir dal hedef adresinden neden olabilir.

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

Bir dizinin işlemleri durum başka bir yük besleme yük bu koşul ayrıca bir misprediction nedeniyle, sonlandırma koşulu aşan bir döngü ile birlikte ortaya çıkabilir.

### <a name="array-out-of-bounds-store-feeding-an-indirect-branch"></a>Dizi işlemleri depolamak dolaylı bir dal besleme

Yük bir dolaylı dal hedefi etkilemek önceki örnekte bir kurgusal nasıl işlemleri gösterilmiştir, ancak aynı zamanda mümkündür bir işlev işaretçisi veya dönüş adresi gibi bir dolaylı dal hedefi değiştirme işlemleri depolayın. Kurgusal yürütmeyi bu büyük olasılıkla bir saldırgan tarafından belirtilen adresten açabilir.

Bu örnekte, güvenilmeyen bir dizin aracılığıyla geçirilen `untrusted_index` parametresi. Varsa `untrusted_index` öğe sayısı'dan küçük `pointers` dizi (256 öğeleri) ve ardından sağlanan işaretçi değeri `ptr` yazılan `pointers` dizisi. Bu kod mimari güvenlidir, ancak CPU koşullu bir dal yanlış tahminlerinin, neden `ptr` yığın tarafından ayrılan sınırlarının ötesine speculatively yazılan `pointers` dizisi. Bu dönüş adresi kurgusal Bozulması neden olabilir `WriteSlot`. Bir saldırganın değerini kontrol edebilirsiniz, `ptr`, rastgele bir kurgusal yürütmeyi neden mümkün olabilir ne zaman adres `WriteSlot` kurgusal yol boyunca döndürür.

```cpp
unsigned char WriteSlot(unsigned int untrusted_index, void *ptr) {
    void *pointers[256];
    if (untrusted_index < 256) {
        // SPECULATION BARRIER
        pointers[untrusted_index] = ptr;
    }
}
```

Benzer şekilde, adlı bir işlev işaretçisi yerel bir değişken, `func` speculatively adresini değiştirmek mümkün olabilir, yığında ayrılan, `func` koşullu dalı misprediction oluştuğunda ifade eder. İşlev işaretçisi aracılığıyla çağrıldığında bir rastgele adresinden kurgusal yürütmeyi sonuçlanabilir.

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

Bu örneklerin her ikisi kurgusal değişikliği yığın ayırma dolaylı dal işaretçiler içeren unutulmamalıdır. Genel değişkenler, yığın tarafından ayrılan bellek ve hatta salt okunur bellek üzerinde bazı CPU'yu kurgusal değişikliği de meydana gelebilir mümkündür. Yığın tarafından ayrılan bellek için Visual C++ derleyicisi zaten speculatively yığın ayırma dolaylı dal hedefi gibi yerel değişkenler arabellekler için bir güvenlik tanımlama bilgisi bitişik yerleştirilir olacak şekilde yeniden sıralayarak değiştirmek daha zor hale getirmek için gerekli adımları gerçekleştirir. parçası [/GS](https://docs.microsoft.com/cpp/build/reference/gs-buffer-security-check) derleyici güvenlik özelliği.

## <a name="speculative-type-confusion"></a>Kurgusal türü karışıklığı

Bu kategori, kurgusal türü karışıklığa ortaya çıkmasına neden veren desenleri kodlama ile ilgilidir. Bu durum, bellek kurgusal yürütme sırasında hatalı bir tür mimari olmayan bir yol kullanılarak erişilen oluşur. Koşullu dalı misprediction hem kurgusal deposu atlama olabilecek bir kurgusal türü karışıklığa neden olabilir.

Kurgusal deposu atlama için bu burada bir derleyici birden fazla değişken için yığın konumunu kullanır senaryolarda oluşabilir. Bunun nedeni, mimari türünde bir değişken deposu `A` , böylece yük türü izin vererek atlanmasına `A` değişkeni atanmadan önce speculatively yürütülecek. Daha önce depolanan değişken farklı türde ise, bu kurgusal türü Karışıklığı önlemek için bir koşul oluşturabilirsiniz.

Koşullu dalı misprediction için aşağıdaki kod parçacığı tanımlamak için kullanılacak kurgusal türü karışıklık verebilirsiniz farklı koşullar gelmek üzere.

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

### <a name="speculative-type-confusion-leading-to-an-out-of-bounds-load"></a>Kurgusal türü Karışıklığı önlemek için önde gelen bir yükleme işlemleri

Bu kodlama düzeni burada kurgusal türü karışıklık sonuçlanabilir çalışması içerir bir işlemleri veya burada yüklenen değer akışları sonraki yük adresi türü yanıltıcı alan erişimi. Bu dizi işlemleri kodlama desenine benzer ancak alternatif yukarıda da gösterildiği gibi sıralı kodlama ile bildirilen. Bu örnekte, bir saldırıyı gerçekleştiren bağlamı yürütülecek victim bağlam neden olabilecek `ProcessType` birden çok kez türünde bir nesne ile `CType1` (`type` alan eşittir `Type1`). Bu, ilk koşullu dalı eğitim etkisi olmayacak `if` deyimini çekildiği tahmin değil. Saldırıyı gerçekleştiren bağlamı daha sonra yürütülecek victim bağlam neden `ProcessType` türünde bir nesne ile `CType2`. İlk koşul dallandırma yaparsanız bu bir kurgusal türü kullanıcılarda kafa karışıklığına neden olabilir `if` ifade yanlış tahminlerinin ve gövdesini yürütür `if` deyimi, bu nedenle türünde bir nesne atama `CType2` için `CType1`. Bu yana `CType2` küçük olduğuna `CType1`, bellek erişimi `CType1::field2` sonucunda bir kurgusal işlemleri, gizli verileri yükler. Bu değer bir yük içinde kullanılır `shared_buffer` hangi oluşturabilirsiniz gözlemlenebilir bir yan etkileri gibi dizi ile örnekte açıklanan önceden işlemleri.

### <a name="speculative-type-confusion-leading-to-an-indirect-branch"></a>Dolaylı bir dala baştaki kurgusal türü karışıklığı

Bu kodlama düzeni kurgusal türü karışıklık kurgusal yürütme sırasında güvenli olmayan bir dolaylı dalda burada sonuçlanabilir çalışması içerir. Bu örnekte, bir saldırıyı gerçekleştiren bağlamı yürütülecek victim bağlam neden olabilecek `ProcessType` birden çok kez türünde bir nesne ile `CType2` (`type` alan eşittir `Type2`). Bu ilk koşullu dalı eğitim etkisi olacaktır `if` alınmasını deyimi ve `else if` deyimi değil gerçekleştirilecek. Saldırıyı gerçekleştiren bağlamı daha sonra yürütülecek victim bağlam neden `ProcessType` türünde bir nesne ile `CType1`. İlk koşul dallandırma yaparsanız bu bir kurgusal türü kullanıcılarda kafa karışıklığına neden olabilir `if` deyimi tahmin geçen ve `else if` deyimi değil çekildiği tahmin böylece gövdesi yürütülürken `else if` ve türündebirnesneatama`CType1` için `CType2`. Bu yana `CType2::dispatch_routine` alanı ile çakışıyor `char` dizi `CType1::field1`, bu kurgusal bir dolaylı dalda bir istenmeyen dal hedefine neden olabilir. Saldırıyı gerçekleştiren bağlam bayt değerleri denetleyemeyeceğinizi `CType1::field1` dizi, bunlar olabilir dal hedef adresi denetleyebilirsiniz.

## <a name="speculative-uninitialized-use"></a>Kurgusal başlatılmamış kullanın

Bu kategori, kodlama desenleri, kurgusal yürütmeyi burada ve ilk değeri atanmamış bellek erişim sonraki yük ya da dolaylı dal akışa kullanma senaryoları kapsar. Bu kodlama desenleri için açıklardan olacak şekilde bir saldırganın denetlemek ya da atayamayacağına içinde kullanılıyor bağlam tarafından başlatılan olmadan kullanılan bellek içeriğini etkilemek olması gerekir.

### <a name="speculative-uninitialized-use-leading-to-an-out-of-bounds-load"></a>Kurgusal başlatılmamış kullanmak için önde gelen bir yükleme işlemleri

Kurgusal bir başlatılmamış kullanmak olası açabilir bir işlemleri bir saldırgan tarafından denetlenen değerini kullanarak yükleyin. Değerini aşağıdaki örnekte `index` atanan `trusted_index` mimari yazmalar ve `trusted_index` ya da eşit olduğu varsayılır `buffer_size`. Ancak, derleyici tarafından üretilen kod bağlı olarak, bir kurgusal deposu atlama yükü sağlayan oluşabilir mümkündür `buffer[index]` ve atama için önceden yürütmek için bağımlı ifadeler `index`. Bu meydana gelirse, başlatılmamış bir değer `index` uzaklık olarak kullanılacak `buffer` işlemleri hassas bilgileri okuyun ve bu bağımlı yükünü yan kanalımızdan üzerinden iletmek bir saldırgan sağlayabilir `shared_buffer` .

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

### <a name="speculative-uninitialized-use-leading-to-an-indirect-branch"></a>Dolaylı bir dala baştaki kurgusal başlatılmamış kullanın

Kurgusal bir başlatılmamış kullanın, burada dal hedefi bir saldırgan tarafından denetlenir dolaylı bir dala potansiyel olarak açabilir. Aşağıdaki örnekte `routine` ya da atanan `DefaultMessageRoutine1` veya `DefaultMessageRoutine` değerine göre `mode`. Mimari yola göre bu sonuçlanır `routine` önüne dolaylı dal her zaman başlatılmış. Derleyici tarafından üretilen kod bağlı olarak, bir kurgusal deposu atlama aracılığıyla dolaylı dal izin veren ancak oluşabilir `routine` speculatively atamaya önüne yürütülecek `routine`. Bu meydana gelirse, bir saldırganın saldırgan etkilemek veya başlatılmamış değerini kontrol varsayılarak bir rastgele adresinden speculatively yürütülecek mümkün olabilir `routine`.

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

Kurgusal yürütme yan kanal güvenlik açıklarına kaynak koduna değişiklikleri yaparak azaltılabilir. Bu değişiklikleri ekleyerek gibi belirli bir güvenlik açığı örneklerini Azaltıcı ekleyebileceği bir *Spekülasyon engeli*, veya hassas bilgilerin erişilemez kurgusal sağlamak için bir uygulama tasarımını değişiklikler yaparak yürütme.

### <a name="speculation-barrier-via-manual-instrumentation"></a>Spekülasyon engeli aracılığıyla el ile izleme

A *Spekülasyon engeli* mimari olmayan yol ilerlemesini kurgusal yürütmeyi önlemek için bir geliştirici tarafından el ile girilebilir. Örneğin, bir geliştirici bir Spekülasyon engeli tehlikeli bir kodlama düzeni önce bir koşullu blok, blok başına (sonra koşullu bir dal) ya da gövdesi ekleyebilirsiniz veya bir sorun ilk yüklenmesinden önce. Bu, bir koşullu dalı misprediction tehlikeli kod yürütme seri hale getirme mimari olmayan bir yola yürütülmesini engeller. Spekülasyon engeli dizisi, aşağıdaki tabloda açıklandığı gibi donanım mimarisi tarafından farklıdır:

|Mimari|CVE-2017-5753 için iç Spekülasyon engeli|CVE-2018-3639 için iç Spekülasyon engeli|
|----------------|----------------|----------------|
|x86/x64|_mm_lfence()|_mm_lfence()|
|ARM|şu anda kullanılamıyor|__dsb(0)|
|ARM64|şu anda kullanılamıyor|__dsb(0)|

Örneğin, aşağıdaki kod desenini kullanarak azaltılabilir `_mm_lfence` aşağıda gösterildiği gibi iç.

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

### <a name="speculation-barrier-via-compiler-time-instrumentation"></a>Spekülasyon engeli aracılığıyla derleme zamanı izleme

Visual Studio 2017 (sürüm 15.5.5 ile başlayarak) Visual C++ derleyicisi için destek içerir `/Qspectre` ilgili CVE-2017-5753 için otomatik olarak bir Spekülasyon engeli sınırlı sayıda savunmasız kodlama desenleri için ekleyen bir anahtar. Belgelerine [/qspectre](https://docs.microsoft.com/en-us/cpp/build/reference/qspectre) bayrağı kullanım ve etkileri hakkında daha fazla bilgi sağlar. Bu bayrak tüm savunmasız kodlama desenleri kapsamaz ve bu nedenle geliştiriciler üzerinde bu sınıf, güvenlik açığı için kapsamlı bir risk azaltma olarak doğrulamamalısınız unutulmaması önemlidir.

### <a name="masking-array-indices"></a>Dizi dizinleri maskeleme

Burada bir kurgusal'ı işlemleri yük durumlarda oluşabilir dizi dizini kesin hem de mimari ve mimari olmayan yolunda dizi dizini açıkça bağlı mantıksal ekleyerek sınırlanmış. Bir dizi ikinin üssü için uygun bir boyut için ayrılabilir, örneğin, ardından basit maskesi tanıtılabilir. Bu olduğu varsayılır, aşağıdaki örnekte gösterilmiştir `buffer_size` ikinin üssü için hizalanır. Bu sağlar `untrusted_index` olduğundan her zaman küçüktür `buffer_size`bile koşullu dalı misprediction gerçekleşir ve `untrusted_index` değerinden büyük veya ona eşit bir değeri geçirildi `buffer_size`.

Burada gerçekleştirilen dizin maskeleme kurgusal deposu atlama derleyici tarafından oluşturulan kodu bağlı olarak tabi olabilir, bu unutulmamalıdır.

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

### <a name="removing-sensitive-information-from-memory"></a>Hassas bilgileri bellekten kaldırılıyor

Kurgusal yürütme yan kanal güvenlik açıklarına azaltmak için kullanılabilecek başka bir teknik, hassas bilgileri bellekten kaldırmaktır. Yazılım geliştiricileri kurgusal yürütme sırasında hassas bilgileri erişilebilir değil, kendi uygulama yeniden fırsatları bakabilirsiniz. Bu hassas bilgileri ayrı işlemlerde yalıtmak için bir uygulama tasarımını Düzenleyicisi tarafından gerçekleştirilebilir. Örneğin, bir web tarayıcı uygulaması ayrı işlemlerde, bu nedenle bir işlem kurgusal yürütmeyi çıkış noktaları arası verilerine erişebilir olmasını önleyen içine her web kaynağı ile ilişkili verileri yalıtmak deneyebilirsiniz.

## <a name="see-also"></a>Ayrıca Bkz.

[Kurgusal yürütme yan kanal güvenlik açıklarını azaltmaya yönelik kılavuz](https://portal.msrc.microsoft.com/security-guidance/advisory/ADV180002)<br/>
[Kurgusal yürütme yan kanal donanım güvenlik açıkları azaltma](https://blogs.technet.microsoft.com/srd/2018/03/15/mitigating-speculative-execution-side-channel-hardware-vulnerabilities/)
