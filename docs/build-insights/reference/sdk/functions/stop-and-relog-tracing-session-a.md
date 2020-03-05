---
title: StopAndRelogTracingSessionA
description: C++ BUILD Insights SDK StopAndRelogTracingSessionA işlev başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndRelogTracingSessionA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c9fe2ea47b378565d3ce9785b6f4cc3e541ebe80
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78332707"
---
# <a name="stopandrelogtracingsessiona"></a>StopAndRelogTracingSessionA

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`StopAndRelogTracingSessionA` işlevi devam eden bir izleme oturumunu durduruyor ve elde edilen izlemeyi geçici bir dosyaya kaydeder. Yeniden günlüğe kaydetme oturumu daha sonra giriş olarak geçici dosyayı kullanmaya hemen başlatılır. Yeniden günlüğe kaydetme oturumu tarafından üretilen son yeniden günlüğe kaydetme izlemesi, çağıran tarafından belirtilen bir dosyaya kaydedilir. Bu işlevi çağıran yürütülebilir dosyalar yönetici ayrıcalıklarına sahip olmalıdır.

## <a name="syntax"></a>Sözdizimi

```cpp
enum RESULT_CODE StopAndRelogTracingSessionA(
    const char*                 sessionName,
    const char*                 outputLogFile,
    TRACING_SESSION_STATISTICS* statistics,
    const RELOG_DESCRIPTOR*     relogDescriptor);
```

### <a name="parameters"></a>Parametreler

*oturumadı*\
Durdurulacak izleme oturumunun adı. [Starttracingsession](start-tracing-session.md), [starttracingsessiona](start-tracing-session-a.md)veya [starttracingsessionw](start-tracing-session-w.md)öğesine geçirilen oturum adını kullanın.

*Outputlogfile*\
Yeniden günlüğe kaydetme oturumu tarafından üretilen yeniden oturum açan izlemenin yazılacağı dosya.

*istatistikler*\
[TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) nesnesine yönelik işaretçi. `StopAndRelogTracingSessionA`, döndürmeden önce bu nesnedeki izleme toplama istatistiklerini yazar.

*Analysisdescriptor*\
[RELOG_DESCRIPTOR](../other-types/analysis-descriptor-struct.md) nesnesine yönelik işaretçi. `StopAndRelogTracingSessionA`tarafından başlatılan yeniden günlüğe kaydetme oturumunu yapılandırmak için bu nesneyi kullanın.

### <a name="return-value"></a>Dönüş Değeri

[RESULT_CODE](../other-types/result-code-enum.md) numaralandırmasından elde edilen sonuç kodu.

::: moniker-end
