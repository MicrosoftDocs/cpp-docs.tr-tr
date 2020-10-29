---
title: StartTracingSessionW
description: C++ Build Insights SDK 'Sı StartTracingSessionW işlev başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StartTracingSessionW
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: d89bd6d040f9786539c9be08b9da0813d3bb2c82
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922744"
---
# <a name="starttracingsessionw"></a>StartTracingSessionW

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`StartTracingSessionW`İşlevi bir izleme oturumu başlatır. Bu işlevi çağıran yürütülebilir dosyalar yönetici ayrıcalıklarına sahip olmalıdır.

## <a name="syntax"></a>Sözdizimi

```cpp
enum RESULT_CODE StartTracingSessionW(
    const wchar_t*                 sessionName,
    const TRACING_SESSION_OPTIONS* options);
```

### <a name="parameters"></a>Parametreler

*OturumAdı*\
Başlatılacak izleme oturumunun adı. [Stoptracingsessionw](stop-tracing-session-w.md)veya diğer durdurma izleme işlevini çağırırken aynı adı kullanın.

*Seçenekler*\
[TRACING_SESSION_OPTIONS](../other-types/tracing-session-options-struct.md) nesnesine yönelik işaretçi. İzleme oturumu tarafından hangi olayların toplanması gerektiğini seçmek için bu nesneyi kullanın.

### <a name="return-value"></a>Dönüş Değeri

[RESULT_CODE](../other-types/result-code-enum.md) numaralandırmasından elde edilen sonuç kodu.

::: moniker-end
