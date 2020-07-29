---
title: "C++ derleme öngörüleri SDK 'Sı: olay tablosu"
description: Visual Studio C++ Build Insights SDK 'Sı için olay başvurusu
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Events
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 6b1cf6871329fcce3166495e173360a88ac38ee0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224220"
---
# <a name="c-build-insights-sdk-event-table"></a>C++ derleme öngörüleri SDK 'Sı: olay tablosu

::: moniker range="<=vs-2015"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

## <a name="compiler-events"></a>Derleyici olayları

[DERLEYICI](#compiler)\
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
[ZINCIRININ](#thread)\
[ÇALıŞMAYACAKTıR](#function)\
[FORCE_INLINEE](#force-inlinee)

## <a name="linker-events"></a>Bağlayıcı olayları

[BAĞLAYıCı](#linker)\
[COMMAND_LINE](#command-line)\
[ENVIRONMENT_VARIABLE](#environment-variable)\
[FILE_INPUT](#file-input)\
[EXECUTABLE_IMAGE_OUTPUT](#executable-image-output)\
[EXP_OUTPUT](#exp-output)\
[IMP_LIB_OUTPUT](#imp-lib-output)\
[LIB_OUTPUT](#lib-output)\
[PASS1](#pass1)\
[PRE_LTCG_OPT_REF](#pre-ltcg-opt-ref)\
[LTCG](#ltcg)\
[OPT_REF](#opt-ref)\
[OPT_ICF](#opt-icf)\
[OPT_LBR](#opt-lbr)\
[PASS2](#pass2)

## <a name="event-table"></a>Olay tablosu

| Olay | Özellik | Açıklama |
|--|--|--|
| <a name="back-end-pass"></a>BACK_END_PASS | Tür | Etkinlik |
|  | Üst öğeler | [DERLEYICI](#compiler) |
|  | Alt öğeler | [C2_DLL](#c2-dll) |
|  | Özellikler | -Giriş kaynak dosyasına mutlak yol<br/>-Çıkış nesnesi dosyasının mutlak yolu |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[CompilerPass](cpp-event-data-types/compiler-pass.md)<br/>[BackEndPass](cpp-event-data-types/back-end-pass.md) |
|  | Açıklama | Derleyici arka uç geçişinin başlangıcında ve durdurulduğunda gerçekleşir. Bu geçiş, ayrıştırılmış C/C++ kaynak kodunu iyileştirmek ve makine koduna dönüştürmek için sorumludur. |
| <a name="bottom-up"></a>BOTTOM_UP | Tür | Etkinlik |
|  | Üst öğeler | [WHOLE_PROGRAM_ANALYSIS](#whole-program-analysis) |
|  | Alt öğeler | Hiçbiri |
|  | Özellikler | Hiçbiri |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[BottomUp](cpp-event-data-types/bottom-up.md) |
|  | Açıklama | Tüm program analizinin en alta açılan geçişinin başlangıcında ve durdurulduğunda gerçekleşir. |
| <a name="c1-dll"></a>C1_DLL | Tür | Etkinlik |
|  | Üst öğeler | [FRONT_END_PASS](#front-end-pass) |
|  | Alt öğeler | [FRONT_END_FILE](#front-end-file)<br/>[SYMBOL_NAME](#symbol-name)<br/>[TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | Özellikler | Hiçbiri |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[C1DLL](cpp-event-data-types/c1-dll.md) |
|  | Açıklama | Bir *c1.dll* başlatma ve durdurma *c1xx.dll* çağırma sırasında gerçekleşir. Bu dll 'Ler derleyicinin C ve C++ ön ucu. Bunlar yalnızca derleyici sürücüsü (*cl.exe*) tarafından çağırılır. |
| <a name="c2-dll"></a>C2_DLL | Tür | Etkinlik |
|  | Üst öğeler | [BACK_END_PASS](#back-end-pass)<br/>[LTCG](#ltcg) |
|  | Alt öğeler | [CODE_GENERATION](#code-generation)<br/>[WHOLE_PROGRAM_ANALYSIS](#whole-program-analysis) |
|  | Özellikler | Hiçbiri |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[C2DLL](cpp-event-data-types/c2-dll.md) |
|  | Açıklama | *c2.dll* bir çağrının başlangıcında ve durdurulduğunda gerçekleşir. Bu DLL, derleyicinin arka ucu olur. Derleyici sürücüsü (*cl.exe*) tarafından çağırılır. Ayrıca, bağlantı zamanı kod üretimi kullanıldığında bağlayıcı (*link.exe*) tarafından da çağrılır. |
| <a name="code-generation"></a>CODE_GENERATION | Tür | Etkinlik |
|  | Üst öğeler | [C2_DLL](#c2-dll) |
|  | Alt öğeler | [ÇALıŞMAYACAKTıR](#function)<br/>[ZINCIRININ](#thread) |
|  | Özellikler | Hiçbiri |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[CodeGeneration](cpp-event-data-types/code-generation.md) |
|  | Açıklama | Arka ucun kod oluşturma aşamasının başlangıcında ve durdurulduğunda gerçekleşir. |
| <a name="command-line"></a>COMMAND_LINE | Tür | Basit olay |
|  | Üst öğeler | [DERLEYICI](#compiler)<br/>[BAĞLAYıCı](#linker) |
|  | Alt öğeler | Hiçbiri |
|  | Özellikler | - *cl.exe* veya *link.exe* çağırmak için kullanılan komut satırı |
|  | Sınıfları yakala | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[CommandLine](cpp-event-data-types/command-line.md) |
|  | Açıklama | Derleyici ve bağlayıcı komut satırını değerlendirmeyi tamamladıktan sonra gerçekleşir. Değerlendirilen komut satırı, bir yanıt dosyası aracılığıyla geçirilen tüm *cl.exe* ve *link.exe* parametrelerini içerir. Ayrıca, *cl.exe* PARAMETRELERI ve CL, *link.exe* \_ CL \_ , bağlantı ve bağlantı gibi ortam değişkenleri aracılığıyla geçirilenlink.exeiçerir \_ \_ . |
| <a name="compiler"></a>DERLEYICI | Tür | Etkinlik |
|  | Üst öğeler | Hiçbiri |
|  | Alt öğeler | [BACK_END_PASS](#back-end-pass)<br/>[COMMAND_LINE](#command-line)<br/>[ENVIRONMENT_VARIABLE](#environment-variable)<br/>[FILE_INPUT](#file-input)<br/>[OBJ_OUTPUT](#obj-output)<br/>[FRONT_END_PASS](#front-end-pass) |
|  | Özellikler | -Derleyici sürümü<br/>-Çalışma dizini<br/>-Çağrılan *cl.exe* mutlak yolu |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[Çağrı](cpp-event-data-types/invocation.md)<br/>[Derleyici](cpp-event-data-types/compiler.md) |
|  | Açıklama | *cl.exe* bir çağrının başlangıcında ve durdurulduğunda gerçekleşir. |
| <a name="environment-variable"></a>ENVIRONMENT_VARIABLE | Tür | Basit olay |
|  | Üst öğeler | [DERLEYICI](#compiler)<br/>[BAĞLAYıCı](#linker) |
|  | Alt öğeler | Hiçbiri |
|  | Özellikler | -Ortam değişkeninin adı<br/>-Ortam değişkeninin değeri. |
|  | Sınıfları yakala | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[EnvironmentVariable](cpp-event-data-types/environment-variable.md) |
|  | Açıklama | *cl.exe* veya *link.exe* çağrıldığında, var olan her ortam değişkeni için bir kez gerçekleşir. |
| <a name="executable-image-output"></a>EXECUTABLE_IMAGE_OUTPUT | Tür | Basit olay |
|  | Üst öğeler | [BAĞLAYıCı](#linker) |
|  | Alt öğeler | Hiçbiri |
|  | Özellikler | -Bir DLL veya yürütülebilir çıkış dosyasının mutlak yolu. |
|  | Sınıfları yakala | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[FileOutput](cpp-event-data-types/file-output.md)<br/>[ExecutableImageOutput](cpp-event-data-types/executable-image-output.md) |
|  | Açıklama | Bağlayıcı girdilerden biri DLL veya yürütülebilir bir görüntü dosyası olduğunda gerçekleşir. |
| <a name="exp-output"></a>EXP_OUTPUT | Tür | Basit olay |
|  | Üst öğeler | [BAĞLAYıCı](#linker) |
|  | Alt öğeler | Hiçbiri |
|  | Özellikler | - *. Exp* çıkış dosyasının mutlak yolu. |
|  | Sınıfları yakala | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[FileOutput](cpp-event-data-types/file-output.md)<br/>[ExpOutput](cpp-event-data-types/exp-output.md) |
|  | Açıklama | Bağlayıcının çıktılarından biri *. exp* dosyası olduğunda gerçekleşir. |
| <a name="file-input"></a>FILE_INPUT | Tür | Basit olay |
|  | Üst öğeler | [DERLEYICI](#compiler)<br/>[BAĞLAYıCı](#linker) |
|  | Alt öğeler | Hiçbiri |
|  | Özellikler | -Giriş dosyasının mutlak yolu<br/>-Giriş dosyasının türü |
|  | Sınıfları yakala | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[FileInput](cpp-event-data-types/file-input.md) |
|  | Açıklama | Bir *cl.exe* veya *link.exe* girişi duyurmak için gerçekleşir. |
| <a name="force-inlinee"></a>FORCE_INLINEE | Tür | Basit olay |
|  | Üst öğeler | [ÇALıŞMAYACAKTıR](#function) |
|  | Alt öğeler | Hiçbiri |
|  | Özellikler | -Zorlamalı satır içine alınmış işlevin adı.<br/>-Bir ara yönerge sayısı olarak temsil edilen zorla satır içine alınmış işlevin boyutu. |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[ForceInlinee](cpp-event-data-types/force-inlinee.md) |
|  | Açıklama | Bir işlev anahtar sözcüğünün kullanımı aracılığıyla başka bir işleve zorla satır içine eklendiğinde gerçekleşir **`__forceinline`** . |
| <a name="front-end-file"></a>FRONT_END_FILE | Tür | Etkinlik |
|  | Üst öğeler | [C1_DLL](#c1-dll)<br/>[FRONT_END_FILE](#front-end-file) |
|  | Alt öğeler | [FRONT_END_FILE](#front-end-file)<br/>[TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | Özellikler | -Dosyanın mutlak yolu. |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[FrontEndFile](cpp-event-data-types/front-end-file.md) |
|  | Açıklama | Derleyici ön ucu başladığında ve bir dosyayı işlemeyi durdurduğu zaman gerçekleşir. Bu olay özyinelemeli. Ön uç dahil edilen dosyaları ayrıştırırken özyineleme gerçekleşir. |
| <a name="front-end-pass"></a>FRONT_END_PASS | Tür | Etkinlik |
|  | Üst öğeler | [DERLEYICI](#compiler) |
|  | Alt öğeler | [C1_DLL](#c1-dll) |
|  | Özellikler | -Giriş kaynak dosyasına mutlak yol<br/>-Çıkış nesnesi dosyasının mutlak yolu |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[CompilerPass](cpp-event-data-types/compiler-pass.md)<br/>[FrontEndPass](cpp-event-data-types/front-end-pass.md) |
|  | Açıklama | Derleyicinin ön uç geçişinin başlangıcında ve durdurulduğunda gerçekleşir. Bu geçiş, C/C++ kaynak kodunu ayrıştırmaktan ve ara dile dönüştürmesinden sorumludur. |
| <a name="function"></a>ÇALıŞMAYACAKTıR | Tür | Etkinlik |
|  | Üst öğeler | [CODE_GENERATION](#code-generation)<br/>[ZINCIRININ](#thread)<br/>[TOP_DOWN](#top-down) |
|  | Alt öğeler | [FORCE_INLINEE](#force-inlinee) |
|  | Özellikler | -İşlevin adı |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[İşlev](cpp-event-data-types/function.md) |
|  | Açıklama | Bir işlev için kod oluşturma başlatılırken ve sona ermek üzere gerçekleşir. |
| <a name="imp-lib-output"></a>IMP_LIB_OUTPUT | Tür | Basit olay |
|  | Üst öğeler | [BAĞLAYıCı](#linker) |
|  | Alt öğeler | Hiçbiri |
|  | Özellikler | -Bir içeri aktarma kitaplığı çıkış dosyasının mutlak yolu. |
|  | Sınıfları yakala | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[FileOutput](cpp-event-data-types/file-output.md)<br/>[ImpLibOutput](cpp-event-data-types/imp-lib-output.md) |
|  | Açıklama | Bağlayıcının çıktılarından biri içeri aktarma kitaplığı olduğunda gerçekleşir. |
| <a name="lib-output"></a>LIB_OUTPUT | Tür | Basit olay |
|  | Üst öğeler | [BAĞLAYıCı](#linker) |
|  | Alt öğeler | Hiçbiri |
|  | Özellikler | -Statik kitaplık çıkış dosyasının mutlak yolu. |
|  | Sınıfları yakala | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[FileOutput](cpp-event-data-types/file-output.md)<br/>[LibOutput](cpp-event-data-types/lib-output.md) |
|  | Açıklama | Bağlayıcının çıktılarından biri statik kitaplık olduğunda gerçekleşir. |
| <a name="linker"></a>BAĞLAYıCı | Tür | Etkinlik |
|  | Üst öğeler | Hiçbiri |
|  | Alt öğeler | [COMMAND_LINE](#command-line)<br/>[ENVIRONMENT_VARIABLE](#environment-variable)<br/>[EXECUTABLE_IMAGE_OUTPUT](#executable-image-output)<br/>[EXP_OUTPUT](#exp-output)<br/>[FILE_INPUT](#file-input)<br/>[IMP_LIB_OUTPUT](#imp-lib-output)<br/>[LIB_OUTPUT](#lib-output)<br/>[PASS1](#pass1)<br/>[PASS2](#pass2) |
|  | Özellikler | -Bağlayıcı sürümü<br/>-Çalışma dizini<br/>-Çağrılan *link.exe* mutlak yolu |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[Çağrı](cpp-event-data-types/invocation.md)<br/>[Bağlayıcı](cpp-event-data-types/linker.md) |
|  | Açıklama | *link.exe* bir çağrının başlangıcında ve durdurulduğunda gerçekleşir. |
| <a name="ltcg"></a>LTCG | Tür | Etkinlik |
|  | Üst öğeler | [PASS1](#pass1) |
|  | Alt öğeler | [C2_DLL](#c2-dll) |
|  | Özellikler | Hiçbiri |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[LTCG](cpp-event-data-types/ltcg.md) |
|  | Açıklama | Bağlantı zamanı kod üretimi başlatma ve durdurma sırasında gerçekleşir. |
| <a name="obj-output"></a>OBJ_OUTPUT | Tür | Basit olay |
|  | Üst öğeler | [DERLEYICI](#compiler) |
|  | Alt öğeler | Hiçbiri |
|  | Özellikler | - *. Obj* çıkış dosyasının mutlak yolu |
|  | Sınıfları yakala | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[FileOutput](cpp-event-data-types/file-output.md)<br/>[ObjOutput](cpp-event-data-types/obj-output.md) |
|  | Açıklama | *cl.exe*tarafından üretilen her *. obj* çıktısı için bir kez gerçekleşir. |
| <a name="opt-icf"></a>OPT_ICF | Tür | Etkinlik |
|  | Üst öğeler | [PASS1](#pass1) |
|  | Alt öğeler | Hiçbiri |
|  | Özellikler | Hiçbiri |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[OptICF](cpp-event-data-types/opt-icf.md) |
|  | Açıklama | Aynı COMDAT katlama (/OPT: ICF) bağlayıcı iyileştirmesinin başlangıcında ve durdurulduğunda gerçekleşir. |
| <a name="opt-lbr"></a>OPT_LBR | Tür | Etkinlik |
|  | Üst öğeler | [PASS1](#pass1) |
|  | Alt öğeler | Hiçbiri |
|  | Özellikler | Hiçbiri |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[OptLBR](cpp-event-data-types/opt-lbr.md) |
|  | Açıklama | Uzun dal (/OPT: LBR) bağlayıcı iyileştirmesinin başlangıcında ve durdurulduğunda gerçekleşir. |
| <a name="opt-ref"></a>OPT_REF | Tür | Etkinlik |
|  | Üst öğeler | [PASS1](#pass1) |
|  | Alt öğeler | Hiçbiri |
|  | Özellikler | Hiçbiri |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[OptRef](cpp-event-data-types/opt-ref.md) |
|  | Açıklama | Başvurulmayan işlevler ve veri eleme (/OPT: REF) bağlayıcı iyileştirmesinin başlangıcında ve durdurulduğunda gerçekleşir. |
| <a name="pass1"></a>PASS1 | Tür | Etkinlik |
|  | Üst öğeler | [BAĞLAYıCı](#linker) |
|  | Alt öğeler | [LTCG](#ltcg)<br/>[OPT_ICF](#opt-icf)<br/>[OPT_LBR](#opt-lbr)<br/>[OPT_REF](#opt-ref) |
|  | Özellikler | Hiçbiri |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[Pass1](cpp-event-data-types/pass1.md) |
|  | Açıklama | Bağlayıcının pass 1 ' in başlangıcında ve durdurulduğunda gerçekleşir. |
| <a name="pass2"></a>PASS2 | Tür | Etkinlik |
|  | Üst öğeler | [BAĞLAYıCı](#linker) |
|  | Alt öğeler | Hiçbiri |
|  | Özellikler | Hiçbiri |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[Pass2](cpp-event-data-types/pass2.md) |
|  | Açıklama | Bağlayıcının Pass 2 ' nin başlangıcında ve durdurulduğunda gerçekleşir. |
| <a name="pre-ltcg-opt-ref"></a>PRE_LTCG_OPT_REF | Tür | Etkinlik |
|  | Üst öğeler | [PASS1](#pass1) |
|  | Alt öğeler | Hiçbiri |
|  | Özellikler | Hiçbiri |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[PreLTCGOptRef](cpp-event-data-types/pre-ltcg-opt-ref.md) |
|  | Açıklama | , Başvurulmayan işlevleri ve verileri ortadan kaldıran bağlayıcı iyileştirme geçişinin başlangıcında ve durdurulduğunda gerçekleşir (/OPT: REF). Bu işlem, bağlantı zaman kodu oluşturmadan önce yapılır. |
| <a name="symbol-name"></a>SYMBOL_NAME | Tür | Basit olay |
|  | Üst öğeler | [C1_DLL](#c1-dll) |
|  | Alt öğeler | Hiçbiri |
|  | Özellikler | -Tür anahtarı<br/> -Türün adı |
|  | Sınıfları yakala | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[SymbolName](cpp-event-data-types/symbol-name.md) |
|  | Açıklama | Ön uç geçişinin sonunda gerçekleşir: şablon örneklemelerde yer alan her tür için bir kez. Anahtar, türü için sayısal bir tanıtıcıdır, ad ise metin gösterimidir. Tür anahtarları çözümlenmekte olan izleme içinde benzersizdir. Ancak, farklı derleyici ön uç geçişlerinden gelen farklı anahtarlar aynı türe işaret edebilir. Farklı derleyici ön uç geçişleri arasındaki türleri karşılaştırmak için adlarının kullanılması gerekir. SYMBOL_NAME olaylar, tüm şablon örneklemeleri gerçekleştirildikten sonra bir derleyici ön ucu geçişinin sonuna yayılır. |
| <a name="template-instantiation"></a>TEMPLATE_INSTANTIATION | Tür | Etkinlik |
|  | Üst öğeler | [C1_DLL](#c1-dll)<br/>[FRONT_END_FILE](#front-end-file)<br/>[TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | Alt öğeler | [TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | Özellikler | -Özelleştirilmiş tür için anahtar<br/>-Birincil şablonun türünün anahtarı<br/>-Oluşturulan şablonun türü |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[TemplateInstantiation](cpp-event-data-types/template-instantiation.md) |
|  | Açıklama | Şablon örneklemesinin başlangıcında ve sonunda gerçekleşir. Birincil şablon türü (gibi `vector` ) örneği oluşturulur ve özel bir tür (örneğin, `std::vector<int>` ) oluşur. Her iki tür için de bir anahtar verilir. Bir anahtarı türün adına dönüştürmek için [SYMBOL_NAME](#symbol-name) olayını kullanın. Tür anahtarları çözümlenmekte olan izleme içinde benzersizdir. Ancak, farklı derleyici ön uç geçişlerinden gelen farklı anahtarlar aynı türe işaret edebilir. Farklı derleyici ön uç geçişleri arasındaki türleri karşılaştırmak için sembol adlarının kullanılması gerekir. Bu olay özyinelemeli. Ön uç iç içe geçmiş şablonları örnekledikten sonra bazı durumlarda özyineleme meydana gelir. |
| <a name="thread"></a>ZINCIRININ | Tür | Etkinlik |
|  | Üst öğeler | [CODE_GENERATION](#code-generation)<br/>[TOP_DOWN](#top-down) |
|  | Alt öğeler | [ÇALıŞMAYACAKTıR](#function) |
|  | Özellikler | Hiçbiri |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[Zincirinin](cpp-event-data-types/thread.md) |
|  | Açıklama | Derleyici arka uç iş parçacığı yürütmesinin başlangıcında ve sonunda gerçekleşir. Askıya alınan bir iş parçacığı sona erdi olarak kabul edilir. Uyandırıldığında bir iş parçacığı başlatılmış olarak kabul edilir. |
| <a name="top-down"></a>TOP_DOWN | Tür | Etkinlik |
|  | Üst öğeler | [WHOLE_PROGRAM_ANALYSIS](#whole-program-analysis) |
|  | Alt öğeler | [ÇALıŞMAYACAKTıR](#function)<br/>[ZINCIRININ](#thread) |
|  | Özellikler | Hiçbiri |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[TopDown](cpp-event-data-types/top-down.md) |
|  | Açıklama | Tüm program analizinin yukarıdan açılan geçişinin başlangıcında ve durdurulduğunda gerçekleşir. |
| <a name="whole-program-analysis"></a>WHOLE_PROGRAM_ANALYSIS | Tür | Etkinlik |
|  | Üst öğeler | [C2_DLL](#c2-dll) |
|  | Alt öğeler | [BOTTOM_UP](#bottom-up)<br/>[TOP_DOWN](#top-down) |
|  | Özellikler | Hiçbiri |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[WholeProgramAnalysis](cpp-event-data-types/whole-program-analysis.md) |
|  | Açıklama | Bağlantı zamanı kod oluşturma işleminin tam program çözümleme aşamasının başlatılması ve durdurulması sırasında gerçekleşir. |

::: moniker-end
