---
title: Başlangıç OturumuW
description: C++ Build Insights SDK StartTracingSessionW fonksiyon başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StartTracingSessionW
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: af67c3be50cb19ccbfb7fe286e5d61cd1d241bf8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323792"
---
# <a name="starttracingsessionw"></a>Başlangıç OturumuW

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

İşlev `StartTracingSessionW` bir izleme oturumu başlatır. Bu işlevi çağıran yürütülebilirlerin yönetici ayrıcalıkları olmalıdır.

## <a name="syntax"></a>Sözdizimi

```cpp
enum RESULT_CODE StartTracingSessionW(
    const wchar_t*                 sessionName,
    const TRACING_SESSION_OPTIONS* options);
```

### <a name="parameters"></a>Parametreler

*Oturumadı*\
Başlayacak izleme oturumunun adı. [StopTracingSessionW](stop-tracing-session-w.md)veya başka bir durdurma izleme işlevini ararken aynı adı kullanın.

*Seçenekler*\
[TRACING_SESSION_OPTIONS](../other-types/tracing-session-options-struct.md) bir nesneye işaretçi. İzleme oturumu tarafından hangi olayların toplanması gerektiğini seçmek için bu nesneyi kullanın.

### <a name="return-value"></a>Dönüş Değeri

[RESULT_CODE](../other-types/result-code-enum.md) enum bir sonuç kodu.

::: moniker-end
