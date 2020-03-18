---
title: "C++Derleme öngörüleri SDK 'Sı: olay tablosu"
description: Visual Studio C++ Build Insights SDK 'sı için olay başvurusu
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Events
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2ccc8a4ef707942963b85edc6db9e21e05610b54
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79417511"
---
# <a name="c-build-insights-sdk-event-table"></a>C++Derleme öngörüleri SDK 'Sı: olay tablosu

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

## <a name="compiler-events"></a>Derleyici olayları

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
[İşlev](#function)\
[FORCE_INLINEE](#force-inlinee)

## <a name="linker-events"></a>Bağlayıcı olayları

[Bağlayıcı](#linker)\
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
|  | Alt | [C2_DLL](#c2-dll) |
|  | Özellikler | -Giriş kaynak dosyasına mutlak yol<br/>-Çıkış nesnesi dosyasının mutlak yolu |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[CompilerPass](cpp-event-data-types/compiler-pass.md)<br/>[BackEndPass](cpp-event-data-types/back-end-pass.md) |
|  | Açıklama | Derleyici arka uç geçişinin başlangıcında ve durdurulduğunda gerçekleşir. Bu geçiş, ayrıştırılmış C/C++ kaynak kodunu iyileştirmek ve makine koduna dönüştürmek için sorumludur. |
| <a name="bottom-up"></a>BOTTOM_UP | Tür | Etkinlik |
|  | Üst öğeler | [WHOLE_PROGRAM_ANALYSIS](#whole-program-analysis) |
|  | Alt | Yok |
|  | Özellikler | Yok |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[BottomUp](cpp-event-data-types/bottom-up.md) |
|  | Açıklama | Tüm program analizinin en alta açılan geçişinin başlangıcında ve durdurulduğunda gerçekleşir. |
| <a name="c1-dll"></a>C1_DLL | Tür | Etkinlik |
|  | Üst öğeler | [FRONT_END_PASS](#front-end-pass) |
|  | Alt | [FRONT_END_FILE](#front-end-file)<br/>[SYMBOL_NAME](#symbol-name)<br/>[TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | Özellikler | Yok |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[C1DLL](cpp-event-data-types/c1-dll.md) |
|  | Açıklama | Bir *C1. dll* veya *c1xx. dll* çağırma işleminin başlangıcında ve durdurulduğunda gerçekleşir. Bu dll 'Ler derleyicinin C ve C++ ön ucu. Bunlar yalnızca derleyici sürücüsü (*CL. exe*) tarafından çağırılır. |
| <a name="c2-dll"></a>C2_DLL | Tür | Etkinlik |
|  | Üst öğeler | [BACK_END_PASS](#back-end-pass)<br/>[LTCG](#ltcg) |
|  | Alt | [CODE_GENERATION](#code-generation)<br/>[WHOLE_PROGRAM_ANALYSIS](#whole-program-analysis) |
|  | Özellikler | Yok |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[C2DLL](cpp-event-data-types/c2-dll.md) |
|  | Açıklama | Bir *C2. dll* çağırma işleminin başlangıcında ve durdurulduğunda gerçekleşir. Bu DLL, derleyicinin arka ucu olur. Derleyici sürücüsü (*CL. exe*) tarafından çağırılır. Ayrıca, bağlantı zamanı kod üretimi kullanıldığında bağlayıcı (*Link. exe*) tarafından da çağrılır. |
| <a name="code-generation"></a>CODE_GENERATION | Tür | Etkinlik |
|  | Üst öğeler | [C2_DLL](#c2-dll) |
|  | Alt | [FUNCTION](#function)<br/>[ZINCIRININ](#thread) |
|  | Özellikler | Yok |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[CodeGeneration](cpp-event-data-types/code-generation.md) |
|  | Açıklama | Arka ucun kod oluşturma aşamasının başlangıcında ve durdurulduğunda gerçekleşir. |
| <a name="command-line"></a>COMMAND_LINE | Tür | Basit olay |
|  | Üst öğeler | [DERLEYICI](#compiler)<br/>[BAĞLAYıCı](#linker) |
|  | Alt | Yok |
|  | Özellikler | - *CL. exe* veya *LINK. exe* ' yi çağırmak için kullanılan komut satırı |
|  | Sınıfları yakala | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[Komut satırı](cpp-event-data-types/command-line.md) |
|  | Açıklama | Derleyici ve bağlayıcı komut satırını değerlendirmeyi tamamladıktan sonra gerçekleşir. Değerlendirilen komut satırı, bir yanıt dosyası aracılığıyla geçirilen tüm *CL. exe* ve *LINK. exe* parametrelerini içerir. Ayrıca, CL *. exe* ve *LINK. exe* ' nın cl, \_CL\_, bağlantı ve \_bağlantı\_gibi ortam değişkenleri aracılığıyla geçirildiği parametreleri de içerir. |
| <a name="compiler"></a>DERLEYICI | Tür | Etkinlik |
|  | Üst öğeler | Yok |
|  | Alt | [BACK_END_PASS](#back-end-pass)<br/>[COMMAND_LINE](#command-line)<br/>[ENVIRONMENT_VARIABLE](#environment-variable)<br/>[FILE_INPUT](#file-input)<br/>[OBJ_OUTPUT](#obj-output)<br/>[FRONT_END_PASS](#front-end-pass) |
|  | Özellikler | -Derleyici sürümü<br/>-Çalışma dizini<br/>-Çağrılan *CL. exe* ' ye mutlak yol |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[Çağrılması](cpp-event-data-types/invocation.md)<br/>[Derleyici](cpp-event-data-types/compiler.md) |
|  | Açıklama | Bir *CL. exe* çağırma işleminin başlangıcında ve durdurulduğunda gerçekleşir. |
| <a name="environment-variable"></a>ENVIRONMENT_VARIABLE | Tür | Basit olay |
|  | Üst öğeler | [DERLEYICI](#compiler)<br/>[BAĞLAYıCı](#linker) |
|  | Alt | Yok |
|  | Özellikler | -Ortam değişkeninin adı<br/>-Ortam değişkeninin değeri. |
|  | Sınıfları yakala | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[EnvironmentVariable](cpp-event-data-types/environment-variable.md) |
|  | Açıklama | *CL. exe* veya *LINK. exe* çağrıldığında, var olan her ortam değişkeni için bir kez gerçekleşir. |
| <a name="executable-image-output"></a>EXECUTABLE_IMAGE_OUTPUT | Tür | Basit olay |
|  | Üst öğeler | [BAĞLAYıCı](#linker) |
|  | Alt | Yok |
|  | Özellikler | -Bir DLL veya yürütülebilir çıkış dosyasının mutlak yolu. |
|  | Sınıfları yakala | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[Dosya çıkışı](cpp-event-data-types/file-output.md)<br/>[Executableımageoutput](cpp-event-data-types/executable-image-output.md) |
|  | Açıklama | Bağlayıcı girdilerden biri DLL veya yürütülebilir bir görüntü dosyası olduğunda gerçekleşir. |
| <a name="exp-output"></a>EXP_OUTPUT | Tür | Basit olay |
|  | Üst öğeler | [BAĞLAYıCı](#linker) |
|  | Alt | Yok |
|  | Özellikler | - *. Exp* çıkış dosyasının mutlak yolu. |
|  | Sınıfları yakala | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[Dosya çıkışı](cpp-event-data-types/file-output.md)<br/>[ExpOutput](cpp-event-data-types/exp-output.md) |
|  | Açıklama | Bağlayıcının çıktılarından biri *. exp* dosyası olduğunda gerçekleşir. |
| <a name="file-input"></a>FILE_INPUT | Tür | Basit olay |
|  | Üst öğeler | [DERLEYICI](#compiler)<br/>[BAĞLAYıCı](#linker) |
|  | Alt | Yok |
|  | Özellikler | -Giriş dosyasının mutlak yolu<br/>-Giriş dosyasının türü |
|  | Sınıfları yakala | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[Dosya girişi](cpp-event-data-types/file-input.md) |
|  | Açıklama | Bir *CL. exe* veya *LINK. exe* girişini duyurmak için gerçekleşir. |
| <a name="force-inlinee"></a>FORCE_INLINEE | Tür | Basit olay |
|  | Üst öğeler | [FUNCTION](#function) |
|  | Alt | Yok |
|  | Özellikler | -Zorlamalı satır içine alınmış işlevin adı.<br/>-Bir ara yönerge sayısı olarak temsil edilen zorla satır içine alınmış işlevin boyutu. |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[Forceınlinee](cpp-event-data-types/force-inlinee.md) |
|  | Açıklama | Bir işlev, `__forceinline` anahtar sözcüğünün kullanımı aracılığıyla başka bir işleve zorla satır içine eklendiğinde gerçekleşir. |
| <a name="front-end-file"></a>FRONT_END_FILE | Tür | Etkinlik |
|  | Üst öğeler | [C1_DLL](#c1-dll)<br/>[FRONT_END_FILE](#front-end-file) |
|  | Alt | [FRONT_END_FILE](#front-end-file)<br/>[TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | Özellikler | -Dosyanın mutlak yolu. |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[FrontEndFile](cpp-event-data-types/front-end-file.md) |
|  | Açıklama | Derleyici ön ucu başladığında ve bir dosyayı işlemeyi durdurduğu zaman gerçekleşir. Bu olay özyinelemeli. Ön uç dahil edilen dosyaları ayrıştırırken özyineleme gerçekleşir. |
| <a name="front-end-pass"></a>FRONT_END_PASS | Tür | Etkinlik |
|  | Üst öğeler | [DERLEYICI](#compiler) |
|  | Alt | [C1_DLL](#c1-dll) |
|  | Özellikler | -Giriş kaynak dosyasına mutlak yol<br/>-Çıkış nesnesi dosyasının mutlak yolu |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[CompilerPass](cpp-event-data-types/compiler-pass.md)<br/>[FrontEndPass](cpp-event-data-types/front-end-pass.md) |
|  | Açıklama | Derleyicinin ön uç geçişinin başlangıcında ve durdurulduğunda gerçekleşir. Bu geçiş, C/C++ kaynak kodunu ayrıştırmaktan ve ara dile dönüştürmesinden sorumludur. |
| <a name="function"></a>ÇALıŞMAYACAKTıR | Tür | Etkinlik |
|  | Üst öğeler | [CODE_GENERATION](#code-generation)<br/>[ZINCIRININ](#thread)<br/>[TOP_DOWN](#top-down) |
|  | Alt | [FORCE_INLINEE](#force-inlinee) |
|  | Özellikler | -İşlevin adı |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[Çalışmayacaktır](cpp-event-data-types/function.md) |
|  | Açıklama | Bir işlev için kod oluşturma başlatılırken ve sona ermek üzere gerçekleşir. |
| <a name="imp-lib-output"></a>IMP_LIB_OUTPUT | Tür | Basit olay |
|  | Üst öğeler | [BAĞLAYıCı](#linker) |
|  | Alt | Yok |
|  | Özellikler | -Bir içeri aktarma kitaplığı çıkış dosyasının mutlak yolu. |
|  | Sınıfları yakala | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[Dosya çıkışı](cpp-event-data-types/file-output.md)<br/>[Implii put](cpp-event-data-types/imp-lib-output.md) |
|  | Açıklama | Bağlayıcının çıktılarından biri içeri aktarma kitaplığı olduğunda gerçekleşir. |
| <a name="lib-output"></a>LIB_OUTPUT | Tür | Basit olay |
|  | Üst öğeler | [BAĞLAYıCı](#linker) |
|  | Alt | Yok |
|  | Özellikler | -Statik kitaplık çıkış dosyasının mutlak yolu. |
|  | Sınıfları yakala | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[Dosya çıkışı](cpp-event-data-types/file-output.md)<br/>[Lii put](cpp-event-data-types/lib-output.md) |
|  | Açıklama | Bağlayıcının çıktılarından biri statik kitaplık olduğunda gerçekleşir. |
| <a name="linker"></a>BAĞLAYıCı | Tür | Etkinlik |
|  | Üst öğeler | Yok |
|  | Alt | [COMMAND_LINE](#command-line)<br/>[ENVIRONMENT_VARIABLE](#environment-variable)<br/>[EXECUTABLE_IMAGE_OUTPUT](#executable-image-output)<br/>[EXP_OUTPUT](#exp-output)<br/>[FILE_INPUT](#file-input)<br/>[IMP_LIB_OUTPUT](#imp-lib-output)<br/>[LIB_OUTPUT](#lib-output)<br/>[PASS1](#pass1)<br/>[PASS2](#pass2) |
|  | Özellikler | -Bağlayıcı sürümü<br/>-Çalışma dizini<br/>-Çağrılan *LINK. exe* ' ye mutlak yol |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[Çağrılması](cpp-event-data-types/invocation.md)<br/>[Bağlayıcı](cpp-event-data-types/linker.md) |
|  | Açıklama | Bir *LINK. exe* çağırma işleminin başlangıcında ve durdurulduğunda gerçekleşir. |
| <a name="ltcg"></a>LTCG | Tür | Etkinlik |
|  | Üst öğeler | [PASS1](#pass1) |
|  | Alt | [C2_DLL](#c2-dll) |
|  | Özellikler | Yok |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[LTCG](cpp-event-data-types/ltcg.md) |
|  | Açıklama | Bağlantı zamanı kod üretimi başlatma ve durdurma sırasında gerçekleşir. |
| <a name="obj-output"></a>OBJ_OUTPUT | Tür | Basit olay |
|  | Üst öğeler | [DERLEYICI](#compiler) |
|  | Alt | Yok |
|  | Özellikler | - *. Obj* çıkış dosyasının mutlak yolu |
|  | Sınıfları yakala | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[Dosya çıkışı](cpp-event-data-types/file-output.md)<br/>[ObjOutput](cpp-event-data-types/obj-output.md) |
|  | Açıklama | *CL. exe*tarafından üretilen her *. obj* çıktısı için bir kez gerçekleşir. |
| <a name="opt-icf"></a>OPT_ICF | Tür | Etkinlik |
|  | Üst öğeler | [PASS1](#pass1) |
|  | Alt | Yok |
|  | Özellikler | Yok |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[OptICF](cpp-event-data-types/opt-icf.md) |
|  | Açıklama | Aynı COMDAT katlama (/OPT: ICF) bağlayıcı iyileştirmesinin başlangıcında ve durdurulduğunda gerçekleşir. |
| <a name="opt-lbr"></a>OPT_LBR | Tür | Etkinlik |
|  | Üst öğeler | [PASS1](#pass1) |
|  | Alt | Yok |
|  | Özellikler | Yok |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[OptLBR](cpp-event-data-types/opt-lbr.md) |
|  | Açıklama | Uzun dal (/OPT: LBR) bağlayıcı iyileştirmesinin başlangıcında ve durdurulduğunda gerçekleşir. |
| <a name="opt-ref"></a>OPT_REF | Tür | Etkinlik |
|  | Üst öğeler | [PASS1](#pass1) |
|  | Alt | Yok |
|  | Özellikler | Yok |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[Seçenekbaşvurusu](cpp-event-data-types/opt-ref.md) |
|  | Açıklama | Başvurulmayan işlevler ve veri eleme (/OPT: REF) bağlayıcı iyileştirmesinin başlangıcında ve durdurulduğunda gerçekleşir. |
| <a name="pass1"></a>PASS1 | Tür | Etkinlik |
|  | Üst öğeler | [BAĞLAYıCı](#linker) |
|  | Alt | [LTCG](#ltcg)<br/>[OPT_ICF](#opt-icf)<br/>[OPT_LBR](#opt-lbr)<br/>[OPT_REF](#opt-ref) |
|  | Özellikler | Yok |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[Pass1](cpp-event-data-types/pass1.md) |
|  | Açıklama | Bağlayıcının pass 1 ' in başlangıcında ve durdurulduğunda gerçekleşir. |
| <a name="pass2"></a>PASS2 | Tür | Etkinlik |
|  | Üst öğeler | [BAĞLAYıCı](#linker) |
|  | Alt | Yok |
|  | Özellikler | Yok |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[Pass2](cpp-event-data-types/pass2.md) |
|  | Açıklama | Bağlayıcının Pass 2 ' nin başlangıcında ve durdurulduğunda gerçekleşir. |
| <a name="pre-ltcg-opt-ref"></a>PRE_LTCG_OPT_REF | Tür | Etkinlik |
|  | Üst öğeler | [PASS1](#pass1) |
|  | Alt | Yok |
|  | Özellikler | Yok |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[Preltcgseçenekbaşvurusu](cpp-event-data-types/pre-ltcg-opt-ref.md) |
|  | Açıklama | , Başvurulmayan işlevleri ve verileri ortadan kaldıran bağlayıcı iyileştirme geçişinin başlangıcında ve durdurulduğunda gerçekleşir (/OPT: REF). Bu işlem, bağlantı zaman kodu oluşturmadan önce yapılır. |
| <a name="symbol-name"></a>SYMBOL_NAME | Tür | Basit olay |
|  | Üst öğeler | [C1_DLL](#c1-dll) |
|  | Alt | Yok |
|  | Özellikler | -Tür anahtarı<br/> -Türün adı |
|  | Sınıfları yakala | [SimpleEvent](cpp-event-data-types/simple-event.md)<br/>[SymbolName](cpp-event-data-types/symbol-name.md) |
|  | Açıklama | Ön uç geçişinin sonunda gerçekleşir: şablon örneklemelerde yer alan her tür için bir kez. Anahtar, türü için sayısal bir tanıtıcıdır, ad ise metin gösterimidir. Tür anahtarları çözümlenmekte olan izleme içinde benzersizdir. Ancak, farklı derleyici ön uç geçişlerinden gelen farklı anahtarlar aynı türe işaret edebilir. Farklı derleyici ön uç geçişleri arasındaki türleri karşılaştırmak için adlarının kullanılması gerekir. SYMBOL_NAME olaylar, tüm şablon örneklemeleri gerçekleştirildikten sonra bir derleyici ön ucu geçişinin sonuna yayılır. |
| <a name="template-instantiation"></a>TEMPLATE_INSTANTIATION | Tür | Etkinlik |
|  | Üst öğeler | [C1_DLL](#c1-dll)<br/>[FRONT_END_FILE](#front-end-file)<br/>[TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | Alt | [TEMPLATE_INSTANTIATION](#template-instantiation) |
|  | Özellikler | -Özelleştirilmiş tür için anahtar<br/>-Birincil şablonun türünün anahtarı<br/>-Oluşturulan şablonun türü |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[Templateörneklemesi](cpp-event-data-types/template-instantiation.md) |
|  | Açıklama | Şablon örneklemesinin başlangıcında ve sonunda gerçekleşir. Birincil şablon türü (örneğin, `vector`) örneği oluşturulur ve özel bir tür (örneğin, `std::vector<int>`) olur. Her iki tür için de bir anahtar verilir. Bir anahtarı türün adına dönüştürmek için [SYMBOL_NAME](#symbol-name) olayını kullanın. Tür anahtarları çözümlenmekte olan izleme içinde benzersizdir. Ancak, farklı derleyici ön uç geçişlerinden gelen farklı anahtarlar aynı türe işaret edebilir. Farklı derleyici ön uç geçişleri arasındaki türleri karşılaştırmak için sembol adlarının kullanılması gerekir. Bu olay özyinelemeli. Ön uç iç içe geçmiş şablonları örnekledikten sonra bazı durumlarda özyineleme meydana gelir. |
| <a name="thread"></a>ZINCIRININ | Tür | Etkinlik |
|  | Üst öğeler | [CODE_GENERATION](#code-generation)<br/>[TOP_DOWN](#top-down) |
|  | Alt | [FUNCTION](#function) |
|  | Özellikler | Yok |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[Zincirinin](cpp-event-data-types/thread.md) |
|  | Açıklama | Derleyici arka uç iş parçacığı yürütmesinin başlangıcında ve sonunda gerçekleşir. Askıya alınan bir iş parçacığı sona erdi olarak kabul edilir. Uyandırıldığında bir iş parçacığı başlatılmış olarak kabul edilir. |
| <a name="top-down"></a>TOP_DOWN | Tür | Etkinlik |
|  | Üst öğeler | [WHOLE_PROGRAM_ANALYSIS](#whole-program-analysis) |
|  | Alt | [FUNCTION](#function)<br/>[ZINCIRININ](#thread) |
|  | Özellikler | Yok |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[Aşağı aşağı](cpp-event-data-types/top-down.md) |
|  | Açıklama | Tüm program analizinin yukarıdan açılan geçişinin başlangıcında ve durdurulduğunda gerçekleşir. |
| <a name="whole-program-analysis"></a>WHOLE_PROGRAM_ANALYSIS | Tür | Etkinlik |
|  | Üst öğeler | [C2_DLL](#c2-dll) |
|  | Alt | [BOTTOM_UP](#bottom-up)<br/>[TOP_DOWN](#top-down) |
|  | Özellikler | Yok |
|  | Sınıfları yakala | [Etkinlik](cpp-event-data-types/activity.md)<br/>[WholeProgramAnalysis](cpp-event-data-types/whole-program-analysis.md) |
|  | Açıklama | Bağlantı zamanı kod oluşturma işleminin tam program çözümleme aşamasının başlatılması ve durdurulması sırasında gerçekleşir. |

::: moniker-end
