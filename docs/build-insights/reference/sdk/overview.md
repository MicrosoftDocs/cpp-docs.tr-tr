---
title: C++ Build Insights SDK
description: Visual Studio C++ Build Insights SDK'ya genel bakış.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Analyzing
- Relogging
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 126abb0d039227eb269500966d46ef0a729763ee
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323257"
---
# <a name="c-build-insights-sdk"></a>C++ Build Insights SDK

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

C++ Build Insights SDK, C++ Build Insights platformunun üstünde kişiselleştirilmiş araçlar oluşturmanıza olanak tanıyan bir API koleksiyonudur. Bu sayfa, başlamanıza yardımcı olmak için üst düzey bir genel bakış sağlar.

## <a name="obtaining-the-sdk"></a>SDK'nın alınması

Aşağıdaki adımları izleyerek C++ Build Insights SDK'yı NuGet paketi olarak indirebilirsiniz:

1. Visual Studio 2017 ve üzeri, yeni bir C++ projesi oluşturun.
1. Çözüm **Gezgini** bölmesinde, projenize sağ tıklayın.
1. Bağlam menüsünden **NuGet Paketlerini Yönet'i** seçin.
1. Sağ üstte, **nuget.org** paket kaynağını seçin.
1. Microsoft.Cpp.BuildInsights paketinin en son sürümünü arayın.
1. **Yükle'yi**seçin.
1. Lisansı kabul et.

SDK'yı çevreleyen genel kavramlar hakkında bilgi için okumaya devam edin. Ayrıca, SDK'yı kullanan gerçek C++ uygulamalarının örneklerini görmek için resmi [C++ Build Insights örnekleri github deposuna](https://github.com/microsoft/cpp-build-insights-samples) da erişebilirsiniz.

## <a name="collecting-a-trace"></a>İz toplama

MSVC araç zincirinden çıkan olayları analiz etmek için C++ Build Insights SDK'yı kullanmak, önce bir izleme toplamanızı gerektirir. SDK, Windows için Olay İzleme'yi (ETW) temel izleme teknolojisi olarak kullanır. İzleme toplama iki şekilde yapılabilir:

### <a name="method-1-using-vcperf-in-visual-studio-2019-and-above"></a>Yöntem 1: Visual Studio 2019 ve üzeri vcperf kullanarak

1. Open an elevated x64 Native Tools Command Prompt for VS 2019.
1. Aşağıdaki komutu çalıştırın:`vcperf /start MySessionName`
1. Projenizi yapılandırın.
1. Aşağıdaki komutu çalıştırın:`vcperf /stopnoanalyze MySessionName outputTraceFile.etl`

   > [!IMPORTANT]
   > Vcperf ile izinizi durdururken `/stopnoanalyze` komutu kullanın. Normal `/stop` komut tarafından durdurulan izleri çözümlemek için C++ Build Insights SDK'yı kullanamazsınız.

### <a name="method-2-programmatically"></a>Yöntem 2: programlı

İzlemeleri programlı olarak başlatmak ve durdurmak için bu C++ Build Insights SDK izleme toplama işlevlerinden herhangi birini kullanın. **Bu işlev çağrılarını yürüten programın yönetim ayrıcalıkları olmalıdır.** Yalnızca başlatma ve durdurma işlevleri ni idari ayrıcalıklar gerektirir. C++ Build Insights SDK'daki diğer tüm işlevler onlar olmadan yürütülebilir.

### <a name="sdk-functions-related-to-trace-collection"></a>İzleme toplama ile ilgili SDK işlevleri

| İşlev | C++ API | C API |
|--|--|--|
| İzleme başlatma | [Başlangıç Yarışı Oturumu](functions/start-tracing-session.md) | [Başlangıç YarışıSessionA](functions/start-tracing-session-a.md)<br />[Başlangıç OturumuW](functions/start-tracing-session-w.md) |
| İzi durdurma | [StopTracingSession](functions/stop-tracing-session.md) | [StopTracingSessionA](functions/stop-tracing-session-a.md)<br />[StopTracingSessionW](functions/stop-tracing-session-w.md) |
| Bir izlemeyi durdurma ve<br />sonucu hemen analiz etme | [StopAndAnalyzeTracingSession](functions/stop-and-analyze-tracing-session.md) | [StopAndAnalyzeTracingSessionA](functions/stop-and-analyze-tracing-session-a.md)<br />[StopAndAnalyzeTracingSession](functions/stop-and-analyze-tracing-session-w.md) |
| Bir izlemeyi durdurma ve<br />sonucu hemen yeniden kaydetme | [StopAndRelogTracingOturum](functions/stop-and-relog-tracing-session.md) | [StopAndRelogTracingSessionA](functions/stop-and-relog-tracing-session-a.md)<br />[StopAndRelogTracingSessionW](functions/stop-and-relog-tracing-session-w.md) |

İzleyen bölümler, bir çözümlemeyi veya yeniden günlüğe kaydetme oturumunu nasıl yapılandırabileceğinizi gösterir. [StopAndAnalyzeTracingSession](functions/stop-and-analyze-tracing-session.md)gibi birleştirilmiş işlevsellik işlevleri için gereklidir.

## <a name="consuming-a-trace"></a>İzleme yi yontma

Bir ETW izlemeniz olduğunda, açmak için C++ Build Insights SDK'yı kullanın. SDK, araçlarınızı hızlı bir şekilde geliştirmenizi sağlayan bir biçimde olayları size verir. SDK kullanmadan ham ETW izini tüketmenizi önermiyoruz. MSVC tarafından kullanılan olay biçimi belgesiz, büyük yapılarölçeklendirmek için optimize edilmiş ve mantıklı zor. Ayrıca, C++ Build Insights SDK API kararlıyken, ham ETW izleme biçimi önceden haber verilmeden değiştirilebilir.

### <a name="sdk-types-and-functions-related-to-trace-consumption"></a>İzleme tüketimiyle ilgili SDK türleri ve işlevleri

| İşlev | C++ API | C API | Notlar |
|--|--|--|--|
| Olay geri aramalarını ayarlama | [IAnalyzer](other-types/ianalyzer-class.md)<br />[IRelogger](other-types/irelogger-class.md) | [ANALYSIS_CALLBACKS](other-types/analysis-callbacks-struct.md)<br />[RELOG_CALLBACKS](other-types/relog-callbacks-struct.md) | C++ Build Insights SDK, geri arama işlevleri aracılığıyla olaylar sağlar. C++'da, IAnalyzer veya IRelogger arabirimini devralan bir çözümleyici veya relogger sınıfı oluşturarak geri arama işlevlerini uygulayın. C'de, geri aramaları genel işlevlerde uygulayın ve ANALYSIS_CALLBACKS veya RELOG_CALLBACKS yapısında işaretçiler sağlayın. |
| Yapı grupları | [MakeStaticAnalyzerGroup](functions/make-static-analyzer-group.md)<br />[MakeStaticReloggerGroup](functions/make-static-relogger-group.md)<br />[MakeDynamicAnalyzerGroup](functions/make-dynamic-analyzer-group.md)<br />[MakeDynamicReloggerGroup](functions/make-dynamic-relogger-group.md) |  | C++ API, birden çok çözümleyici ve relogger nesnelerini bir araya getirmek için yardımcı işlevler ve türleri sağlar. Gruplar, karmaşık bir çözümlemesi daha basit adımlara bölmenin düzgün bir yoludur. [vcperf](https://github.com/microsoft/vcperf) bu şekilde organize edilir. |
| Analiz etme veya yeniden kaydetme | [Çözümleme](functions/analyze.md)<br />[Relog](functions/relog.md) | [AnalyzeA](functions/analyze-a.md)<br />[AnalyzeW](functions/analyze-w.md)<br />[RelogA](functions/relog-a.md)<br />[Yeniden LogW](functions/relog-w.md) |  |

### <a name="analyzing-and-relogging"></a>Analiz etme ve yeniden kaydetme

İzleme yitirme, bir analiz oturumu veya yeniden günleme oturumu aracılığıyla yapılır.

Düzenli bir çözümleme kullanmak çoğu senaryo için uygundur. Bu yöntem size çıktı biçiminizi seçme `printf` esnekliği sağlar: metin, xml, JSON, veritabanı, REST aramaları, ve benzeri.

Relogging bir ETW çıkış dosyası üretmek için gereken özel amaçlı analizler içindir. Yeniden kaydetmeyi kullanarak, C++ Build Insights etkinliklerini kendi ETW etkinlik biçiminize çevirebilirsiniz. Yeniden kaydetmenin uygun bir kullanımı, C++ Build Insights verilerini mevcut ETW araçlarınıza ve altyapınıza bağlamak olacaktır. Örneğin, [vcperf](https://github.com/microsoft/vcperf) yeniden ağaçlama arabirimlerini kullanır. Bunun nedeni, bir ETW aracı olan Windows Performance Analyzer'ın anlayabileceği verileri üretmesi gerektiğidir. Yeniden günlüğe kaydetme arabirimlerini kullanmayı planlıyorsanız, ETW'nin nasıl çalıştığına dair önceden bilgi sahibi olmak gerekir.

### <a name="creating-analyzer-groups"></a>Çözümleyici grupları oluşturma

Nasıl grup oluşturulacağını bilmek önemlidir. İşte *Merhaba, dünya* yazdıran bir analizör grubu oluşturmak için nasıl gösteren bir örnek! aldığı her etkinlik başlangıç olayı için.

```cpp
using namespace Microsoft::Cpp::BuildInsights;

class Hello : public IAnalyzer
{
public:
    AnalysisControl OnStartActivity(
        const EventStack& eventStack) override
    {
        std::cout << "Hello, " << std::endl;
        return AnalysisControl::CONTINUE;
    }
};

class World : public IAnalyzer
{
public:
    AnalysisControl OnStartActivity(
        const EventStack& eventStack) override
    {
        std::cout << "world!" << std::endl;
        return AnalysisControl::CONTINUE;
    }
};

int main()
{
    Hello hello;
    World world;

    // Let's make Hello the first analyzer in the group
    // so that it receives events and prints "Hello, "
    // first.
    auto group = MakeStaticAnalyzerGroup(&hello, &world);

    unsigned numberOfAnalysisPasses = 1;

    // Calling this function initiates the analysis and
    // forwards all events from "inputTrace.etl" to my analyzer
    // group.
    Analyze("inputTrace.etl", numberOfAnalysisPasses, group);

    return 0;
}
```

## <a name="using-events"></a>Olayları kullanma

### <a name="sdk-types-and-functions-related-to-events"></a>Olaylarla ilgili SDK türleri ve işlevleri

| İşlev | C++ API | C API | Notlar |
|--|--|--|--|
| Olayları eşleştirme ve filtreleme | [MatchEventStackInmemberFonksiyonu](functions/match-event-stack-in-member-function.md)<br />[MatchEventStack](functions/match-event-stack.md)<br />[MatchEventInmemberFunction](functions/match-event-in-member-function.md)<br />[Maç Etkinliği](functions/match-event.md) |  | C++ API, değer verdiğin olayları izlemelerinizden çıkarmayı kolaylaştıran işlevler sunar. C API ile bu filtreleme elle yapılmalıdır. |
| Olay veri türleri | [Etkinlik](cpp-event-data-types/activity.md)<br />[Arka Geçit](cpp-event-data-types/back-end-pass.md)<br />[BottomUp](cpp-event-data-types/bottom-up.md)<br />[C1DLL](cpp-event-data-types/c1-dll.md)<br />[C2DLL](cpp-event-data-types/c2-dll.md)<br />[Kod Oluşturma](cpp-event-data-types/code-generation.md)<br />[Commandline](cpp-event-data-types/command-line.md)<br />[Derleyici](cpp-event-data-types/compiler.md)<br />[DerleyiciPass](cpp-event-data-types/compiler-pass.md)<br />[ÇevreDeğişken](cpp-event-data-types/environment-variable.md)<br />[Olay](cpp-event-data-types/event.md)<br />[Etkinlik Grubu](cpp-event-data-types/event-group.md)<br />[EventStack](cpp-event-data-types/event-stack.md)<br />[ÇalıştırılabilirImageOutput](cpp-event-data-types/executable-image-output.md)<br />[ExpOutput](cpp-event-data-types/exp-output.md)<br />[FileInput](cpp-event-data-types/file-input.md)<br />[Dosya Çıktısı](cpp-event-data-types/file-output.md)<br />[ForceInlinee](cpp-event-data-types/force-inlinee.md)<br />[FrontEndFile](cpp-event-data-types/front-end-file.md)<br />[FrontEndFileGroup](cpp-event-data-types/front-end-file-group.md)<br />[FrontendPass](cpp-event-data-types/front-end-pass.md)<br />[İşlev](cpp-event-data-types/function.md)<br />[ImplibOutput](cpp-event-data-types/imp-lib-output.md)<br />[Çağırma](cpp-event-data-types/invocation.md)<br />[Çağrı Grubu](cpp-event-data-types/invocation-group.md)<br />[LibOutput](cpp-event-data-types/lib-output.md)<br />[Bağlayıcı](cpp-event-data-types/linker.md)<br />[LinkerGroup](cpp-event-data-types/linker-group.md)<br />[LinkerPass](cpp-event-data-types/linker-pass.md)<br />[Ltcg](cpp-event-data-types/ltcg.md)<br />[ObjOutput](cpp-event-data-types/obj-output.md)<br />[OptICF](cpp-event-data-types/opt-icf.md)<br />[OptLBR](cpp-event-data-types/opt-lbr.md)<br />[Optref](cpp-event-data-types/opt-ref.md)<br />[Geçiş1](cpp-event-data-types/pass1.md)<br />[Geçiş 2](cpp-event-data-types/pass2.md)<br />[PreLTCGOptRef](cpp-event-data-types/pre-ltcg-opt-ref.md)<br />[SimpleEvent](cpp-event-data-types/simple-event.md)<br />[Sembol Adı](cpp-event-data-types/symbol-name.md)<br />[ŞablonAnında](cpp-event-data-types/template-instantiation.md)<br />[TemplateInstantiationGroup](cpp-event-data-types/template-instantiation-group.md)<br />[Iş parçacığı](cpp-event-data-types/thread.md)<br />[Topdown](cpp-event-data-types/top-down.md)<br />[Traceınfo](cpp-event-data-types/trace-info.md)<br />[BütünProgramAnalizi](cpp-event-data-types/whole-program-analysis.md) | [CL_PASS_DATA](c-event-data-types/cl-pass-data-struct.md)<br />[EVENT_COLLECTION_DATA](c-event-data-types/event-collection-data-struct.md)<br />[EVENT_DATA](c-event-data-types/event-data-struct.md)<br />[EVENT_ID](c-event-data-types/event-id-enum.md)<br />[FILE_DATA](c-event-data-types/file-data-struct.md)<br />[FILE_TYPE_CODE](c-event-data-types/file-type-code-enum.md)<br />[FRONT_END_FILE_DATA](c-event-data-types/front-end-file-data-struct.md)<br />[FUNCTION_DATA](c-event-data-types/function-data-struct.md)<br />[FUNCTION_FORCE_INLINEE_DATA](c-event-data-types/function-force-inlinee-data-struct.md)<br />[INVOCATION_DATA](c-event-data-types/invocation-data-struct.md)<br />[INVOCATION_VERSION_DATA](c-event-data-types/invocation-version-data-struct.md)<br />[MSVC_TOOL_CODE](c-event-data-types/msvc-tool-code-enum.md)<br />[NAME_VALUE_PAIR_DATA](c-event-data-types/name-value-pair-data-struct.md)<br />[SYMBOL_NAME_DATA](c-event-data-types/symbol-name-data-struct.md)<br />[TEMPLATE_INSTANTIATION_DATA](c-event-data-types/template-instantiation-data-struct.md)<br />[TEMPLATE_INSTANTIATION_KIND_CODE](c-event-data-types/template-instantiation-kind-code-enum.md)<br />[TRACE_INFO_DATA](c-event-data-types/trace-info-data-struct.md)<br />[TRANSLATION_UNIT_PASS_CODE](c-event-data-types/translation-unit-pass-code-enum.md) |  |

### <a name="activities-and-simple-events"></a>Etkinlikler ve basit etkinlikler

Etkinlikler iki kategoride gelir: *etkinlikler* ve *basit etkinlikler.* Etkinlikler, bir başlangıcı ve sonu olan zamanda devam eden süreçlerdir. Basit olaylar dakik olaylardır ve bir süresi yoktur. C++ Build Insights SDK ile MSVC izlemelerini analiz ederken, bir etkinlik başlayıp durduğunda ayrı olaylar alırsınız. Basit bir olay gerçekleştiğinde yalnızca bir olay alırsınız.

### <a name="parent-child-relationships"></a>Üst-alt ilişkileri

Etkinlikler ve basit olaylar üst-alt ilişkileri yoluyla birbiriyle ilişkilidir. Bir etkinliğin veya basit bir olayın üst öğesi, bunların meydana geldiği alanı kapsayan etkinliktir. Örneğin, bir kaynak dosyayı derlediğinizde derleyicinin dosyayı ayrıştması ve ardından kodu oluşturması gerekir. Ayrıştırma ve kod oluşturma etkinlikleri derleyici etkinliğinin her ikisi de çocukdur.

Basit olayların bir süresi yoktur, bu yüzden içlerinde başka bir şey olamaz. Bu yüzden hiç çocukları olmadı.

Her etkinliğin ve basit olayın üst-alt ilişkileri [olay tablosunda](event-table.md)belirtilir. C++ Build Insights etkinliklerini tüketirken bu ilişkileri bilmek önemlidir. Bir olayın tam içeriğini anlamak için sık sık onlara güvenmeniz gerekir.

### <a name="properties"></a>Özellikler

Tüm olaylar aşağıdaki özelliklere sahiptir:

| Özellik | Açıklama |
|--|--|
| Tür tanımlayıcısı | Olay türünü benzersiz olarak tanımlayan bir sayı. |
| Örnek tanımlayıcı | İzleme içindeki olayı benzersiz olarak tanımlayan bir sayı. Bir izlemede aynı türde iki olay oluşursa, her ikisi de benzersiz bir örnek tanımlayıcısı alır. |
| Başlangıç saati | Bir etkinliğin başladığı saat veya basit bir olayın oluştuğu saat. |
| İşlem tanımlayıcısı | Olayın oluştuğu işlemi tanımlayan bir sayı. |
| İş parçacığı tanımlayıcısı | Olayın oluştuğu iş parçacığı tanımlayan bir sayı. |
| İşlemci dizini | Olayın hangi mantıksal işlemci tarafından yayıldığını gösteren sıfır tabanlı dizin. |
| Olay adı | Olay türünü açıklayan bir dize. |

Basit olaylar dışındaki tüm etkinlikler de şu özelliklere sahiptir:

| Özellik | Açıklama |
|--|--|
| Durma süresi | Etkinliğin durduğu saat. |
| Özel süre | Çocuk etkinliklerinde harcanan zaman hariç olmak üzere, bir etkinlikte harcanan süre. |
| CPU süresi | CPU'nun etkinlik ekinde iş parçacığında kodu yürütmek için harcadığı süre. Aktiviteye bağlı iş parçacığının uyuduğu zamanı içermez. |
| Özel CPU süresi | CPU süresiyle aynıdır, ancak alt etkinlikler tarafından harcanan CPU süresi hariç. |
| Duvar saati zaman sorumluluğu | Etkinliğin genel duvar saati zamanına katkısı. Duvar saati zaman sorumluluğu, faaliyetler arasındaki paralelliği dikkate alır. Örneğin, iki ilgisiz etkinlik paralel olarak çalıştırılyalım. Her ikisi de 10 saniyelik bir süreye ve tam olarak aynı başlangıç ve durma süresine sahiptir. Bu durumda, Build Insights her iki duvar saati zaman sorumluluğu 5 saniye atar. Buna karşılık, bu etkinlikler üst üste çakışma olmadan birbiri ardına çalıştırılırsa, her ikisine de 10 saniyelik bir duvar saati zaman sorumluluğu atanır. |
| Özel duvar saati zaman sorumluluğu | Duvar-saat zaman sorumluluğu ile aynıdır, ancak çocuk etkinliklerinin duvar saati zaman sorumluluğunu hariç tutar. |

Bazı olayların bahsedilenlerin ötesinde kendi özellikleri vardır. Bu durumda, bu ek özellikler [olay tablosunda](event-table.md)listelenir.

### <a name="consuming-events-provided-by-the-c-build-insights-sdk"></a>C++ Build Insights SDK tarafından sağlanan etkinlikleri tüketen

#### <a name="the-event-stack"></a>Olay yığını

C++ Build Insights SDK size bir olay verdiğinde, yığın biçiminde gelir. Yığındaki son giriş geçerli olaydır ve üst hiyerarşisinden önce girişler yapılır. Örneğin, [LTCG](event-table.md#ltcg) başlatma ve durdurma olayları bağlayıcının 1'ingeçişi sırasında meydana gelir. Bu durumda alacağınız yığın \[içerir: [LINKER](event-table.md#linker), [PASS1](event-table.md#pass1)\], LTCG . Bir olayı köküne kadar izleyebilirsiniz, çünkü üst hiyerarşi uygundur. Yukarıda belirtilen LTCG aktivitesi yavaşsa, hangi bağlayıcı çağırmanın söz konusu olduğunu hemen öğrenebilirsiniz.

#### <a name="matching-events-and-event-stacks"></a>Olayları ve olay yığınlarını eşleştirme

C++ Build Insights SDK size bir izlemedeki her olayı verir, ancak çoğu zaman yalnızca bir alt kümesini önemsersiniz. Bazı durumlarda, yalnızca *olay yığınlarının*bir alt kümesini önemseyebilirsiniz. SDK, ihtiyacınız olan olayları veya olay yığınını hızlı bir şekilde ayıklamanıza ve olmadığınız etkinlikleri reddetmenize yardımcı olacak olanaklar sağlar. Bu eşleşen işlevler aracılığıyla yapılır:

|  |  |
|--|--|
| [Maç Etkinliği](functions/match-event.md) | Belirtilen türlerden biriyle eşleşiyorsa bir olay tutun. Bir lambda veya diğer çağrılabilir türe eşleşen olaylar. Olayın üst hiyerarşisi bu işlev tarafından dikkate alınmaz. |
| [MatchEventInmemberFunction](functions/match-event-in-member-function.md) | Bir üye işlevin parametresinde belirtilen türle eşleşiyorsa olayı tutun. Eşleşen olayları üye işlevle iletme. Olayın üst hiyerarşisi bu işlev tarafından dikkate alınmaz. |
| [MatchEventStack](functions/match-event-stack.md) | Olay ve üst hiyerarşisi belirtilen türlerle eşleşirse bir olay tutun. Olayı ve eşleşen üst hiyerarşi olaylarını lambda veya diğer çağrılabilir türe iletin. |
| [MatchEventStackInmemberFonksiyonu](functions/match-event-stack-in-member-function.md) | Olay ve üst hiyerarşisi bir üye işlevin parametre listesinde belirtilen türlerle eşleşirse olayı tutun. Olayı ve eşleşen üst hiyerarşi olaylarını üye işlevine iletin. |

Üst hiyerarşinin eşleşmesini açıklarken boşluklara izin verme gibi `MatchEventStack` olay yığını eşleştirme işlevleri. Örneğin, \[ [LINKER](event-table.md#linker), [LTCG](event-table.md#ltcg) \] yığınıyla ilgilendiğinizi söyleyebilirsiniz. Ayrıca \[LINKER, [PASS1,](event-table.md#pass1)LTCG\] yığını maç olacaktır. Belirtilen son tür, eşlenecek olay türü olmalıdır ve üst hiyerarşinin bir parçası değildir.

#### <a name="capture-classes"></a>Sınıfları yakalama

İşlevleri `Match*` kullanmak, eşleştirmek istediğiniz türleri belirtmenizi gerektirir. Bu *türler, yakalama sınıfları*listesinden seçilir. Yakalama sınıfları aşağıda açıklanan çeşitli kategorilerde gelir.

| Kategori | Açıklama |
|--|--|
| Exact | Bu yakalama sınıfları belirli bir olay türü yle eşleşecek şekilde kullanılır ve başka hiçbir şey kullanılmaz. Derleyici [olayıyla](event-table.md#compiler) eşleşen [Derleyici](cpp-event-data-types/compiler.md) sınıfı bir örnektir. |
| Joker | Bu yakalama sınıfları, destekledikleri olaylar listesindeki herhangi bir olayı eşleştirmek için kullanılabilir. Örneğin, [Etkinlik](cpp-event-data-types/activity.md) joker kartı herhangi bir etkinlik olayıyla eşleşir. Başka bir örnek [derleyiciPass](cpp-event-data-types/compiler-pass.md) joker karakter, [FRONT_END_PASS](event-table.md#front-end-pass) veya [BACK_END_PASS](event-table.md#back-end-pass) olay eşleşebilir. |
| Grup | Grup yakalama sınıflarının adları *Grup'ta*sona erer. Boşlukları yok sayarak, aynı türdeki birden fazla olayı arka arkaya eşleştirmek için kullanılırlar. Bunlar yalnızca özyinelemeli olayları eşleştirirken anlamlıdır, çünkü olay yığınında kaç tane olduğunu bilmiyorsunuz. Örneğin, [FRONT_END_FILE](event-table.md#front-end-file) etkinliği derleyici bir dosyayı her parses her zaman olur. Derleyici dosyayı ayrıştırırken bir dahil yönergesi bulabileceğinden, bu etkinlik özyinelemelidir. [FrontEndFile](cpp-event-data-types/front-end-file.md) sınıfı yığında yalnızca bir FRONT_END_FILE olayıyla eşleşir. Dahil hiyerarşisinin tamamını eşleştirmek için [FrontEndFileGroup](cpp-event-data-types/front-end-file-group.md) sınıfını kullanın. |
| Joker karakter grubu | Joker karakter grubu joker karakter ve grupların özelliklerini birleştirir. Bu kategorideki tek sınıf, tüm [LINKER](event-table.md#linker) ve [COMPILER](event-table.md#compiler) olaylarını tek bir olay yığınında eşleştiren ve yakalayan [InvocationGroup'tur.](cpp-event-data-types/invocation-group.md) |

Her olayla eşleşecek şekilde hangi yakalama sınıflarının kullanılabileceğini öğrenmek için [etkinlik tablosuna](event-table.md) bakın.

#### <a name="after-matching-using-captured-events"></a>Eşleştirmeden sonra: yakalanan olayları kullanma

Bir eşleşme başarıyla tamamlandığında, `Match*` işlevler yakalama sınıfı nesnelerini oluşturmak ve bunları belirtilen işleve iletir. Olayların özelliklerine erişmek için bu yakalama sınıfı nesnelerini kullanın.

#### <a name="example"></a>Örnek

```cpp
AnalysisControl MyAnalyzer::OnStartActivity(const EventStack& eventStack)
{
    // The event types to match are specified in the PrintIncludes function
    // signature.  
    MatchEventStackInMemberFunction(eventStack, this, &MyAnalyzer::PrintIncludes);
}

// We want to capture event stacks where:
// 1. The current event is a FrontEndFile activity.
// 2. The current FrontEndFile activity has at least one parent FrontEndFile activity
//    and possibly many.
void PrintIncludes(FrontEndFileGroup parentIncludes, FrontEndFile currentFile)
{
    // Once we reach this point, the event stack we are interested in has been matched.
    // The current FrontEndFile activity has been captured into 'currentFile', and
    // its entire inclusion hierarchy has been captured in 'parentIncludes'.

    cout << "The current file being parsed is: " << currentFile.Path() << endl;
    cout << "This file was reached through the following inclusions:" << endl;

    for (auto& f : parentIncludes)
    {
        cout << f.Path() << endl;
    }
}
```

::: moniker-end
