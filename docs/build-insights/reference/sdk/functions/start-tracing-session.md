---
title: StartTracingSession
description: C++ Build Insights SDK 'Sı StartTracingSession işlev başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StartTracingSession
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: de9d46b4a684d66bf01f76e7ea753694cf40d2cd
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78332623"
---
# <a name="starttracingsession"></a>StartTracingSession

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`StartTracingSession` işlevi bir izleme oturumu başlatır. Bu işlevi çağıran yürütülebilir dosyalar yönetici ayrıcalıklarına sahip olmalıdır.

## <a name="syntax"></a>Sözdizimi

```cpp
RESULT_CODE StartTracingSession(
    const char*                    sessionName,
    const TRACING_SESSION_OPTIONS& options);

RESULT_CODE StartTracingSession(
    const wchar_t*                 sessionName,
    const TRACING_SESSION_OPTIONS& options);
```

### <a name="parameters"></a>Parametreler

*oturumadı*\
Başlatılacak izleme oturumunun adı. [Stoptracingsession](stop-tracing-session.md) veya diğer durdurma izleme işlevini çağırırken aynı adı kullanın.

*seçenekler*\
[TRACING_SESSION_OPTIONS](../other-types/tracing-session-options-struct.md) nesnesine yönelik işaretçi. İzleme oturumu tarafından hangi olayların toplanması gerektiğini seçmek için bu nesneyi kullanın.

### <a name="return-value"></a>Dönüş Değeri

[RESULT_CODE](../other-types/result-code-enum.md) numaralandırmasından elde edilen sonuç kodu.

::: moniker-end
