---
title: Kurgusal yürütme yan kanalları C++ Geliştirici Kılavuzu | Microsoft Docs
ms.custom: ''
ms.date: 05/21/2018
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
author: mamillmsft
ms.author: mikeblome
ms.workload:
- cplusplus
ms.openlocfilehash: 515e2223e67d86da12488d9880a1a0a258fc4bdf
ms.sourcegitcommit: 4b2c3b0c720aef42bce7e1e5566723b0fec5ec7f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2018
---
# <a name="c-developer-guidance-for-speculative-execution-side-channels"></a>Kurgusal yürütme yan kanalları C++ Geliştirici Kılavuzu

Bu makalede, geliştiricilerin tanımlama ve C++ yazılım kurgusal yürütme yan kanal donanım güvenlik açıkları Azaltıcı yardımcı olmak kılavuz içerir. Bu güvenlik açıklarından hassas bilgileri güven sınırları boyunca çıkartabilir ve yönergeleri kurgusal, sipariş yürütülmesi destekleyen işlemcileri üzerinde çalıştırılan yazılım etkileyebilir. Bu sınıf güvenlik açıklarının Ocak, 2018 açıklanan ilk ve ek arka plan oldu ve kılavuz bulunabilir [Microsoft'un güvenlik önerisi](https://portal.msrc.microsoft.com/en-US/security-guidance/advisory/ADV180002).

Bu makalede tarafından sağlanan yönergeleri sınıfları tarafından temsil edilen güvenlik açıklarının ilişkilidir:

1. CVE-2017-5753, Spectre değişken 1 olarak da bilinir. Bu donanım güvenlik açığı sınıfı koşullu dal misprediction sonucunda ortaya çıkan kurgusal yürütme nedeniyle ortaya çıkabilir yan kanalları ilgilidir. Visual Studio (15.5.5 sürümünden başlayarak) 2017'de Visual C++ Derleyici desteği içeren `/Qspectre` savunmasız olabilecek kodlama desenleri sınırlı sayıda için derleme zamanı azaltma sağlayan anahtar ilgili 2017 CVE 5753 için. Belgelerine [/Qspectre](https://docs.microsoft.com/en-us/cpp/build/reference/qspectre) bayrağı kendi etkiler ve kullanımı hakkında daha fazla bilgi sağlar.

2. CVE-2018-olarak da bilinen 3639, [kurgusal deposu atlama (SSB)](https://aka.ms/sescsrdssb). Bu donanım güvenlik açığı sınıfı yükünün bellek erişimi misprediction sonucunda bağımlı deposu öncesinde kurgusal yürütme nedeniyle ortaya çıkabilir yan kanalları ilgilidir.

Kurgusal yürütme yan kanal güvenlik açıkları erişilebilir giriş başlıklı sunusunda bulunabilir [Spectre çalışması ve Meltdown](https://www.youtube.com/watch?v=_4O0zMW-Zu4) bu sorunları bulunan araştırma takımlar biri tarafından.

## <a name="what-are-speculative-execution-side-channel-hardware-vulnerabilities"></a>Speculative yürütme yan kanal donanım güvenlik açıkları nelerdir?

Modern CPU yaparak daha yüksek derece performansını sağlamak kurgusal ve sıra dışı yürütme yönergeleri kullanın. Örneğin, bu genellikle CPU speculatively tahmin edilen şube hedef yönergeleri yürütülmeye başlamaya için sağlayan dalları (koşullu ve dolaylı) hedefi tahmin ederek çalışmasını gerçekleştirilir gerçek şube hedef olana kadar bu nedenle bir kabini önleme çözümlendi. CPU, daha sonra bir misprediction oluştuğunu bulur, durumunda, tüm speculatively hesaplanmıştır makine durumunun atılır. Bu mimari görünür hiçbir mispredicted Spekülasyon etkilerini olmasını sağlar.

Kurgusal yürütme mimari görünürlük durumunu etkilemez, ancak CPU tarafından kullanılan çeşitli önbellekleri gibi mimari olmayan durumda fazlalık izlemeleri bırakılabilir. Bu kalan izleri yan kanal güvenlik açıklarına neden veren kurgusal yürütme olur. Bu daha iyi anlamak için CVE 2017 5753 (denetleyin sınırları atlama) örneği sağlayan aşağıdaki kod parçası göz önünde bulundurun:

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

Bu örnekte, `ReadByte` olan bir arabellek, bir arabellek boyutuna ve dizin o arabelleğine sağlanan. Dizin parametresi tarafından belirtilen `untrusted_index`, daha az tarafından sağlanan yönetici olmayan bir işlem gibi ayrıcalıklı bağlamı. Varsa `untrusted_index` olan değerinden `buffer_size`, o dizini karakterinde okuma sonra `buffer` ve başvurulan bellek paylaşılan bölge içinde dizin için kullanılan `shared_buffer`. 

Sağlanır gibi bir mimari açısından bu kodu sırası mükemmel güvenli `untrusted_index` her zaman açık değerinden `buffer_size`. Ancak, kurgusal yürütme varlığında CPU koşullu dal mispredict ve eğer gövdesi yürütme mümkündür deyimi bile `untrusted_index` büyük veya eşit `buffer_size`. Bu gruplarındaki sonucu olarak, CPU sınırları from beyond byte speculatively okuyabilirsiniz `buffer` (hangi gizli olabilir) ve sonra bir sonraki yük adresini işlem için bayt değeri kullanabilir `shared_buffer`. 

CPU sonunda bu misprediction algılar, ancak kalan yan etkileri sınırları dışında okuma bayt değeri hakkındaki bilgileri ortaya CPU önbelleği kalabilir `buffer`. Bu yan etkileri göre daha az algılanabilir ayrıcalıklı içeriği nasıl hızlı bir şekilde yoklama tarafından sistem üzerinde çalışan her önbellek satır içinde `shared_buffer` erişilir. Bunu gerçekleştirmek için atılabilecek adımlar şunlardır:

1. **Çağırma `ReadByte` birden çok kez `untrusted_index` olan değerinden `buffer_size`** . Saldırıyı gerçekleştiren bağlam çağrılacak kurban bağlam neden olabilir `ReadByte` (örneğin RPC), şube göstergesi olduğu gibi değil-taken olarak olmasını eğitilmiş `untrusted_index` olan değerinden `buffer_size`.

2. **Tüm önbellek satırlarında flush `shared_buffer`** . Saldırıyı gerçekleştiren bağlam tüm başvurulan bellek paylaşılan bölgede önbellek satırları flush gerekir `shared_buffer`. Bellek bölge paylaşılan olduğundan, bu basittir ve iç bilgileri gibi kullanılarak gerçekleştirilebilir `_mm_clflush`.

3. **Çağırma `ReadByte` ile `untrusted_index` daha büyük olan `buffer_size`** . Çağrılacak kurban bağlam saldırıyı gerçekleştiren bağlam neden `ReadByte` sağlayacak şekilde yanlış dalın değil alınıp tahmin. İf gövdesi speculatively yürütmek için işlemciyi engelleme ile Bu nedenler `untrusted_index` daha büyük olan `buffer_size`, böylece başında out-of-bounds okuma için `buffer`. Sonuç olarak, `shared_buffer` out-of-bounds, böylece CPU tarafından yüklenecek ilgili önbellek satırı neden okundu potansiyel olarak gizli bir değer kullanarak dizinlenir.

4. **Her önbellek satırı okuma `shared_buffer` hangi en hızlı erişilir görmek için**. Her önbellek satırı saldırıyı gerçekleştiren bağlam okuyabilirsiniz `shared_buffer` ve önemli ölçüde diğerlerinden daha hızlı yükler önbellek satırı algılayabilir. Adım 3'tarafından getirdiğiniz muhtemelen önbellek satırı budur. Bu örnekte bayt değeri ve önbellek satırı arasında bir 1:1 ilişki olduğundan, bu saldırganın out-of-bounds okundu bayt gerçek değeri Infer sağlar.

Yukarıdaki adımları CVE 2017 5753 örneği yararlanmasını ile birlikte temizleme + yeniden bilinen bir yöntem kullanarak bir örnek sağlar.

## <a name="what-software-scenarios-can-be-impacted"></a>Hangi yazılım senaryolarını etkilenebilir?

Gibi bir işlemi kullanarak güvenli yazılım geliştirme [güvenlik geliştirme yaşam döngüsü](https://www.microsoft.com/en-us/sdl/) (SDL), geliştiricilerin uygulamalarında mevcut güven sınırları tanımlamak genellikle gerektirir. Burada bir uygulama ile bir çekirdek modu aygıt sürücüsü olması durumunda yönetici olmayan bir kullanıcı modu işlem veya sistem üzerinde başka bir işlem gibi daha az güvenilir bir bağlam tarafından sağlanan verileri etkileşebilir. yerde bir güven sınırı var. Yeni sınıf kurgusal yürütme yan kanalları içeren güvenlik açıklarının birçok güven sınırları içinde kodu ve verileri bir cihazda yalıtmak mevcut yazılım güvenlik modelleri için geçerlidir. 

Aşağıdaki tabloda, burada geliştiriciler oluşan bu güvenlik açıkları hakkında endişelenmeniz gerekebilir yazılım güvenlik modelleri bir özetini sunar:

|Sınır güven|Açıklama|
|----------------|----------------|
|Sanal makine sınır|Başka bir sanal makineden güvenilmeyen veri almasına ayrı sanal makinelere iş yüklerini ayırma uygulamalar risk altında olabilir.| 
|Çekirdek sınır|Bir yönetici olmayan bir kullanıcı modu işlemden güvenilmeyen verileri alan bir çekirdek modu aygıt sürücüsü risk altında olabilir.| 
|İşlem sınır|Bir uzak yordam çağrısı (RPC), paylaşılan bellek veya diğer arası işlem iletişimi (IPC) mekanizmaları risk altında olabilir gibi yerel sistem üzerinde çalışan başka bir işlem güvenilmeyen verileri alan bir uygulama.|
|Enclave sınır|Güvenilmeyen verilerden enclave dışında alan güvenli bir enclave (örneğin, Intel SGX) içinde yürüten bir uygulama risk altında olabilir.|
|Dil sınır|Yorumlar uygulama veya Just-In-Time (JIT) derler ve yazılan güvenilmeyen kodu yürütür üst düzey bir dil risk altında olabilir.|

Güven sınırları tanımlanmasına ve olası örneklerini kurgusal yürütme yan kanal güvenlik açıkları için saldırı yüzeyini kodu gözden geçirmelidir kullanıma sunulan saldırı yüzeyini Yukarıdakilerden hiçbirine sahip uygulamalar. Uzak ağ protokolleri gibi uzaktan saldırı yüzeyleri maruz güven sınırları kurgusal yürütme yan kanal güvenlik açıklarına risk ortaya konmuş olmayan olduğunu unutulmamalıdır.

## <a name="potentially-vulnerable-coding-patterns"></a>Savunmasız olabilecek kodlama desenleri

Kurgusal yürütme yan kanal güvenlik açıkları, birden çok kodlama desenleri gruplarındaki sonucu olarak ortaya çıkabilir. Bu bölümde savunmasız olabilecek kodlama desenleri açıklar ve her biri için örnekler sağlar, ancak bu temaları çeşidi bulunabilir tanınması. Bu nedenle, geliştiriciler bu desenleri tüm savunmasız olabilecek kodlama desenleri kapsamlı bir listesi değil de, örnekler olarak almak için önerilir.

Genel olarak, koşullu ifade, denetlenmesi veya daha az güvenilir bir bağlamdan Etkileyenler verileri üzerinde çalıştığında kurgusal yürütme yan kanalları ilgili koşullu dal misprediction ortaya çıkabilir. Örneğin, bu kullanılan koşullu ifadeler içerebilir `if`, `for`, `while`, `switch`, veya Üçlü deyimleri. Her bu deyimleri için derleyici CPU sonra şube hedef çalışma zamanında tahmin koşullu bir dal oluşturabilir.

Her örneğin bir geliştirici bir azaltma olarak bir engel burada tanıtmak "SPEKÜLASYON engel" tümceciği birlikte bir açıklama eklenir. Bu bölümde daha ayrıntılı Azaltıcı Etkenler üzerinde ele alınmıştır.

## <a name="speculative-out-of-bounds-load"></a>Out-of-bounds kurgusal yükleme

Bu kategori desenleri kodlama out-of-bounds kurgusal bir müşteri adayları koşullu dal misprediction içerir bellek erişimi.

### <a name="array-out-of-bounds-load-feeding-a-load"></a>Dizi out-of-bounds yük yükü besleme

Bu kodlama düzeni CVE 2017 5753 (denetleyin sınırları atlama) için ilk olarak açıklanan güvenlik açığı kodlama düzeni ' dir. Bu makalenin arka plan ayrıntılı bu deseni açıklar.

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

Benzer şekilde, kendi sonlandırma aşan bir döngü ile birlikte yük oluşabilir out-of-bounds dizi misprediction nedeniyle koşul. Bu örnekte, koşullu dal ilişkili `x < buffer_size` ifadesi mispredict ve speculatively gövdesini yürütmek `for` ne zaman döngü `x` büyüktür veya eşittir `buffer_size`, böylece sonuçta ortaya çıkan bir kurgusal içinde Out-of-bounds yükleyin.

```cpp
// A pointer to a shared memory region of size 1MB (256 * 4096)
unsigned char *shared_buffer;

unsigned char ReadBytes(unsigned char *buffer, unsigned int buffer_size) {
    for (unsigned int x = 0; x < buffer_size; x++) {
        // SPECULATION BARRIER
        unsigned char value = buffer[untrusted_index];
        return shared_buffer[value * 4096];
    }
}
```

### <a name="array-out-of-bounds-load-feeding-an-indirect-branch"></a>Dizi out-of-bounds yük dolaylı bir dalı besleme

Bu kodlama düzeni burada koşullu dal misprediction açabilir çalışması içerir bir hedefe dolaylı bir dalı sonra hangi müşteri adaylarına adres işlev işaretçileri dizisi erişimi out-of-bounds out-of-bounds okundu. Aşağıdaki kod parçacığında bu gösteren bir örnek sağlar. 

Bu örnekte, güvenilmeyen İleti tanımlayıcısı DispatchMessage sağlanır `untrusted_message_id` parametresi. Varsa `untrusted_message_id` olan değerinden `MAX_MESSAGE_ID`, bir işlev işaretçileri diziye dizini oluşturmak ve dallanma için kullanılan sonra karşılık gelen şube hedef. Bu kod mimari güvenlidir, ancak koşullu dal CPU mispredicts, neden `DispatchTable` tarafından dizinlenen `untrusted_message_id` değerinden büyük veya eşit değerini olduğunda `MAX_MESSAGE_ID`, böylece başında bir out-of-bounds erişim. Bu speculatively yürütülen koduna bağlı olarak bilgilerin açığa çıkmasına neden olabilir dizinin sınırlarının türetilmiş bir şube hedef adresinden kurgusal yürütmesinde neden olabilir.

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

Başka bir yük besleme out-of-bounds bir dizi durumu ile yük bu koşul ayrıca bir misprediction nedeniyle, sonlandırma koşulu aşıyor bir döngü ile birlikte ortaya çıkabilir.

## <a name="speculative-type-confusion"></a>Kurgusal türü karışıklığı

Bu kategori, kurgusal türü karışıklığa neden veren desenleri kodlama ile ilgilidir. Bu durum, yanlış yazıyı mimari olmayan yol kullanılarak kurgusal yürütme sırasında bellek erişilen oluşur. Olası koşullu dal misprediction ve kurgusal deposu atlama kurgusal türü karışıklığa yol açabilir. 

Kurgusal deposu atlama için bu burada derleyici birden çok tür değişkenleri için yığın konumunu kullanır senaryolarda oluşabilir. Bunun nedeni, türünde bir değişken mimari deposu `A` , böylece yük türü sağlar atlanmasına `A` değişkeni atanmadan önce speculatively yürütülecek. Daha önce depolanan değişken farklı bir tür ise, bu kurgusal türü Karışıklığı önlemek için bir koşul oluşturabilirsiniz.

Koşullu dal misprediction için aşağıdaki kod parçacığını tanımlamak için kullanılan kurgusal türü karışıklığı verebilirsiniz farklı koşullar yükselmeye için.

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

### <a name="speculative-type-confusion-leading-to-an-out-of-bounds-load"></a>Kurgusal türü karışıklığa neden bir out-of-bounds yükleme

Bu kodlama düzeni burada kurgusal türü Karışıklığı önlemek neden çalışması içerir bir out-of-bounds veya burada yüklenen değer Akışları'nı bir sonraki yük adresi türü kafası alan erişimi. Bu dizi out-of-bounds kodlama düzeni benzer ancak sırası yukarıda gösterildiği gibi kodlama alternatif aracılığıyla bildirilmiş. Bu örnekte, bir saldırıyı gerçekleştiren bağlamı yürütmek kurban bağlam neden olabilecek `ProcessType` birden çok kez türünde bir nesne ile `CType1` (`type` alandır eşit `Type1`). İlk kez koşullu dal eğitim etkisini sahip `if` deyimi çekildiği tahmin değil. Saldırıyı gerçekleştiren bağlam sonra yürütülecek kurban bağlam neden olabilir `ProcessType` türünde bir nesne ile `CType2`. İlk koşul dal durumunda bir kurgusal türü karışıklığa yol açabilir `if` deyimi mispredicts ve gövdesi yürütülür `if` deyimi, böylece türünde bir nesne atama `CType2` için `CType1`. Bu yana `CType2` değerinden küçük `CType1`, bellek erişimi `CType1::field2` bir kurgusal sonucunda out-of-bounds gizli verileri yükler. Bu değer daha sonra bir yükü kullanılır `shared_buffer` hangi oluşturabilirsiniz observable yan etkileri gibi diziye sahip örnek açıklanan önceden out-of-bounds.

### <a name="speculative-type-confusion-leading-to-an-indirect-branch"></a>Dolaylı bir dalı baştaki kurgusal türü Karışıklığı önlemek için

Bu kodlama düzeni kurgusal türü karışıklığı kurgusal yürütme sırasında güvenli olmayan bir dolaylı dalında burada sonuçlanabilir çalışması içerir. Bu örnekte, bir saldırıyı gerçekleştiren bağlamı yürütmek kurban bağlam neden olabilecek `ProcessType` birden çok kez türünde bir nesne ile `CType2` (`type` alandır eşit `Type2`). İlk kez koşullu dal eğitim etkisini sahip `if` gerçekleştirilecek deyimi ve `else if` değil gerçekleştirilecek deyimi. Saldırıyı gerçekleştiren bağlam sonra yürütülecek kurban bağlam neden olabilir `ProcessType` türünde bir nesne ile `CType1`. İlk koşul dal durumunda bir kurgusal türü karışıklığa yol açabilir `if` deyimi tahmin gerçekleştirilecek ve `else if` deyimi değil çekildiği tahmin böylece gövdesini yürütme `else if` ve türündebirnesneatama`CType1` için `CType2`. Bu yana `CType2::dispatch_routine` alanı ile çakışıyor `char` dizi `CType1::field1`, bu istenmeyen şube hedefe kurgusal bir dolaylı dalında sonuçlanabilir. Bayt değerleri saldırıyı gerçekleştiren bağlamını kontrol edebilirsiniz `CType1::field1` dizi, bunlar olabilir şube hedef adres denetleyebilir.

## <a name="speculative-uninitialized-use"></a>Kurgusal başlatılmamış kullanın

Bu kategori desenleri kodlama burada kurgusal yürütme başlatılmamış bellek erişmek ve bir sonraki yük ya da dolaylı şube akışına kullanmak senaryolar içerir. Kodlama bu desenleri Etkilenme olmasını bilgi için bir saldırganın denetlemek veya anlamlı içinde kullanılan bağlam tarafından başlatılmış olmadan kullanılan bellek içeriğini etkilemek gerekir.

### <a name="speculative-uninitialized-use-leading-to-an-out-of-bounds-load"></a>Kurgusal başlatılmamış kullanmak için önde gelen bir out-of-bounds yükleme

Kurgusal bir başlatılmamış kullanımı olası açabilir bir out-of-bounds bir saldırganın denetlenen değerini kullanarak yükleyin. Değeri, aşağıdaki örnekte `index` atanan `trusted_index` tüm mimari yollarında ve `trusted_index` küçük veya eşit olduğu varsayılır `buffer_size`. Ancak, derleyici tarafından üretilen kod bağlı olarak, kurgusal deposu atlama yüklerinin veren oluşabilir mümkündür `buffer[index]` ve atamayı öncesinde yürütmek için bağımlı ifadeler `index`. Bu meydana gelirse, başlatılmamış bir değer `index` olarak uygun kullanılacak `buffer` out-of-bounds hassas bilgileri okuyun ve bu bağımlı yükünü aracılığıyla yan kanalı üzerinden iletmek bir saldırgan sağlayabilir `shared_buffer` .

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

### <a name="speculative-uninitialized-use-leading-to-an-indirect-branch"></a>Dolaylı bir dalı baştaki kurgusal başlatılmamış kullanın

Kurgusal bir başlatılmamış kullanımı burada şube hedef bir saldırgan tarafından denetlenir dolaylı bir dalı olası neden olabilir. Aşağıdaki örnekte `routine` ya da atanan `DefaultMessageRoutine1` veya `DefaultMessageRoutine` değerine bağlı olarak `mode`. Mimari yolda bu sonuçlanır `routine` dolaylı şube öncesinde her zaman başlatılmış. Derleyici tarafından üretilen kod bağlı olarak, kurgusal deposu atlama aracılığıyla dolaylı şube izin veren ancak oluşabilir `routine` speculatively atamayı öncesinde yürütülecek `routine`. Bu durumda, bir saldırganın saldırgan etkilemek veya başlatılmamış değerini denetlemek varsayılarak speculatively rasgele bir adresinden yürütmek mümkün olabilir `routine`.

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

## <a name="mitigation-options"></a>Azaltma seçenekleri

Kurgusal yürütme yan kanal güvenlik açıkları, kaynak koduna değişiklikler yaparak azaltılabilir. Bu değişiklikler ekleyerek gibi belirli bir güvenlik açığı örneklerini Azaltıcı içerebileceği bir *Spekülasyon engel*, veya hassas bilgileri için erişilemez kurgusal hale getirmek için bir uygulama tasarımını değişiklikler yaparak yürütme.

### <a name="speculation-barrier-via-manual-instrumentation"></a>El ile araçları aracılığıyla Spekülasyon engelle

A *Spekülasyon engel* el ile devam etmeden mimari olmayan bir yol boyunca kurgusal yürütülmesini engellemek için bir geliştirici tarafından eklenebilir. Örneğin, bir geliştirici Spekülasyon engel tehlikeli olabilecek bir kodlama düzeni önce koşullu bir blok, blok başına (sonra koşullu dal) ya da gövdesi ekleyebilirsiniz veya bu tarihten önce sorunu ilk yükleme. Bu yürütme seri hale getirme mimari olmayan bir yola tehlikeli kod yürütülmesini koşullu dal misprediction engeller. Spekülasyon engel dizisi tarafından aşağıdaki tabloda açıklandığı gibi donanım mimarisi tarafından farklıdır:

|Mimari|Spekülasyon engel 2017 CVE 5753 için iç|Spekülasyon engel CVE-2018-3639 için iç|
|----------------|----------------|----------------|
|x86/x64|_mm_lfence()|_mm_lfence()|
|ARM|Şu anda kullanılamıyor|__dsb(0)|
|ARM64|Şu anda kullanılamıyor|__dsb(0)|

Örneğin, aşağıdaki kod düzeni kullanılarak azaltılabilir `_mm_lfence` aşağıda gösterildiği gibi iç.

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

### <a name="speculation-barrier-via-compiler-time-instrumentation"></a>Derleme zamanı araçları aracılığıyla Spekülasyon engelle

Visual Studio (15.5.5 sürümünden başlayarak) 2017'de Visual C++ Derleyici desteği içeren `/Qspectre` Spekülasyon engel savunmasız olabilecek kodlama desenleri sınırlı sayıda için otomatik olarak ekler anahtarı ilgili 2017 CVE 5753 için. Belgelerine [/Qspectre](https://docs.microsoft.com/en-us/cpp/build/reference/qspectre) bayrağı kendi etkiler ve kullanımı hakkında daha fazla bilgi sağlar. Bu bayrak savunmasız olabilecek kodlama desenleri tümünün kapsamaz ve bu nedenle geliştiriciler üzerinde güvenlik açıklarının Bu sınıf için kapsamlı bir azaltma olarak doğrulamamalısınız dikkate almak önemlidir.

## <a name="masking-array-indices"></a>Dizi dizinlerini maskeleme

Burada bir kurgusal'ı out-of-bounds yük durumlarda oluşabilir dizi dizini kesinlikle her iki mimari ve mimari olmayan yola açıkça dizi dizini bağlı mantığı ekleyerek ilişkisindeki. Bir dizi iki üssüne hizalanır bir boyuta ayrılabilen, örneğin, ardından bir basit maskesi tanıtılabilir. Bu olduğu varsayılır, aşağıdaki örnekte gösterilmiştir `buffer_size` iki üssüne hizalanır. Bu sağlar `untrusted_index` olduğu her zaman değerinden `buffer_size`, koşullu dal misprediction gerçekleşse bile ve `untrusted_index` bir değeri sıfırdan büyük veya eşit geçildi `buffer_size`.

Burada gerçekleştirilen dizin maskeleme kurgusal deposu atlama derleyici tarafından üretilen koduna bağlı olarak tabi olabilir unutulmamalıdır.

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

## <a name="removing-sensitive-information-from-memory"></a>Hassas bilgileri bellekten kaldırılıyor

Kurgusal yürütme yan kanal güvenlik açıkları azaltmak için kullanılan başka bir teknik hassas bilgileri bellekten kaldırmaktır. Yazılım geliştiriciler, hassas bilgileri kurgusal yürütme sırasında erişilebilir değil, kendi uygulama yeniden düzenlemeniz fırsatı arayabilirsiniz. Bu ayrı işlemler hassas bilgileri ayırmak için bir uygulama tasarımını yeniden düzenleme tarafından gerçekleştirilebilir. Örneğin, bir web tarayıcı uygulaması olan her web kaynak ayrı işlemler, bu nedenle bir işlemi kurgusal yürütme çıkış noktaları arası verilerine erişebilir olmasını önleyen içine ilişkili verileri yalıtmak deneyebilirsiniz.

## <a name="see-also"></a>Ayrıca Bkz.

[Kurgusal yürütme yan kanal güvenlik açıkları azaltmak için kılavuz](https://portal.msrc.microsoft.com/en-US/security-guidance/advisory/ADV180002)
[kurgusal yürütme yan kanal donanım güvenlik açıkları Azaltıcı](https://blogs.technet.microsoft.com/srd/2018/03/15/mitigating-speculative-execution-side-channel-hardware-vulnerabilities/)