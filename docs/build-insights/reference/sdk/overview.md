---
title: C++ Derleme İçgörüleri SDK’sı
description: Visual Studio C++ Build Insights SDK 'sına genel bakış.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Analyzing
- Relogging
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 6f53a9b6c682a0af7d8a01f6378ed0574d8fa4ca
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041178"
---
# <a name="c-build-insights-sdk"></a>C++ Derleme İçgörüleri SDK’sı

::: moniker range="<=vs-2015"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

C++ derleme öngörüleri SDK 'Sı, C++ Build Insights platformunun üzerinde kişiselleştirilmiş araçlar oluşturmanıza imkan tanıyan bir API koleksiyonudur. Bu sayfa, başlamanıza yardımcı olmak için üst düzey bir genel bakış sağlar.

## <a name="obtaining-the-sdk"></a>SDK 'Yı edinme

Aşağıdaki adımları izleyerek C++ Build Insights SDK 'sını bir NuGet paketi olarak indirebilirsiniz:

1. Visual Studio 2017 ve üzeri sürümlerde yeni bir C++ projesi oluşturun.
1. **Çözüm Gezgini** bölmesinde projenize sağ tıklayın.
1. Bağlam menüsünden **NuGet Paketlerini Yönet** ' i seçin.
1. Sağ üst köşedeki **NuGet.org** paket kaynağını seçin.
1. Microsoft. cpp. Buildinsıghts paketinin en son sürümünü arayın.
1. **Yüklemeyi**seçin.
1. Lisansı kabul edin.

SDK 'Yı çevreleyen genel kavramlar hakkında daha fazla bilgi için okumaya devam edin. Ayrıca, SDK 'Yı kullanan gerçek C++ uygulamalarının örneklerini görmek için resmi [C++ Build Insights örnekleri GitHub deposuna](https://github.com/microsoft/cpp-build-insights-samples) erişebilirsiniz.

## <a name="collecting-a-trace"></a>İzleme toplama

MSVC toolzincirinden gelen olayları çözümlemek için C++ Build Insights SDK 'sını kullanmak, önce bir izleme toplamanızı gerektirir. SDK, temel izleme teknolojisi olarak Windows için olay Izleme (ETW) kullanımını sağlar. Bir izlemenin toplanması iki şekilde yapılabilir:

### <a name="method-1-using-vcperf-in-visual-studio-2019-and-above"></a>Yöntem 1: Visual Studio 2019 ve üzeri sürümlerde vcperf kullanma

1. VS 2019 için yükseltilmiş bir x64 Yerel Araçları Komut İstemi açın.
1. Şu komutu çalıştırın: `vcperf /start MySessionName`
1. Projenizi yapılandırın.
1. Şu komutu çalıştırın: `vcperf /stopnoanalyze MySessionName outputTraceFile.etl`

   > [!IMPORTANT]
   > `/stopnoanalyze`İzlemeyi vcperf ile durdururken komutunu kullanın. Normal komut tarafından durdurulan izlemeleri çözümlemek için C++ Build Insights SDK 'sını kullanamazsınız `/stop` .

### <a name="method-2-programmatically"></a>Yöntem 2: programlı olarak

İzlemeleri programlama yoluyla başlatmak ve durdurmak için bu C++ Build Insights SDK izleme toplama işlevlerinden herhangi birini kullanın. **Bu işlev çağrılarını yürüten programın yönetici ayrıcalıklarına sahip olması gerekir.** Yalnızca başlatma ve durdurma işlevleri için yönetici ayrıcalıkları gerekir. C++ derleme öngörüleri SDK 'sının diğer tüm işlevleri bu olmadan çalıştırılabilir.

### <a name="sdk-functions-related-to-trace-collection"></a>İzleme koleksiyonuyla ilgili SDK işlevleri

| İşlev | C++ API | C APı 'SI |
|--|--|--|
| İzleme başlatılıyor | [StartTracingSession](functions/start-tracing-session.md) | [StartTracingSessionA](functions/start-tracing-session-a.md)<br />[StartTracingSessionW](functions/start-tracing-session-w.md) |
| İzleme durduruluyor | [StopTracingSession](functions/stop-tracing-session.md) | [StopTracingSessionA](functions/stop-tracing-session-a.md)<br />[StopTracingSessionW](functions/stop-tracing-session-w.md) |
| Bir izlemeyi durdurma ve<br />sonucu hemen analiz etme | [StopAndAnalyzeTracingSession](functions/stop-and-analyze-tracing-session.md) | [StopAndAnalyzeTracingSessionA](functions/stop-and-analyze-tracing-session-a.md)<br />[StopAndAnalyzeTracingSession](functions/stop-and-analyze-tracing-session-w.md) |
| Bir izlemeyi durdurma ve<br />sonucu hemen yeniden günlüğe kaydetme | [StopAndRelogTracingSession](functions/stop-and-relog-tracing-session.md) | [StopAndRelogTracingSessionA](functions/stop-and-relog-tracing-session-a.md)<br />[StopAndRelogTracingSessionW](functions/stop-and-relog-tracing-session-w.md) |

Aşağıdaki bölümlerde, bir çözümlemenin veya bir yeniden günlüğe kaydetme oturumunun nasıl yapılandırılacağı gösterilir. [Stopandçözümleyiciler Etracingsession](functions/stop-and-analyze-tracing-session.md)gibi Birleşik işlevsellik işlevleri için gereklidir.

## <a name="consuming-a-trace"></a>İzleme kullanma

Bir ETW izlemesinde, paketini açmak için C++ Build Insights SDK 'sını kullanın. SDK, size araçları hızlı bir şekilde geliştirmenize olanak sağlayan bir biçimde olayları sağlar. Ham ETW izlemesini SDK kullanmadan kullanmanızı önermeyiz. MSVC tarafından kullanılan olay biçimi açıklanmamıştır, çok büyük yapılara ölçeklendirilmesi için iyileştirilmiştir ve anlamlı hale getirilir. Ayrıca, C++ Build Insights SDK 'Sı, ham ETW izleme biçimi bildirimde bulunulmadan değiştirilebilir.

### <a name="sdk-types-and-functions-related-to-trace-consumption"></a>SDK türleri ve izleme tüketimiyle ilgili işlevler

| İşlev | C++ API | C APı 'SI | Notlar |
|--|--|--|--|
| Olay geri çağırmaları ayarlama | [IAnalyzer](other-types/ianalyzer-class.md)<br />[IRelogger](other-types/irelogger-class.md) | [ANALYSIS_CALLBACKS](other-types/analysis-callbacks-struct.md)<br />[RELOG_CALLBACKS](other-types/relog-callbacks-struct.md) | C++ derleme öngörüleri SDK 'Sı, geri çağırma işlevleri aracılığıyla Olaylar sağlar. C++ ' da, IAnalyzer veya ıregünlükçü arabirimini devralan bir çözümleyici veya yeniden günlükçü sınıfı oluşturarak geri çağırma işlevlerini uygulayın. C 'de, genel işlevlerde geri çağırmaları uygulayın ve ANALYSIS_CALLBACKS veya RELOG_CALLBACKS yapısında bunlara işaretçiler sağlayın. |
| Grup oluşturma | [MakeStaticAnalyzerGroup](functions/make-static-analyzer-group.md)<br />[MakeStaticReloggerGroup](functions/make-static-relogger-group.md)<br />[MakeDynamicAnalyzerGroup](functions/make-dynamic-analyzer-group.md)<br />[MakeDynamicReloggerGroup](functions/make-dynamic-relogger-group.md) |  | C++ API 'SI, birden çok çözümleyici ve yeniden günlükçü nesnesini birlikte gruplamak için yardımcı işlevler ve türler sağlar. Gruplar, karmaşık bir analizi daha basit adımlara bölmek için bir düzenlidir yoludur. [vcperf](https://github.com/microsoft/vcperf) bu şekilde düzenlenir. |
| Çözümleme veya yeniden günlüğe kaydetme | [Çözümleme](functions/analyze.md)<br />[Relog](functions/relog.md) | [AnalyzeA](functions/analyze-a.md)<br />[AnalyzeW](functions/analyze-w.md)<br />[RelogA](functions/relog-a.md)<br />[RelogW](functions/relog-w.md) |  |

### <a name="analyzing-and-relogging"></a>Analiz ve yeniden günlüğe kaydetme

Bir izlemeyi kullanmak, bir analiz oturumu veya bir yeniden günlüğe kaydetme oturumu aracılığıyla yapılır.

Düzenli bir çözümlemenin kullanılması çoğu senaryo için uygundur. Bu yöntem, çıktı biçiminizi seçme esnekliği sağlar: `printf` metin, XML, JSON, veritabanı, Rest çağrıları vb.

Yeniden günlüğe kaydetme, ETW çıkış dosyası üretmesi gereken özel amaçlı analizler içindir. Yeniden günlüğe kaydetmeyi kullanarak, C++ Build Insights olaylarını kendi ETW olay biçiminize çevirebilirsiniz. Yeniden günlüğe kaydetme işleminin uygun bir şekilde kullanılması, C++ derleme öngörüleri verilerini mevcut ETW araçlarınıza ve altyapınıza bağlamak olacaktır. Örneğin, [vcperf](https://github.com/microsoft/vcperf) yeniden günlüğe kaydetme arabirimlerini kullanır. Bunun nedeni, bir ETW aracı olan Windows Performans Çözümleyicisi, veri üretmesi gerekir. Yeniden günlüğe kaydetme arabirimlerini kullanmayı planlıyorsanız ETW 'nin nasıl çalıştığı hakkında daha önceki bir bilgi.

### <a name="creating-analyzer-groups"></a>Çözümleyici grupları oluşturma

Grupların nasıl oluşturulacağını öğrenmek önemlidir. İşte *Hello, World!* görüntüleyen bir çözümleyici grubu oluşturmayı gösteren bir örnek. aldığı her etkinlik başlangıç olayı için.

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

### <a name="sdk-types-and-functions-related-to-events"></a>SDK türleri ve olaylarla ilgili işlevler

| İşlev | C++ API | C APı 'SI | Notlar |
|--|--|--|--|
| Olayları eşleştirme ve filtreleme | [MatchEventStackInMemberFunction](functions/match-event-stack-in-member-function.md)<br />[MatchEventStack](functions/match-event-stack.md)<br />[MatchEventInMemberFunction](functions/match-event-in-member-function.md)<br />[MatchEvent](functions/match-event.md) |  | C++ API 'SI, izlemelerinizin önem verdiğiniz olayları ayıklamayı kolaylaştıran işlevler sunar. C API 'SI ile bu filtrelemenin el ile yapılması gerekir. |
| Olay veri türleri | [Etkinlik](cpp-event-data-types/activity.md)<br />[BackEndPass](cpp-event-data-types/back-end-pass.md)<br />[BottomUp](cpp-event-data-types/bottom-up.md)<br />[C1DLL](cpp-event-data-types/c1-dll.md)<br />[C2DLL](cpp-event-data-types/c2-dll.md)<br />[CodeGeneration](cpp-event-data-types/code-generation.md)<br />[CommandLine](cpp-event-data-types/command-line.md)<br />[Derleyici](cpp-event-data-types/compiler.md)<br />[CompilerPass](cpp-event-data-types/compiler-pass.md)<br />[EnvironmentVariable](cpp-event-data-types/environment-variable.md)<br />[Olay](cpp-event-data-types/event.md)<br />[EventGroup](cpp-event-data-types/event-group.md)<br />[EventStack](cpp-event-data-types/event-stack.md)<br />[ExecutableImageOutput](cpp-event-data-types/executable-image-output.md)<br />[ExpOutput](cpp-event-data-types/exp-output.md)<br />[FileInput](cpp-event-data-types/file-input.md)<br />[FileOutput](cpp-event-data-types/file-output.md)<br />[ForceInlinee](cpp-event-data-types/force-inlinee.md)<br />[FrontEndFile](cpp-event-data-types/front-end-file.md)<br />[FrontEndFileGroup](cpp-event-data-types/front-end-file-group.md)<br />[FrontEndPass](cpp-event-data-types/front-end-pass.md)<br />[İşlev](cpp-event-data-types/function.md)<br />[ImpLibOutput](cpp-event-data-types/imp-lib-output.md)<br />[Çağrı](cpp-event-data-types/invocation.md)<br />[InvocationGroup](cpp-event-data-types/invocation-group.md)<br />[LibOutput](cpp-event-data-types/lib-output.md)<br />[Bağlayıcı](cpp-event-data-types/linker.md)<br />[LinkerGroup](cpp-event-data-types/linker-group.md)<br />[LinkerPass](cpp-event-data-types/linker-pass.md)<br />[LTCG](cpp-event-data-types/ltcg.md)<br />[ObjOutput](cpp-event-data-types/obj-output.md)<br />[OptICF](cpp-event-data-types/opt-icf.md)<br />[OptLBR](cpp-event-data-types/opt-lbr.md)<br />[OptRef](cpp-event-data-types/opt-ref.md)<br />[Pass1](cpp-event-data-types/pass1.md)<br />[Pass2](cpp-event-data-types/pass2.md)<br />[PreLTCGOptRef](cpp-event-data-types/pre-ltcg-opt-ref.md)<br />[SimpleEvent](cpp-event-data-types/simple-event.md)<br />[SymbolName](cpp-event-data-types/symbol-name.md)<br />[TemplateInstantiation](cpp-event-data-types/template-instantiation.md)<br />[TemplateInstantiationGroup](cpp-event-data-types/template-instantiation-group.md)<br />[Zincirinin](cpp-event-data-types/thread.md)<br />[TopDown](cpp-event-data-types/top-down.md)<br />[TraceInfo](cpp-event-data-types/trace-info.md)<br />[WholeProgramAnalysis](cpp-event-data-types/whole-program-analysis.md) | [CL_PASS_DATA](c-event-data-types/cl-pass-data-struct.md)<br />[EVENT_COLLECTION_DATA](c-event-data-types/event-collection-data-struct.md)<br />[EVENT_DATA](c-event-data-types/event-data-struct.md)<br />[EVENT_ID](c-event-data-types/event-id-enum.md)<br />[FILE_DATA](c-event-data-types/file-data-struct.md)<br />[FILE_TYPE_CODE](c-event-data-types/file-type-code-enum.md)<br />[FRONT_END_FILE_DATA](c-event-data-types/front-end-file-data-struct.md)<br />[FUNCTION_DATA](c-event-data-types/function-data-struct.md)<br />[FUNCTION_FORCE_INLINEE_DATA](c-event-data-types/function-force-inlinee-data-struct.md)<br />[INVOCATION_DATA](c-event-data-types/invocation-data-struct.md)<br />[INVOCATION_VERSION_DATA](c-event-data-types/invocation-version-data-struct.md)<br />[MSVC_TOOL_CODE](c-event-data-types/msvc-tool-code-enum.md)<br />[NAME_VALUE_PAIR_DATA](c-event-data-types/name-value-pair-data-struct.md)<br />[SYMBOL_NAME_DATA](c-event-data-types/symbol-name-data-struct.md)<br />[TEMPLATE_INSTANTIATION_DATA](c-event-data-types/template-instantiation-data-struct.md)<br />[TEMPLATE_INSTANTIATION_KIND_CODE](c-event-data-types/template-instantiation-kind-code-enum.md)<br />[TRACE_INFO_DATA](c-event-data-types/trace-info-data-struct.md)<br />[TRANSLATION_UNIT_PASS_CODE](c-event-data-types/translation-unit-pass-code-enum.md) |  |

### <a name="activities-and-simple-events"></a>Etkinlikler ve basit olaylar

Olaylar iki kategoride gelir: *Etkinlikler* ve *basit olaylar*. Etkinlikler, başlangıç ve bitiş zamanı olan zaman içinde devam eden işlemlerdir. Basit olaylar, zayıf oluşumlardır ve süresi yoktur. C++ Build Insights SDK 'Sı ile MSVC izlemelerini analiz edilirken, bir etkinlik başladığında ve durdurulduğunda ayrı olaylar alırsınız. Basit bir olay gerçekleştiğinde yalnızca bir olay alırsınız.

### <a name="parent-child-relationships"></a>Üst-alt öğe ilişkileri

Etkinlikler ve basit olaylar, üst-alt ilişkileri aracılığıyla birbirleriyle ilişkilidir. Etkinliğin üst öğesi veya basit bir olay, gerçekleştikleri dahil etme etkinliğidir. Örneğin, bir kaynak dosya derlenirken derleyicinin dosyayı ayrıştırmak ve kodu oluşturması gerekir. Ayrıştırma ve kod oluşturma etkinlikleri, her iki derleyici etkinliğinin alt öğesi.

Basit olayların süresi yoktur, bu nedenle bunlar içinde başka hiçbir şey gerçekleşmez. Bu nedenle, hiç çocuğu yoktur.

Her etkinliğin ve basit etkinliğin üst-alt ilişkileri [olay tablosunda](event-table.md)belirtilir. C++ derleme öngörüleri olaylarını kullanırken bu ilişkilerin bilinmesi önemlidir. Genellikle bir olayın tam bağlamını anlamak için bunları bilmeniz gerekir.

### <a name="properties"></a>Özellikler

Tüm olaylar aşağıdaki özelliklere sahiptir:

| Özellik | Açıklama |
|--|--|
| Tür tanımlayıcısı | Olay türünü benzersiz bir şekilde tanımlayan bir sayı. |
| Örnek tanımlayıcısı | Trace içinde olayı benzersiz bir şekilde tanımlayan bir sayı. Aynı türde iki olay bir izlemede oluşursa, her ikisi de benzersiz bir örnek tanımlayıcısı alır. |
| Başlangıç saati | Etkinliğin başlatıldığı saat veya basit bir olayın gerçekleştiği zaman. |
| İşlem tanımlayıcısı | Olayın gerçekleştiği işlemi tanımlayan bir sayı. |
| İş parçacığı tanımlayıcısı | Olayın gerçekleştiği iş parçacığını tanımlayan bir sayı. |
| İşlemci dizini | Olayın hangi mantıksal işlemciyi yayınlamadığını gösteren sıfır tabanlı bir dizin. |
| Olay adı | Olay türünü tanımlayan bir dize. |

Basit olaylar dışındaki tüm etkinliklerin de şu özellikler vardır:

| Özellik | Açıklama |
|--|--|
| Durdurma zamanı | Etkinliğin durdurulduğu zaman. |
| Dışlamalı süre | Alt etkinliklerinde harcanan süre hariç olmak üzere bir etkinlikte harcanan süre. |
| CPU süresi | CPU 'nun etkinliğe eklenmiş iş parçacığında kod çalıştırırken harcadığı süre. Etkinliğe iliştirilen iş parçacığının uyuma zaman dahil değildir. |
| Dışlamalı CPU süresi | CPU zamanı ile aynı, ancak alt etkinlikler tarafından harcanan CPU süresini hariç tutma. |
| Duvar saati saat sorumluluğu | Etkinliğin genel duvar saati zamanına katkısı. Duvar saati zamanı sorumluluğu, etkinlikler arasında paralellik hesaba sahiptir. Örneğin, ilgisiz iki etkinliğin paralel olarak çalışacağını varsayalım. Her ikisinde de 10 saniyelik bir süre ve tam olarak aynı başlangıç ve bitiş saati vardır. Bu durumda, derleme öngörüleri 5 saniyelik bir duvar saati zaman sorumluluğunu atar. Buna karşılık, bu etkinlikler çakışma olmadan diğeri bir kez çalışıyorsa, her ikisi de 10 saniyelik bir duvar saati zaman sorumluluğuna atanır. |
| Özel duvar saati saat sorumluluğu | Duvar saati zaman sorumluluğunda aynıdır, ancak alt etkinliklerin duvar saati zaman sorumluluğunu dışlar. |

Bazı olayların, bahsedilen Özellikler ötesinde kendi özellikleri vardır. Bu durumda, bu ek özellikler [olay tablosunda](event-table.md)listelenir.

### <a name="consuming-events-provided-by-the-c-build-insights-sdk"></a>C++ Build Insights SDK 'Sı tarafından sunulan olayları kullanma

#### <a name="the-event-stack"></a>Olay yığını

C++ derleme öngörüleri SDK 'Sı size bir olay sunışınızda, yığın biçiminde gelir. Yığındaki son giriş, geçerli olaydır ve üst hiyerarşinden önceki girişler olur. Örneğin, [LTCG](event-table.md#ltcg) Start ve stop olayları bağlayıcı 1. geçiş sırasında oluşur. Bu durumda, aldığınız yığın şunları içerir: \[ [bağlayıcı](event-table.md#linker), [PASS1](event-table.md#pass1), LTCG \] . Bir olayı köküne geri izlemenize olanak sağladığından üst hiyerarşi uygun değildir. Yukarıda belirtilen LTCG etkinliği yavaşsa, hangi bağlayıcı çağrısının dahil olduğunu hemen öğrenebilirsiniz.

#### <a name="matching-events-and-event-stacks"></a>Eşleşen olaylar ve olay yığınları

C++ derleme öngörüleri SDK 'Sı, bir izlemede her etkinlik sağlar, ancak çoğu zaman yalnızca bunların bir alt kümesiyle ilgilenmenizi sağlar. Bazı durumlarda, yalnızca bir *olay yığınları*alt kümesi olabilir. SDK, ihtiyacınız olan olayları ve olay yığınını hızlıca ayıklamanıza yardımcı olan tesisler sağlar ve bunları reddedebilirsiniz. Bu eşleşen işlevler aracılığıyla yapılır:

| İşlev | Açıklama |
|--|--|
| [MatchEvent](functions/match-event.md) | Belirtilen türlerden biriyle eşleşiyorsa bir olayı saklayın. Eşleşen olayları lambda veya diğer çağrılabilir bir türe ilet. Olayın üst hiyerarşisi bu işlev tarafından dikkate alınmıyor. |
| [MatchEventInMemberFunction](functions/match-event-in-member-function.md) | Bir üye işlevin parametresinde belirtilen türle eşleşiyorsa bir olayı saklayın. Eşleşen olayları üye işlevine ilet. Olayın üst hiyerarşisi bu işlev tarafından dikkate alınmıyor. |
| [MatchEventStack](functions/match-event-stack.md) | Hem olay hem de onun üst hiyerarşisi belirtilen türlerle eşleşiyorsa bir olayı saklayın. Olayı ve eşleşen üst hiyerarşi olaylarını bir lambda veya diğer çağrılabilir bir türe iletin. |
| [MatchEventStackInMemberFunction](functions/match-event-stack-in-member-function.md) | Hem olay hem de onun üst hiyerarşisi üye işlevin parametre listesinde belirtilen türlerle eşleşiyorsa bir olayı saklayın. Olayı ve eşleşen üst hiyerarşi olaylarını üye işlevine iletin. |

`MatchEventStack`Eşleşmesi için üst hiyerarşiyi açıklayan sırada boşluk kullanılmasına izin ver gibi olay yığını eşleştirme işlevleri. Örneğin, \[ [LTCG](event-table.md#ltcg) yığınında [bağlayıcı](event-table.md#linker)ile ilgilendiğinizi varsayalım \] . Ayrıca \[ bağlayıcı, [PASS1](event-table.md#pass1), LTCG Stack ile de eşleşir \] . Belirtilen son tür, eşleştirilecek olay türü olmalıdır ve üst hiyerarşinin bir parçası değildir.

#### <a name="capture-classes"></a>Sınıfları yakala

İşlevlerinin kullanılması `Match*` için, eşleştirmek istediğiniz türleri belirtmeniz gerekir. Bu türler, *yakalama sınıfları*listesinden seçilir. Yakalama sınıfları aşağıda açıklanan çeşitli kategorilerde gelir.

| Kategori | Açıklama |
|--|--|
| Exact | Bu yakalama sınıfları, belirli bir olay türünü ve başka hiçbirini eşleştirmek için kullanılır. [Derleyici](event-table.md#compiler) olayı Ile eşleşen [derleyici](cpp-event-data-types/compiler.md) sınıfı bir örnektir. |
| Liyorsa | Bu yakalama sınıfları, destekledikleri olaylar listesinden herhangi bir olayı eşleştirmek için kullanılabilir. Örneğin, [etkinlik](cpp-event-data-types/activity.md) joker karakteri herhangi bir etkinlik olayından eşleşir. Diğer bir örnek, [FRONT_END_PASS](event-table.md#front-end-pass) veya [BACK_END_PASS](event-table.md#back-end-pass) olayından eşleşen bir [compilerpass](cpp-event-data-types/compiler-pass.md) joker karakterdir. |
| Grup | Grup yakalama sınıflarının adları *Grup*olarak sona erdir. Bunlar, boşlukları yoksayarak bir satırdaki aynı türdeki birden fazla olayı eşleştirmek için kullanılır. Olay yığınında kaç tane mevcut olduğunu bilmiyorsanız, özyinelemeli olayları eşleştirirken yalnızca anlamalar yapılır. Örneğin, derleyici bir dosyayı her ayrıştırdığında [FRONT_END_FILE](event-table.md#front-end-file) etkinlik olur. Derleyici dosyayı ayrıştırırken bir içerme yönergesi bulabileceğinden bu etkinlik özyinelemeli olur. [Frontendfile](cpp-event-data-types/front-end-file.md) sınıfı yığında yalnızca bir FRONT_END_FILE olayla eşleşir. Tüm içerme hiyerarşisine uyması için [Frontendfılegroup](cpp-event-data-types/front-end-file-group.md) sınıfını kullanın. |
| Joker karakter grubu | Joker karakter grubu ve grupların özelliklerini birleştirir. Bu kategorinin tek sınıfı, tek bir olay yığınındaki tüm [bağlayıcı](event-table.md#linker) ve [derleyici](event-table.md#compiler) olaylarını eşleştirecek ve yakaladığı [ıncationgroup](cpp-event-data-types/invocation-group.md)' dır. |

Her olayla eşleştirmek için hangi yakalama sınıflarının kullanılabileceğini öğrenmek için [olay tablosuna](event-table.md) bakın.

#### <a name="after-matching-using-captured-events"></a>Eşleştirmeden sonra: yakalanan olayları kullanma

Bir eşleşme başarıyla tamamlandıktan sonra işlevler, `Match*` yakalama sınıfı nesnelerini oluşturur ve bunları belirtilen işleve iletir. Olayların özelliklerine erişmek için bu yakalama sınıfı nesnelerini kullanın.

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
