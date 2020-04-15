---
title: 'C++ Build Insights SDK: etkinlik tablosu'
description: Visual Studio C++ Build Insights SDK için etkinlik referansı
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Events
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 932b78347e05d313e7962da2fdff8c3454dec963
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324130"
---
# <a name="c-build-insights-sdk-event-table"></a>C++ Build Insights SDK: etkinlik tablosu

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

## <a name="compiler-events"></a>Derleyici etkinlikleri

[Derleyici](#compiler)\
[COMMAND_LINE](#command-line)\
[ENVIRONMENT_VARIABLE](#environment-variable)\
[FILE_INPUT](#file-input)\
[OBJ_OUTPUT](#obj-output)\
[FRONT_END_PASS](#front-end-pass)\
[BACK_END_PASS](#back-end-pass)

## <a name="compiler-front-end-events"></a>Derleyici ön uç olayları

[C1_DLL](#c1-dll)\
[FRONT_END_FILE](#front-end-file)\
[TEMPLATE_INSTANTIATION](#template-instantiation)\
[SYMBOL_NAME](#symbol-name)

## <a name="compiler-back-end-events"></a>Derleyici arka uç olayları

[C2_DLL](#c2-dll)\
[WHOLE_PROGRAM_ANALYSIS](#whole-program-analysis)\
[TOP_DOWN](#top-down)\
[BOTTOM_UP](#bottom-up)\
[CODE_GENERATION](#code-generation)\
[Iş parçacığı](#thread)\
[Işlev](#function)\
[FORCE_INLINEE](#force-inlinee)

## <a name="linker-events"></a>Bağlayıcı etkinlikleri

[Bağlayıcı](#linker)\
[COMMAND_LINE](#command-line)\
[ENVIRONMENT_VARIABLE](#environment-variable)\
[FILE_INPUT](#file-input)\
[EXECUTABLE_IMAGE_OUTPUT](#executable-image-output)\
[EXP_OUTPUT](#exp-output)\
[IMP_LIB_OUTPUT](#imp-lib-output)\
[LIB_OUTPUT](#lib-output)\
[GEÇİş 1](#pass1)\
[PRE_LTCG_OPT_REF](#pre-ltcg-opt-ref)\
[Ltcg](#ltcg)\
[OPT_REF](#opt-ref)\
[OPT_ICF](#opt-icf)\
[OPT_LBR](#opt-lbr)\
[PASS2](#pass2)

## <a name="event-table"></a>Etkinlik tablosu

| Olay | Özellik | Açıklama |
|--|--|--|
| <a name="back-end-pass"></a>BACK_END_PASS | Tür | Etkinlik |
|  | Üst öğeler | [Derleyici](#compiler) |
|  | Alt öğeler | [C2_DLL](#c2-dll) |
|  | Özellikler | - Giriş kaynak dosyasına mutlak yol<br/>- Çıkış nesnesi dosyasına mutlak yol |
|  | Sınıfları yakalama | [Etkinlik](cpp-event-data-types/activity.md)<br/>[DerleyiciPass](cpp-event-data-types/compiler-pass.md)<br/>[Arka Geçit](cpp-event-data-types/back-end-pass.md) |
|  | Açıklama | Derleyici arka uç geçişinin başında ve sonunda oluşur. Bu geçiş, ayrıştırılmış C/C++ kaynak kodunu optimize etmek ve makine koduna dönüştürmekten sorumludur. |
| <a name="bottom-up"></a>BOTTOM_UP | Tür | Etkinlik |
|  | Üst öğeler | [WHOLE_PROGRAM_ANALYSIS](#whole-program-analysis) |
|  | Alt öğeler | None |
|  | Özellikler | None |
|  | Sınıfları yakalama | [Etkinlik](cpp-event-data-types/activity.md)<br/>[BottomUp](cpp-event-data-types/bottom-up.md) |
|  | Açıklama | Tüm program analizinin aşağıdan yukarıya geçişinin başında ve sonunda gerçekleşir. |
| <a name="c1-dll"></a>C1_DLL | Tür | Etkinlik |
|  | Üst öğeler | [FRONT_END_PASS](#front-end-pass) |
|  | Alt öğeler | [FRONT_END_FILE](#front-end-file)<br/>[SYMBOL_NAME](#symbol-name)<br/>[TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | Özellikler | None |
|  | Sınıfları yakalama | [Etkinlik](cpp-event-data-types/activity.md)<br/>[C1DLL](cpp-event-data-types/c1-dll.md) |
|  | Açıklama | *C1.dll veya c1xx.dll* *c1xx.dll* çağırmanın başında ve sonunda oluşur. Bu DL'ler derleyicinin C ve C++ ön ucu. Onlar sadece derleyici sürücü *(cl.exe)* tarafından çağrılır konum. |
| <a name="c2-dll"></a>C2_DLL | Tür | Etkinlik |
|  | Üst öğeler | [BACK_END_PASS](#back-end-pass)<br/>[Ltcg](#ltcg) |
|  | Alt öğeler | [CODE_GENERATION](#code-generation)<br/>[WHOLE_PROGRAM_ANALYSIS](#whole-program-analysis) |
|  | Özellikler | None |
|  | Sınıfları yakalama | [Etkinlik](cpp-event-data-types/activity.md)<br/>[C2DLL](cpp-event-data-types/c2-dll.md) |
|  | Açıklama | *C2.dll* çağırmanın başlangıcında ve sonunda oluşur. Bu DLL derleyicinin arka ucudur. Derleyici sürücü *(cl.exe)* tarafından çağrılır. Ayrıca bağlantı zamanı kodu oluşturma kullanıldığında bağlayıcı *(link.exe)* tarafından çağrılır. |
| <a name="code-generation"></a>CODE_GENERATION | Tür | Etkinlik |
|  | Üst öğeler | [C2_DLL](#c2-dll) |
|  | Alt öğeler | [Işlev](#function)<br/>[Iş parçacığı](#thread) |
|  | Özellikler | None |
|  | Sınıfları yakalama | [Etkinlik](cpp-event-data-types/activity.md)<br/>[Kod Oluşturma](cpp-event-data-types/code-generation.md) |
|  | Açıklama | Arka uç kod oluşturma aşamasının başında ve sonunda oluşur. |
| <a name="command-line"></a>COMMAND_LINE | Tür | Basit Olay |
|  | Üst öğeler | [Derleyici](#compiler)<br/>[Bağlayıcı](#linker) |
|  | Alt öğeler | None |
|  | Özellikler | - *cl.exe* veya *link.exe* çağırmak için kullanılan komut satırı |
|  | Sınıfları yakalama | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[Commandline](cpp-event-data-types/command-line.md) |
|  | Açıklama | Derleyici ve bağlayıcı komut satırı değerlendirirken yapıldığında oluşur. Değerlendirilen komut satırı, yanıt dosyası üzerinden geçirilen tüm *cl.exe* ve *link.exe* parametrelerini içerir. Ayrıca CL, CL, \_\_ \_LINK ve LINK\_gibi ortam değişkenleri üzerinden geçirilen *cl.exe* ve *link.exe* parametrelerini içerir. |
| <a name="compiler"></a>Derleyici | Tür | Etkinlik |
|  | Üst öğeler | None |
|  | Alt öğeler | [BACK_END_PASS](#back-end-pass)<br/>[COMMAND_LINE](#command-line)<br/>[ENVIRONMENT_VARIABLE](#environment-variable)<br/>[FILE_INPUT](#file-input)<br/>[OBJ_OUTPUT](#obj-output)<br/>[FRONT_END_PASS](#front-end-pass) |
|  | Özellikler | - Derleyici sürümü<br/>- Çalışma dizini<br/>- Çağrılan *cl.exe* için mutlak yol |
|  | Sınıfları yakalama | [Etkinlik](cpp-event-data-types/activity.md)<br/>[Çağırma](cpp-event-data-types/invocation.md)<br/>[Derleyici](cpp-event-data-types/compiler.md) |
|  | Açıklama | *Cl.exe* çağırmasının başında ve sonunda meydana gelir. |
| <a name="environment-variable"></a>ENVIRONMENT_VARIABLE | Tür | Basit Olay |
|  | Üst öğeler | [Derleyici](#compiler)<br/>[Bağlayıcı](#linker) |
|  | Alt öğeler | None |
|  | Özellikler | - Çevre değişkeninin adı<br/>- Çevre değişkeninin değeri. |
|  | Sınıfları yakalama | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[ÇevreDeğişken](cpp-event-data-types/environment-variable.md) |
|  | Açıklama | *Cl.exe* veya *link.exe* çağrıldığı anda varolan her ortam değişkeni için bir kez oluşur. |
| <a name="executable-image-output"></a>EXECUTABLE_IMAGE_OUTPUT | Tür | Basit Olay |
|  | Üst öğeler | [Bağlayıcı](#linker) |
|  | Alt öğeler | None |
|  | Özellikler | - Bir DLL veya çalıştırılabilir çıktı dosyasına mutlak yol. |
|  | Sınıfları yakalama | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[Dosya Çıktısı](cpp-event-data-types/file-output.md)<br/>[ÇalıştırılabilirImageOutput](cpp-event-data-types/executable-image-output.md) |
|  | Açıklama | Bağlayıcı girişlerinden biri DLL veya çalıştırılabilir bir görüntü dosyası olduğunda oluşur. |
| <a name="exp-output"></a>EXP_OUTPUT | Tür | Basit Olay |
|  | Üst öğeler | [Bağlayıcı](#linker) |
|  | Alt öğeler | None |
|  | Özellikler | - *Bir .exp* çıktı dosyasına mutlak yol. |
|  | Sınıfları yakalama | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[Dosya Çıktısı](cpp-event-data-types/file-output.md)<br/>[ExpOutput](cpp-event-data-types/exp-output.md) |
|  | Açıklama | Bağlayıcı çıktılarından biri *bir .exp* dosyası olduğunda oluşur. |
| <a name="file-input"></a>FILE_INPUT | Tür | Basit Olay |
|  | Üst öğeler | [Derleyici](#compiler)<br/>[Bağlayıcı](#linker) |
|  | Alt öğeler | None |
|  | Özellikler | - Giriş dosyasına mutlak yol<br/>- Giriş dosyasının türü |
|  | Sınıfları yakalama | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[FileInput](cpp-event-data-types/file-input.md) |
|  | Açıklama | Bir *cl.exe* veya *link.exe* girişi duyurmak için oluşur. |
| <a name="force-inlinee"></a>FORCE_INLINEE | Tür | Basit Olay |
|  | Üst öğeler | [Işlev](#function) |
|  | Alt öğeler | None |
|  | Özellikler | - Kuvvet-inlined fonksiyonun adı.<br/>- Bir ara öğretim sayısı olarak temsil kuvvet inlined fonksiyonun boyutu. |
|  | Sınıfları yakalama | [Etkinlik](cpp-event-data-types/activity.md)<br/>[ForceInlinee](cpp-event-data-types/force-inlinee.md) |
|  | Açıklama | Bir `__forceinline` işlev, anahtar kelimenin kullanımı yoluyla başka bir işleve zorla girildiğinde oluşur. |
| <a name="front-end-file"></a>FRONT_END_FILE | Tür | Etkinlik |
|  | Üst öğeler | [C1_DLL](#c1-dll)<br/>[FRONT_END_FILE](#front-end-file) |
|  | Alt öğeler | [FRONT_END_FILE](#front-end-file)<br/>[TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | Özellikler | - Dosyaya mutlak yol. |
|  | Sınıfları yakalama | [Etkinlik](cpp-event-data-types/activity.md)<br/>[FrontEndFile](cpp-event-data-types/front-end-file.md) |
|  | Açıklama | Derleyici ön uç başlatıldığında ve bir dosyayı işlemeyi durdurduğunda oluşur. Bu olay özyinelemeli. Yineleme, ön uç dahil dosyaları ayrıştırırken gerçekleşir. |
| <a name="front-end-pass"></a>FRONT_END_PASS | Tür | Etkinlik |
|  | Üst öğeler | [Derleyici](#compiler) |
|  | Alt öğeler | [C1_DLL](#c1-dll) |
|  | Özellikler | - Giriş kaynak dosyasına mutlak yol<br/>- Çıkış nesnesi dosyasına mutlak yol |
|  | Sınıfları yakalama | [Etkinlik](cpp-event-data-types/activity.md)<br/>[DerleyiciPass](cpp-event-data-types/compiler-pass.md)<br/>[FrontendPass](cpp-event-data-types/front-end-pass.md) |
|  | Açıklama | Derleyici ön uç geçişinin başında ve durağında oluşur. Bu geçiş, C/C++ kaynak kodunu ayrıştırma ve ara dile dönüştürmeden sorumludur. |
| <a name="function"></a>Işlev | Tür | Etkinlik |
|  | Üst öğeler | [CODE_GENERATION](#code-generation)<br/>[Iş parçacığı](#thread)<br/>[TOP_DOWN](#top-down) |
|  | Alt öğeler | [FORCE_INLINEE](#force-inlinee) |
|  | Özellikler | - Fonksiyonun adı |
|  | Sınıfları yakalama | [Etkinlik](cpp-event-data-types/activity.md)<br/>[İşlev](cpp-event-data-types/function.md) |
|  | Açıklama | Bir işlev için kod oluşturma başlatıp sona erdiğinde oluşur. |
| <a name="imp-lib-output"></a>IMP_LIB_OUTPUT | Tür | Basit Olay |
|  | Üst öğeler | [Bağlayıcı](#linker) |
|  | Alt öğeler | None |
|  | Özellikler | - Bir alma kitaplığı çıktı dosyasına mutlak yol. |
|  | Sınıfları yakalama | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[Dosya Çıktısı](cpp-event-data-types/file-output.md)<br/>[ImplibOutput](cpp-event-data-types/imp-lib-output.md) |
|  | Açıklama | Bağlayıcının çıktılarından biri alma kitaplığı olduğunda oluşur. |
| <a name="lib-output"></a>LIB_OUTPUT | Tür | Basit Olay |
|  | Üst öğeler | [Bağlayıcı](#linker) |
|  | Alt öğeler | None |
|  | Özellikler | - Statik kitaplık çıktı dosyasına giden mutlak yol. |
|  | Sınıfları yakalama | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[Dosya Çıktısı](cpp-event-data-types/file-output.md)<br/>[LibOutput](cpp-event-data-types/lib-output.md) |
|  | Açıklama | Bağlayıcının çıktılarından biri statik kitaplık olduğunda oluşur. |
| <a name="linker"></a>Bağlayıcı | Tür | Etkinlik |
|  | Üst öğeler | None |
|  | Alt öğeler | [COMMAND_LINE](#command-line)<br/>[ENVIRONMENT_VARIABLE](#environment-variable)<br/>[EXECUTABLE_IMAGE_OUTPUT](#executable-image-output)<br/>[EXP_OUTPUT](#exp-output)<br/>[FILE_INPUT](#file-input)<br/>[IMP_LIB_OUTPUT](#imp-lib-output)<br/>[LIB_OUTPUT](#lib-output)<br/>[GEÇİş 1](#pass1)<br/>[PASS2](#pass2) |
|  | Özellikler | - Linker sürümü<br/>- Çalışma dizini<br/>- Çağrılan *link.exe* için mutlak yol |
|  | Sınıfları yakalama | [Etkinlik](cpp-event-data-types/activity.md)<br/>[Çağırma](cpp-event-data-types/invocation.md)<br/>[Bağlayıcı](cpp-event-data-types/linker.md) |
|  | Açıklama | *Link.exe* çağırmasının başında ve sonunda oluşur. |
| <a name="ltcg"></a>Ltcg | Tür | Etkinlik |
|  | Üst öğeler | [GEÇİş 1](#pass1) |
|  | Alt öğeler | [C2_DLL](#c2-dll) |
|  | Özellikler | None |
|  | Sınıfları yakalama | [Etkinlik](cpp-event-data-types/activity.md)<br/>[Ltcg](cpp-event-data-types/ltcg.md) |
|  | Açıklama | Bağlantı zamanı kodu oluşturmanın başında ve durağında oluşur. |
| <a name="obj-output"></a>OBJ_OUTPUT | Tür | Basit Olay |
|  | Üst öğeler | [Derleyici](#compiler) |
|  | Alt öğeler | None |
|  | Özellikler | - *.obj* çıktı dosyasına mutlak yol |
|  | Sınıfları yakalama | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[Dosya Çıktısı](cpp-event-data-types/file-output.md)<br/>[ObjOutput](cpp-event-data-types/obj-output.md) |
|  | Açıklama | *CL.exe*tarafından üretilen her *.obj* çıkışı için bir kez oluşur. |
| <a name="opt-icf"></a>OPT_ICF | Tür | Etkinlik |
|  | Üst öğeler | [GEÇİş 1](#pass1) |
|  | Alt öğeler | None |
|  | Özellikler | None |
|  | Sınıfları yakalama | [Etkinlik](cpp-event-data-types/activity.md)<br/>[OptICF](cpp-event-data-types/opt-icf.md) |
|  | Açıklama | Aynı COMDAT katlama (/OPT:ICF) bağlayıcı optimizasyonunun başında ve sonunda oluşur. |
| <a name="opt-lbr"></a>OPT_LBR | Tür | Etkinlik |
|  | Üst öğeler | [GEÇİş 1](#pass1) |
|  | Alt öğeler | None |
|  | Özellikler | None |
|  | Sınıfları yakalama | [Etkinlik](cpp-event-data-types/activity.md)<br/>[OptLBR](cpp-event-data-types/opt-lbr.md) |
|  | Açıklama | Uzun dalı (/OPT:LBR) bağlayıcı optimizasyonunun başında ve sonunda gerçekleşir. |
| <a name="opt-ref"></a>OPT_REF | Tür | Etkinlik |
|  | Üst öğeler | [GEÇİş 1](#pass1) |
|  | Alt öğeler | None |
|  | Özellikler | None |
|  | Sınıfları yakalama | [Etkinlik](cpp-event-data-types/activity.md)<br/>[Optref](cpp-event-data-types/opt-ref.md) |
|  | Açıklama | Başvurulmamış işlevlerin ve veri eliminasyonunun (/OPT:REF) bağlayıcı optimizasyonunun başlangıcında ve sonunda oluşur. |
| <a name="pass1"></a>GEÇİş 1 | Tür | Etkinlik |
|  | Üst öğeler | [Bağlayıcı](#linker) |
|  | Alt öğeler | [Ltcg](#ltcg)<br/>[OPT_ICF](#opt-icf)<br/>[OPT_LBR](#opt-lbr)<br/>[OPT_REF](#opt-ref) |
|  | Özellikler | None |
|  | Sınıfları yakalama | [Etkinlik](cpp-event-data-types/activity.md)<br/>[Geçiş1](cpp-event-data-types/pass1.md) |
|  | Açıklama | Bağlayıcının geçiş inin başında ve durağında oluşur 1. |
| <a name="pass2"></a>PASS2 | Tür | Etkinlik |
|  | Üst öğeler | [Bağlayıcı](#linker) |
|  | Alt öğeler | None |
|  | Özellikler | None |
|  | Sınıfları yakalama | [Etkinlik](cpp-event-data-types/activity.md)<br/>[Geçiş 2](cpp-event-data-types/pass2.md) |
|  | Açıklama | Bağlayıcının geçişinin başında ve durağında oluşur 2. |
| <a name="pre-ltcg-opt-ref"></a>PRE_LTCG_OPT_REF | Tür | Etkinlik |
|  | Üst öğeler | [GEÇİş 1](#pass1) |
|  | Alt öğeler | None |
|  | Özellikler | None |
|  | Sınıfları yakalama | [Etkinlik](cpp-event-data-types/activity.md)<br/>[PreLTCGOptRef](cpp-event-data-types/pre-ltcg-opt-ref.md) |
|  | Açıklama | Başvurulmamış işlevleri ve verileri (/OPT:REF) ortadan kaldıran bağlayıcı optimizasyon geçişinin başında ve sonunda oluşur. Bağlantı zamanı kodu oluşturmadan önce yapılır. |
| <a name="symbol-name"></a>SYMBOL_NAME | Tür | Basit Olay |
|  | Üst öğeler | [C1_DLL](#c1-dll) |
|  | Alt öğeler | None |
|  | Özellikler | - Bir tür anahtarı<br/> - Türün adı |
|  | Sınıfları yakalama | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[Sembol Adı](cpp-event-data-types/symbol-name.md) |
|  | Açıklama | Ön uç geçişinin sonunda gerçekleşir: şablon anlık iletilerine dahil olan her tür için bir kez. Anahtar, tür için sayısal bir tanımlayıcıiken, ad onun metin gösterimidir. Tür tuşları, analiz edilen izleme içinde benzersizdir. Ancak, farklı derleyici ön uç geçişlerinden gelen farklı tuşlar aynı türe işaret edebilir. Farklı derleyici ön uç geçişleri arasında türleri karşılaştırmak adlarını kullanmayı gerektirir. SYMBOL_NAME olaylar, tüm şablon anlık gerçekleşmeleri gerçekleştikten sonra, derleyici ön uç geçişinin sonunda yayılır. |
| <a name="template-instantiation"></a>TEMPLATE_INSTANTIATION | Tür | Etkinlik |
|  | Üst öğeler | [C1_DLL](#c1-dll)<br/>[FRONT_END_FILE](#front-end-file)<br/>[TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | Alt öğeler | [TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | Özellikler | - Özel türü için anahtar<br/>- Birincil şablonun türü için anahtar<br/>- Anında verilen şablon türü |
|  | Sınıfları yakalama | [Etkinlik](cpp-event-data-types/activity.md)<br/>[ŞablonAnında](cpp-event-data-types/template-instantiation.md) |
|  | Açıklama | Şablon anlık başlangıcında ve sonunda oluşur. Birincil şablon türü (örneğin) `vector`anında bulunur ve özel bir türle sonuçlanır `std::vector<int>`(örneğin). Her iki tür için de bir anahtar verilir. Bir anahtarı türün adına dönüştürmek için [SYMBOL_NAME](#symbol-name) olayını kullanın. Tür tuşları, analiz edilen izleme içinde benzersizdir. Ancak, farklı derleyici ön uç geçişlerinden gelen farklı tuşlar aynı türe işaret edebilir. Farklı derleyici ön uç geçişleri arasındaki türleri karşılaştırmak için sembol adları kullanılması gerekmektedir. Bu olay özyinelemeli. Yineleme, bazı durumlarda ön uç iç içe şablonları anında alırken gerçekleşir. |
| <a name="thread"></a>Iş parçacığı | Tür | Etkinlik |
|  | Üst öğeler | [CODE_GENERATION](#code-generation)<br/>[TOP_DOWN](#top-down) |
|  | Alt öğeler | [Işlev](#function) |
|  | Özellikler | None |
|  | Sınıfları yakalama | [Etkinlik](cpp-event-data-types/activity.md)<br/>[Iş parçacığı](cpp-event-data-types/thread.md) |
|  | Açıklama | Derleyici arka uç iş parçacığı yürütmesinin başında ve sonunda oluşur. Askıya alınan bir iş parçacığı sona erdirilir olarak kabul edilir. Uyandırılan bir iş parçacığı nın başlatıldığı kabul edilir. |
| <a name="top-down"></a>TOP_DOWN | Tür | Etkinlik |
|  | Üst öğeler | [WHOLE_PROGRAM_ANALYSIS](#whole-program-analysis) |
|  | Alt öğeler | [Işlev](#function)<br/>[Iş parçacığı](#thread) |
|  | Özellikler | None |
|  | Sınıfları yakalama | [Etkinlik](cpp-event-data-types/activity.md)<br/>[Topdown](cpp-event-data-types/top-down.md) |
|  | Açıklama | Tüm program analizinin yukarıdan aşağıya geçişinin başında ve sonunda gerçekleşir. |
| <a name="whole-program-analysis"></a>WHOLE_PROGRAM_ANALYSIS | Tür | Etkinlik |
|  | Üst öğeler | [C2_DLL](#c2-dll) |
|  | Alt öğeler | [BOTTOM_UP](#bottom-up)<br/>[TOP_DOWN](#top-down) |
|  | Özellikler | None |
|  | Sınıfları yakalama | [Etkinlik](cpp-event-data-types/activity.md)<br/>[BütünProgramAnalizi](cpp-event-data-types/whole-program-analysis.md) |
|  | Açıklama | Bağlantı zamanı kodu oluşturmanın tüm program çözümleme aşamasının başlangıcında ve sonunda oluşur. |

::: moniker-end
