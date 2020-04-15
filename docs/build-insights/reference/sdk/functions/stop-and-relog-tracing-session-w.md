---
title: StopAndRelogTracingSessionW
description: C++ Build Insights SDK StopAndRelogTracingSessionW fonksiyon başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndRelogTracingSessionW
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c542ba8f313f30cf5adb069dd02cf3db29ffc532
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323686"
---
# <a name="stopandrelogtracingsessionw"></a>StopAndRelogTracingSessionW

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

İşlev `StopAndRelogTracingSessionW` devam eden bir izleme oturumunu durdurur ve ortaya çıkan izlemeyi geçici bir dosyaya kaydeder. Yeniden günlüğe kaydetme oturumu daha sonra geçici dosyayı giriş olarak kullanmaya başlar. Yeniden günlüğe kaydetme oturumu tarafından üretilen son yeniden kaydedilmiş izleme, arayan tarafından belirtilen bir dosyaya kaydedilir. Bu işlevi çağıran yürütülebilirlerin yönetici ayrıcalıkları olmalıdır.

## <a name="syntax"></a>Sözdizimi

```cpp
enum RESULT_CODE StopAndRelogTracingSessionW(
    const wchar_t*              sessionName,
    const wchar_t*              outputLogFile,
    TRACING_SESSION_STATISTICS* statistics,
    const RELOG_DESCRIPTOR*     relogDescriptor);
```

### <a name="parameters"></a>Parametreler

*Oturumadı*\
Durdurmak için izleme oturumunun adı. [StartTracingSession , StartTracingSessionA](start-tracing-session.md)veya [StartTracingSessionW'e](start-tracing-session-w.md)geçen oturum adı ile aynı oturum adını kullanın. [StartTracingSessionA](start-tracing-session-a.md)

*outputLogFile*\
Yeniden ağaçlandırılmak üzere üretilen relogged izin yazılabilmek için dosya.

*Istatistik*\
[TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) bir nesneye işaretçi. `StopAndRelogTracingSessionW`dönmeden önce bu nesneye izleme toplama istatistikleri yazar.

*analizAçıklayıcı*\
[RELOG_DESCRIPTOR](../other-types/analysis-descriptor-struct.md) bir nesneye işaretçi. Tarafından başlatılan yeniden günlüğe kaydetme oturumunu yapılandırmak için bu nesneyi `StopAndRelogTracingSessionW`kullanın.

### <a name="return-value"></a>Dönüş Değeri

[RESULT_CODE](../other-types/result-code-enum.md) enum bir sonuç kodu.

::: moniker-end
