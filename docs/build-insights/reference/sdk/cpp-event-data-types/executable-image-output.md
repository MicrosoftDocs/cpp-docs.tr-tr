---
title: Executableımageoutput sınıfı
description: C++ BUILD Insights SDK Yürütülebilirımageoutput sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ExecutableImageOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 5a2e417a7dd976f257b4dd5a3aabfdf440c604fc
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333386"
---
# <a name="executableimageoutput-class"></a>Executableımageoutput sınıfı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`ExecutableImageOutput` sınıfı [Matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. [EXECUTABLE_IMAGE_OUTPUT](../event-table.md#executable-image-output) bir olayla eşleştirmek için kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class ExecutableImageOutput : public FileOutput
{
public:
    ExecutableImageOutput(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

[Dosya çıkışı](file-output.md) temel sınıfından devralınan üyelerle birlikte `ExecutableImageOutput` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[Executableımageoutput](#executable-image-output)

## <a name="executable-image-output"></a>Executableımageoutput

```cpp
ExecutableImageOutput(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[EXECUTABLE_IMAGE_OUTPUT](../event-table.md#executable-image-output) bir olay.

::: moniker-end
