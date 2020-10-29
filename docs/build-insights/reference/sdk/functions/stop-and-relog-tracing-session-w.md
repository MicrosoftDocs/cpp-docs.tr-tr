---
title: StopAndRelogTracingSessionW
description: C++ derleme öngörüleri SDK StopAndRelogTracingSessionW işlev başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndRelogTracingSessionW
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 9c39607b9d088be18fb24238428512be09d78c53
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922685"
---
# <a name="stopandrelogtracingsessionw"></a>StopAndRelogTracingSessionW

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`StopAndRelogTracingSessionW`İşlevi devam eden bir izleme oturumunu sonlandırır ve elde edilen izlemeyi geçici bir dosyaya kaydeder. Yeniden günlüğe kaydetme oturumu daha sonra giriş olarak geçici dosyayı kullanmaya hemen başlatılır. Yeniden günlüğe kaydetme oturumu tarafından üretilen son yeniden günlüğe kaydetme izlemesi, çağıran tarafından belirtilen bir dosyaya kaydedilir. Bu işlevi çağıran yürütülebilir dosyalar yönetici ayrıcalıklarına sahip olmalıdır.

## <a name="syntax"></a>Sözdizimi

```cpp
enum RESULT_CODE StopAndRelogTracingSessionW(
    const wchar_t*              sessionName,
    const wchar_t*              outputLogFile,
    TRACING_SESSION_STATISTICS* statistics,
    const RELOG_DESCRIPTOR*     relogDescriptor);
```

### <a name="parameters"></a>Parametreler

*OturumAdı*\
Durdurulacak izleme oturumunun adı. [Starttracingsession](start-tracing-session.md), [starttracingsessiona](start-tracing-session-a.md)veya [starttracingsessionw](start-tracing-session-w.md)öğesine geçirilen oturum adını kullanın.

*outputLogFile*\
Yeniden günlüğe kaydetme oturumu tarafından üretilen yeniden oturum açan izlemenin yazılacağı dosya.

*girecek*\
[TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) nesnesine yönelik işaretçi. `StopAndRelogTracingSessionW` döndürmeden önce bu nesnedeki izleme toplama istatistiklerini yazar.

*analysisDescriptor*\
[RELOG_DESCRIPTOR](../other-types/analysis-descriptor-struct.md) nesnesine yönelik işaretçi. Tarafından başlatılan yeniden günlüğe kaydetme oturumunu yapılandırmak için bu nesneyi kullanın `StopAndRelogTracingSessionW` .

### <a name="return-value"></a>Dönüş Değeri

[RESULT_CODE](../other-types/result-code-enum.md) numaralandırmasından elde edilen sonuç kodu.

::: moniker-end
