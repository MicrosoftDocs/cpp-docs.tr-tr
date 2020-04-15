---
title: ExecutableImageOutput sınıfı
description: C++ Build Insights SDK ExecutableImageOutput sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ExecutableImageOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 834689a3605b729260f2d4c925396ee1af1bb705
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324950"
---
# <a name="executableimageoutput-class"></a>ExecutableImageOutput sınıfı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Sınıf `ExecutableImageOutput` [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)ve [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) işlevleri ile kullanılır. [EXECUTABLE_IMAGE_OUTPUT](../event-table.md#executable-image-output) bir olayı eşleştirmek için kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class ExecutableImageOutput : public FileOutput
{
public:
    ExecutableImageOutput(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

[Dosya Çıktısı](file-output.md) taban sınıfından devralınan üyelerle `ExecutableImageOutput` birlikte, sınıf aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[ÇalıştırılabilirImageOutput](#executable-image-output)

## <a name="executableimageoutput"></a><a name="executable-image-output"></a>ÇalıştırılabilirImageOutput

```cpp
ExecutableImageOutput(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*Olay*\
[EXECUTABLE_IMAGE_OUTPUT](../event-table.md#executable-image-output) bir olay.

::: moniker-end
